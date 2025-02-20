# Errors de comunicació entre màquines
Aquests procesos s'hauran d'aplicar a cada màquina (3) introduïnt la seva IP vàlida, tal i com es demana a l'enunciat.

## **1️. Comprovar el Mode de Xarxa**
Obre **VirtualBox** i revisa la configuració de xarxa de cada MV:
1. **Si estàs utilitzant "Red Interna"**, no hi ha passarel·la per defecte.
3. **Si només necessites comunicació entre MVs, assegura't que totes dues estan a la mateixa "Red Interna"** i **no configures cap passarel·la**.

---

## **2️. Configurar IP sense Gateway**
Si fas servir "Red Interna" (`intnet`), no has de configurar `gateway4`. Modifica **Netplan** a `nom-cpd-monitor`:
```bash
    sudo nano /etc/netplan/00-installer-config.yaml
```
Afegeix/modifica:
```yaml
network:
  version: 2
  ethernets:
    enp0s3:
      dhcp4: no
      addresses:
        - 192.168.1.30/24
      nameservers:
        addresses: [8.8.8.8, 1.1.1.1]
```

```bash
    sudo netplan apply
```
Ara comprova la connexió:
```bash
    ping -c 4 192.168.1.20
```

---

## **3. Força que la interfície `enp0s3` s'activi manualment**
Executa a `nom-cpd-storage`:
```bash
    sudo ip link set enp0s3 up  
    sudo ip addr add 192.168.1.20/24 dev enp0s3
```
**Verifica que l'IP s'ha aplicat correctament:**
```bash
    ip a show enp0s3
```

---


## **4. Verifica la ruta de cada màquina**
Executa a **cada màquina**:
```bash
  ip route show
```
**Si no veus una ruta a `192.168.1.0/24`, afegeix-la manualment:**
```bash
  sudo ip route add 192.168.1.0/24 dev enp0s3
```
---

## **Últim test: Comprovar connectivitat**
Després de tot, intenta fer `ping` entre màquines:
```bash
    ping -c 4 192.168.1.20   # des de nom-cpd-monitor
    ping -c 4 192.168.1.30   # des de nom-cpd-storage
```

# **Explicacions:**

### **1️. Per què hem de tocar Netplan?**
**Netplan** és el gestor de configuració de xarxa a Ubuntu a partir de la versió 18.04. Quan configures la IP estàtica d'una interfície de xarxa, Netplan s'encarrega d'aplicar els canvis al sistema i assegurar que es mantenen després de reiniciar.

- Si **NO modifiquem Netplan**, qualsevol canvi manual fet amb `ip addr add` desapareixerà en reiniciar la màquina.
- Si usem **"Red Interna"**, no necessitem configurar cap `gateway4`, ja que no hi ha un router.

---

### **2️. Per què es força la interfície `enp0s3`?**
Quan una interfície de xarxa no està activada (`DOWN`), no pot comunicar-se amb altres dispositius, fins i tot si té una IP assignada.

- Quan forcem **`ip link set enp0s3 up`**, assegurem que l'adaptador està operatiu.
- **Problema comú:** Algunes vegades VirtualBox no activa la interfície automàticament, i cal fer-ho manualment.

---

### **3️. Per què s'afegeix la ruta `192.168.1.0/24`?**
**El sistema ha de saber com arribar a altres màquines de la mateixa xarxa.** Normalment, això passa automàticament quan assignem una IP, però si:
- No hi ha una ruta per defecte,
- Netplan no l'ha aplicat correctament,
- S'ha configurat manualment sense reiniciar serveis,

aleshores cal afegir-la manualment amb:
```bash
sudo ip route add 192.168.1.0/24 dev enp0s3
```
**Sense aquesta ruta, la màquina no sap que altres IPs de la xarxa `192.168.1.0/24` són accessibles a través de `enp0s3`**.

---

### **Conclusió**
- **Netplan** → Perquè els canvis siguin permanents.
- **Activar `enp0s3`** → Perquè pugui comunicar-se.
- **Afegir la ruta** → Perquè les màquines es vegin entre elles.


