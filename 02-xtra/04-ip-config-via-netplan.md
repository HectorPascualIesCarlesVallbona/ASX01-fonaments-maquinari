# IP configuration via Netplan

Per afegir una **IP estàtica** en una màquina amb **Netplan**, segueix aquests passos:

---

## **1️⃣ Comprovar el nom de la interfície de xarxa**
Abans de modificar la configuració, has d’identificar el nom de la interfície de xarxa. Executa:
```bash
ip a
```
Busca el nom de la interfície de xarxa activa, que pot ser:
- **Interfície Ethernet (per cable):** `eth0`, `ens33`, `enp0s3`, etc.
- **Interfície WiFi:** `wlan0`, `wlp3s0`, etc.

---

## **2️⃣ Editar el fitxer de configuració de Netplan**
Obre el fitxer de configuració de Netplan:
```bash
sudo nano /etc/netplan/50-cloud-init.yaml
```
(O `sudo nano /etc/netplan/01-netcfg.yaml` si el primer no existeix.)

---

## **3️⃣ Afegir la configuració d'IP estàtica**
Depenent del tipus de connexió (WiFi o Ethernet), afegeix la configuració adequada.

### **🔹 Per a Ethernet (Cablejat)**
```yaml
network:
  version: 2
  ethernets:
    ens33:  # Substitueix amb el nom correcte de la interfície
      dhcp4: no
      addresses:
        - 192.168.1.100/24
      gateway4: 192.168.1.1
      nameservers:
        addresses:
          - 8.8.8.8
          - 1.1.1.1
```

---

### **🔹 Per a WiFi**
Si la màquina està connectada via WiFi, la configuració ha de contenir les credencials de la xarxa:

```yaml
network:
  version: 2
  wifis:
    wlp3s0:  # Substitueix amb el nom correcte de la interfície
      dhcp4: no
      addresses:
        - 192.168.1.150/24
      gateway4: 192.168.1.1
      nameservers:
        addresses:
          - 8.8.8.8
          - 1.1.1.1
      access-points:
        "NomDeLaTevaXarxaWiFi":
          password: "LaTevaContrasenya"
```

---

## **4️⃣ Aplicar la configuració**
Després de guardar el fitxer (`Ctrl + X`, `Y`, `Enter`), aplica els canvis amb:
```bash
sudo netplan apply
```
Si vols provar la configuració abans de confirmar-la:
```bash
sudo netplan try
```
(Això et permetrà revertir els canvis si alguna cosa falla.)

---

## **5️⃣ Verificar que la configuració s'ha aplicat**
Executa:
```bash
ip a
ip route show
```
Fes un **ping al gateway** per assegurar que tens connexió:
```bash
ping -c 4 192.168.1.1
```

---

## **⚠ Errors comuns i solucions**
🔹 **Error: "Invalid YAML"** → Comprova la **indentació** (ha de ser amb espais, no tabuladors).  
🔹 **No aplica els canvis** → Prova `sudo netplan apply --debug` per veure detalls d'error.  
🔹 **Sense connexió a Internet** → Comprova la passarel·la (`gateway4`) i els DNS (`nameservers`).  
