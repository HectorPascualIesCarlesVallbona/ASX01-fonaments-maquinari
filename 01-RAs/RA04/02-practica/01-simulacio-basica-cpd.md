# **UF04 - Pràctica 01: Simulació avançada d’un CPD amb VirtualBox**  

## **1. Objectiu de la pràctica**  
Aquesta pràctica té com a objectiu la configuració d’un entorn **simulat de Centre de Processament de Dades (CPD)** en **VirtualBox**, amb tres màquines virtuals que compleixen diferents funcions dins d'un entorn corporatiu. 

Cada màquina tindrà una configuració específica i hauràs de connectar-les en una xarxa interna simulada. 

**Aprendràs a:**  
✅ Configurar una xarxa interna entre servidors.  
✅ Assignar **IP estàtiques** amb `netplan`.  
✅ Configurar **Samba** per compartir fitxers entre servidors.  
✅ Instal·lar i configurar **Zabbix Server** per monitoritzar el sistema.  
✅ Implementar un sistema de **seguretat bàsica** amb `ufw` i usuaris dedicats. 

**Terminologia**:
1. **Samba**: és un servei fonamental en molts CPDs perquè permet compartir fitxers i recursos entre diferents servidors o usuaris dins d’una xarxa.
2. **Zabbix Server**: és una eina de monitoratge en temps real que permet supervisar l’estat de servidors, serveis i recursos de xarxa, ajudant a detectar problemes abans que afectin els usuaris.
3. **UFW**: és una eina per a la gestió de tallafocs en sistemes Linux basada en iptables, però amb una interfície més senzilla. És especialment útil per controlar el trànsit de xarxa en un CPD i garantir la seguretat dels servidors.

---

## **2. Configuració inicial de VirtualBox**  
### 🔹 **Descarrega i prepara les imatges del sistema**
1. **Descarrega la ISO d’Ubuntu Server LTS** des de [aquest enllaç](https://ubuntu.com/download/server).  
2. **Crea tres màquines virtuals** amb els paràmetres següents:  

| Nom VM | CPU | RAM | Disc | Xarxa |
|--------|-----|-----|------|--------|
| `nomcognom-cpd-mgmt` | 2 vCPU | 2 GB | 20 GB | Interna (`CPD_Network`) |
| `nomcognom-cpd-storage` | 2 vCPU | 2 GB | 30 GB | Interna (`CPD_Network`) |
| `nomcognom-cpd-monitor` | 2 vCPU | 2 GB | 20 GB | Interna (`CPD_Network`) |

### 🔹 **Instal·lació del sistema operatiu**
Instal·la **Ubuntu Server** en cadascuna de les màquines amb els següents criteris:  
- **Nom d’usuari i hostname:** `nomcognom-cpd-*` (on `*` és `mgmt`, `storage` o `monitor`).  
- **Només interfície de xarxa interna (`CPD_Network`)** sense adaptadors externs.  
- **Eina necessària:** `VirtualBox`  

---

## **3. Configuració de la xarxa interna i IP estàtiques**  

### 🔹 **Assignació d’IP estàtiques amb `netplan`**  
Cada màquina ha de tenir una adreça IP fixa. Configura `netplan` perquè cada servidor tingui la següent adreça:  

| Servidor | IP Assignada | Descripció |
|----------|------------|------------|
| `nomcognom-cpd-mgmt` | `192.168.1.10` | Servidor de gestió |
| `nomcognom-cpd-storage` | `192.168.1.20` | Servidor d’emmagatzematge |
| `nomcognom-cpd-monitor` | `192.168.1.30` | Servidor de monitoratge |

📌 **Referència oficial sobre `netplan`**:  
🔗 [https://ubuntu.com/server/docs/network-configuration](https://ubuntu.com/server/docs/network-configuration)  

Comprova la connexió entre servidors fent `ping` entre ells.

---

## **4. Configuració del servidor d’emmagatzematge (Samba)**  

### 🔹 **Instal·lació i configuració de Samba**  
A la màquina `nomcognom-cpd-storage`, instal·la i configura Samba per compartir fitxers entre servidors.  

📌 **Referència oficial sobre Samba**:  
🔗 [https://ubuntu.com/server/docs/samba-file-server](https://ubuntu.com/server/docs/samba-file-server)  

#### **Tasques a realitzar:**  
✅ Instal·lar el servei **Samba**.  
✅ **Crear el directori compartit `/srv/samba/nomcognom-share/`** i establir els permisos adequats.  
✅ Configurar **`smb.conf`** per definir un recurs compartit amb permisos d'accés.  
✅ Crear un usuari de Samba (`smbpasswd -a usuari`) per accedir al recurs.  
✅ Reiniciar el servei (`systemctl restart smbd`).  
✅ Comprovar l'accés des de les altres màquines.  

---

## **5. Configuració del sistema de monitoratge (Zabbix Server)**  

### 🔹 **Instal·lació i configuració de Zabbix Server**  
A la màquina `nomcognom-cpd-monitor`, instal·la **Zabbix Server** i configura’l per monitoritzar l’entorn.  

📌 **Documentació oficial de Zabbix Server:**  
🔗 [https://www.zabbix.com/documentation/current/manual/installation/install](https://www.zabbix.com/documentation/current/manual/installation/install)  

#### **Tasques a realitzar:**  
✅ Instal·lar **Zabbix Server** i la seva base de dades.  
✅ Crear i configurar la base de dades (`mysql -u root -p`).  
✅ Modificar la configuració del servidor per establir les credencials correctes.  
✅ **Configurar un agent de monitoratge a `nomcognom-cpd-mgmt`**.  
✅ Reiniciar el servei i accedir a la interfície web (`http://192.168.1.30/zabbix`).  

---

## **6. Configuració de seguretat i accés remot**  

### 🔹 **Firewall amb `ufw`**
Implementa regles bàsiques de seguretat a cada servidor:  

```bash
sudo ufw allow from 192.168.1.0/24 to any port 22
sudo ufw allow from 192.168.1.30 to any port 10050
sudo ufw enable
```

📌 **Documentació oficial d’`ufw`**:  
🔗 [https://help.ubuntu.com/community/UFW](https://help.ubuntu.com/community/UFW)  

---

## **7. Validació i informe final**  

| 📝 Tasca | ✅ Verificació |
|----------|--------------|
| **IP estàtiques configurades** | `ping 192.168.1.20` des de `mgmt` |
| **Compartició de fitxers Samba** | `smbclient -L //192.168.1.20 -N` |
| **Accés a Zabbix Server** | `http://192.168.1.30/zabbix` |
| **Firewall actiu** | `ufw status` |

📌 **Lliurament obligatori:**  
📸 Captures de pantalla de **configuració de VirtualBox**.  
📸 Captures de **ping, smbclient i Zabbix**.  
📄 Explicació detallada dels passos realitzats.  

---

## ⚠️ **IMPORTANT**
🚨 **Normes d'entrega:**  
- ❗ **Data límit d'entrega**: Passat aquest dia, la nota serà **0**.  
- ❗ **Copiar d’un company** implica un **0 a tota l’UF**.  
- ❗ **Captures de pantalla obligatòries** on es vegi el **nom i cognom de l’alumne**.  
- ❗ **Només es pot abandonar l'aula després d’entregar la pràctica a Moodle**.  

