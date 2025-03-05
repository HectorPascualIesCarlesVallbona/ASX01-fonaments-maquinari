# **Pràctica 2: Implementació d’un servidor d'alt rendiment**

## **Objectiu**
Dissenyar un sistema mínimament redundant dins d’un CPD virtualitzat, configurant servidors amb tolerància a fallades, seguretat de xarxa i mecanismes bàsics de monitorització.

---

## **1. Configuració del sistema**
1. **Crea dues màquines virtuals**:
   - **SO**: Ubuntu Server.
   - **Servidor-Principal**: 2 CPU, 4 GB RAM, 2 discos (40 GB SO, 20 GB dades).
   - **Servidor-Backup**: 1 CPU, 2 GB RAM, 2 discos (40 GB SO, 20 GB dades).
   - Xarxa en **mode "Bridged"**.
   - **Si tens problemes amb mode Bridge**: [Nat and host only connection](../02-xtra/05-nat-and-host-only-connection.md)

2. **Configura RAID 1 al Servidor-Principal**:
   - Usa `mdadm` per unir els dos discos de dades.
   - Munta el RAID a `/mnt/dades/`.

3. **Configura sincronització automàtica** amb `rsync`:
   - Copia `/mnt/dades/` del `Servidor-Principal` al `Servidor-Backup` cada 6 hores.

---

## **2. Seguretat i protecció de xarxa**
1. **Firewall (`iptables` o `ufw`)**:
   - Permet només trànsit intern entre servidors.
   - Bloqueja tot excepte SSH des d’una IP autoritzada.

2. **Protecció contra atacs**:
   - Instal·la `fail2ban` per bloquejar intents de força bruta a SSH.
   - Simula un atac (intents fallits d’accés) i comprova el bloqueig.

---

## **3. Monitorització bàsica i consulta SNMP**
Per garantir el monitoratge dels servidors dins del CPD, s’ha d’implementar un sistema bàsic de supervisió mitjançant el protocol **SNMP (Simple Network Management Protocol)**. Aquest sistema permet obtenir informació en temps real sobre l’estat del **Servidor-Principal**.

### **3.1 Instal·lació i configuració de SNMP**
1. Instal·la i configura el servei **SNMP** (`snmpd`) al `Servidor-Principal`.
2. Configura una comunitat SNMP segura que permeti només consultes des de la xarxa interna.
3. Comprova que el servei està funcionant correctament.

### **3.2 Consulta d’informació del sistema**
Des del **Servidor-Backup**, fes una consulta SNMP per obtenir informació del `Servidor-Principal`. La consulta ha de recuperar almenys:
- L’ús actual de CPU.
- La memòria RAM disponible.
- L’espai lliure al sistema de fitxers.

### **3.3 Validació de la monitorització**
1. Compara la informació obtinguda via SNMP amb els valors que es poden veure localment al `Servidor-Principal` amb comandes com `htop` o `df -h`.
2. Explica com podries integrar aquesta informació en un sistema de monitoratge més avançat com **Zabbix o Prometheus**.

---

## **4. Simulació de fallades i recuperació**
1. **Força la fallada d’un disc en RAID**:
   ```bash
   mdadm --fail /dev/sdb1
   ```
   - Comprova la degradació amb:
     ```bash
     cat /proc/mdstat
     ```
   - Reemplaça el disc i reconstrueix el RAID.

2. **Apaga el `Servidor-Principal` i verifica l’accés a les dades des del `Servidor-Backup`**.

---

## **5. Entrega i criteris d’avaluació**
- **(30%) Configuració del sistema i RAID.**
- **(25%) Seguretat i firewall ben implementats.**
- **(25%) Monitorització funcional i correcta.**
- **(20%) Simulació de fallades i recuperació efectiva.**
- **(10%) Informe clar amb captures i explicacions.**

---

## ⚠️ **IMPORTANT**
🚨 **Normes d'entrega:**  
- ❗ **Data límit d'entrega**: 14-03-2025 | 23:59, Passat aquest dia, la nota serà **0**.  
- ❗ **Copiar d’un company** implica un **0 a tota l’UF**.  
- ❗ **Captures de pantalla obligatòries** on es vegi el **nom i cognom de l’alumne**.  
- ❗ **Només es pot abandonar l'aula després d’entregar la pràctica a Moodle**.  

