# **Components de Maquinari en un CPD a empreses**

Els Centres de Processament de Dades (CPD) són infraestructures essencials per a les empreses, encarregades d’emmagatzemar, processar i distribuir informació de manera eficient.

---

## **1️⃣ Servidors i Processadors d’Alt Rendiment**

Els servidors són els ordinadors especialitzats que gestionen les aplicacions i dades d’una empresa. Estan dissenyats per funcionar **24/7** i suportar càrregues de treball elevades.

### **📌 Components principals d’un servidor:**
1. **Processador (CPU - Central Processing Unit):**  
   - És el cervell del servidor.  
   - Exemples: **Intel Xeon, AMD EPYC**.  
   - Optimitzat per **múltiples fils d’execució simultanis**.  
   - Inclou tecnologies com **virtualització i multithreading** per gestionar moltes tasques alhora.  

2. **Memòria RAM (Random Access Memory):**  
   - Emmagatzema informació temporal mentre el servidor processa les dades.  
   - Tipus més usat: **RAM ECC (Error-Correcting Code)**, que **corregeix errors automàticament** per evitar fallades crítiques.  

3. **Placa base (Motherboard):**  
   - Connecta tots els components del servidor.  
   - Inclou **ranures d’expansió PCIe** per targetes de xarxa i emmagatzematge d’alt rendiment.  

4. **Fonts d’alimentació redundants:**  
   - Eviten fallades per talls elèctrics.  
   - Es poden substituir en calent sense apagar el servidor.  

5. **Xassís i sistema de refrigeració:**  
   - Carcassa dissenyada per una ventilació òptima.  
   - Pot incloure **refrigeració líquida** en servidors d’alt rendiment.  

---

## **2️⃣ Sistemes d’Emmagatzematge**

Els CPD gestionen grans quantitats de dades i necessiten sistemes d’emmagatzematge ràpids i segurs.

### **📌 Tipus de discos d’emmagatzematge:**
1. **HDD (Hard Disk Drive):**  
   - Dispositius mecànics tradicionals.  
   - Major capacitat d’emmagatzematge a un cost menor.  
   - Més lents que els SSD.  

2. **SSD (Solid State Drive):**  
   - No tenen parts mòbils → **més velocitat i durabilitat**.  
   - Ideals per a bases de dades i sistemes operatius crítics.  
   - **SSD NVMe**: Format més ràpid, es connecta per PCIe en lloc de SATA.  

3. **RAID (Redundant Array of Independent Disks):**  
   - Combina diversos discos per millorar **rendiment i seguretat**.  
   - Exemples:  
     - **RAID 0** (més velocitat, sense redundància).  
     - **RAID 1** (mirall: còpia exacta dels discos).  
     - **RAID 5/6/10** (combinació de velocitat i redundància).  

### **📌 Tipus d’arquitectures d’emmagatzematge:**
1. **DAS (Direct Attached Storage):**  
   - Emmagatzematge **connectat directament** a un servidor.  
   - Sense xarxa compartida.  
   - Exemple: Un disc SSD instal·lat dins d’un servidor.  

2. **NAS (Network Attached Storage):**  
   - Sistema d’emmagatzematge connectat a la xarxa.  
   - Accessible per múltiples servidors i dispositius.  
   - Exemple: Un servidor de fitxers en una empresa.  

3. **SAN (Storage Area Network):**  
   - Xarxa d’alta velocitat dedicada a emmagatzematge.  
   - Ús empresarial, permet **accés ràpid i escalabilitat**.  
   - Exemple: Data Centers que gestionen grans bases de dades.  

📌 **Exemple d’ús:** Un banc necessita un sistema SAN amb RAID per garantir que les dades dels comptes es repliquin en diversos servidors i mai es perdin per una fallada.

---

## **3️⃣ Infraestructura de Xarxa d’Alt Rendiment**

La xarxa d’un CPD connecta els servidors entre si i amb els usuaris finals. Una infraestructura de xarxa deficient pot provocar **col·lapses i retards en la transmissió de dades**.

### **📌 Components principals d’una xarxa en un CPD:**
1. **Encaminadors (Routers):**  
   - Gestionen el trànsit de dades entre xarxes internes i externes.  
   - Exemple: Un encaminador que connecta la xarxa d’un CPD a Internet.  

2. **Commutadors (Switches):**  
   - Connecten dispositius dins de la mateixa xarxa.  
   - Tipus:
     - **Switch Layer 2**: Assigna connexions entre dispositius dins de la mateixa xarxa.  
     - **Switch Layer 3**: Pot prendre decisions de xarxa més avançades (ruting).  

3. **Firewall de maquinari:**  
   - Protegeix el CPD de ciberatacs filtrant el trànsit maliciós.  
   - Pot ser un dispositiu físic dedicat o un servidor de seguretat.  

4. **Balancejadors de càrrega:**  
   - Distribueixen el trànsit entre múltiples servidors per evitar sobrecàrregues.  
   - Exemple: Si molts usuaris accedeixen a una web, un balancejador deriva el trànsit entre diversos servidors per mantenir el rendiment.  

5. **Tecnologia SDN (Software-Defined Networking):**  
   - Xarxa programable per adaptar-se a diferents necessitats sense necessitat de reconfiguració manual.  
   - Exemple: Google Cloud utilitza SDN per optimitzar la seva infraestructura.  

6. **Cables i fibra òptica:**  
   - Connexions d’alta velocitat entre dispositius de xarxa.  
   - La fibra òptica permet transmissions de dades a gran velocitat i distància.  

📌 **🔹 Exemple d’ús:** Un servei de streaming de vídeo com Netflix necessita un balancejador de càrrega per garantir que milions d’usuaris puguin accedir als seus vídeos sense retards.

---

# **📌 Resum per la Pissarra**
🖥️ **1️⃣ Servidors i Processadors**
   - **CPU (Intel Xeon, AMD EPYC)**: Execució eficient de processos.  
   - **RAM ECC**: Evita errors de memòria.  
   - **Fonts d’alimentació redundants**: Prevenció de fallades elèctriques.  
   - **Refrigeració (aire/líquid)**: Manté la temperatura òptima.  

💾 **2️⃣ Sistemes d’Emmagatzematge**
   - **HDD (més capacitat), SSD NVMe (més velocitat)**.  
   - **RAID**: Redundància i seguretat de dades.  
   - **DAS, NAS, SAN**: Diferents maneres d’organitzar l’emmagatzematge.  

🌐 **3️⃣ Infraestructura de Xarxa**
   - **Encaminadors**: Connecten xarxes.  
   - **Switches**: Interconnecten servidors.  
   - **Firewalls**: Protecció contra atacs.  
   - **Balancejadors de càrrega**: Reparteixen el trànsit.  
   - **Fibra òptica**: Connexió d’alta velocitat.  

