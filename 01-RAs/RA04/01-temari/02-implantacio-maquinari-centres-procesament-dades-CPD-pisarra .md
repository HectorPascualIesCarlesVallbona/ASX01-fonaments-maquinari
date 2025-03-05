# RA04 - PISSARRA - Implantació de maquinari en centres de processament de dades (CPD)

## Metodologia entrega pràctiques i examen
- < 4 => pràctica => suspesa RA => presentar pràctica al juny
- < 4 => examen   => suspesa RA
- copiat company  => RA suspesa => t'has de presentar a tota la RA al juny
- pràctiques si no es segueix estructura de la pràctica 

## 1. Introducció als Centres de Processament de Dades (CPD)

### 1.1 Definició
Un Centre de Processament de Dades (CPD), o Data Center, és una instal·lació que reuneix equips informàtics per gestionar grans volums de dades i oferir serveis essencials per a empreses i organitzacions. La seva funció no es limita només a l'emmagatzematge d'informació, sinó que també inclou la gestió de la seguretat, la redundància i l'accessibilitat a les dades, garantint que estiguin disponibles en tot moment. 

### 1.2 Tipus de CPD
Segons la seva infraestructura i el model de desplegament.

1. **tradicionals** són infraestructures físiques que es troben dins de les instal·lacions d'una organització.
  **Exemple institut**

2. **modulars** estan dissenyats per ser escalables i fàcilment desplegables. Es basen en mòduls prefabricats que es poden ampliar segons les necessitats de l'empresa.
https://www.datacenterdynamics.com/es/features/campos-corporaci%C3%B3n-presenta-su-centro-de-datos-industrializado-modular-escalable-y-de-alta-disponibilidad/

3. **núvol**, també coneguts com a Cloud Data Centers, es gestionen a través de proveïdors externs com AWS, Azure o Google Cloud.

4. **híbrids** combinen infraestructures físiques amb serveis al núvol.

### 1.3 Tendències actuals en la gestió de CPD
- la virtualització i l'automatització han permès maximitzar l'ús dels recursos disponibles i facilitar la gestió remota de les infraestructures.
- sostenibilitat i l'eficiència energètica.


## 2. Diferències entre maquinari de tipus personal i empresarial

### 2.1 Característiques dels sistemes personals
Els ordinadors personals estan pensats per a ús domèstic o oficines petites.
No potència comparació amb sistemes empresarials

### 2.2 Característiques dels sistemes empresarials
Els sistemes empresarials, com els servidors i les estacions de treball avançades, estan dissenyats per funcionar de manera contínua i garantir una seguretat i eficiència òptimes en entorns professionals exigents.

## 3. Anàlisi d'entorns que requereixen solucions de maquinari específiques
L'elecció del maquinari en un CPD no és una decisió estàndard, sinó que ha de ser adaptada a les necessitats específiques de cada organització. Cada sector té requeriments diferents en termes de potència de càlcul, capacitat d'emmagatzematge, seguretat i disponibilitat. A continuació, tipus entorns:

1. Entorns amb alta demanda de processament

Les empreses i institucions que necessiten una gran capacitat de càlcul recorren a servidors d'alt rendiment amb múltiples processadors i grans quantitats de memòria RAM. Això és essencial en camps com la recerca científica, la simulació d'esdeveniments físics i la intel·ligència artificial.

Per exemple, en el sector financer. Així mateix, les universitats i centres de recerca.

2. Necessitats d’emmagatzematge massiu i accés ràpid

En sectors com el multimèdia, el big data i la gestió documental, es requereixen grans sistemes d’emmagatzematge amb temps de resposta ràpids. L’ús de sistemes NAS (Network Attached Storage) o SAN (Storage Area Network) és essencial per garantir la disponibilitat i protecció de la informació.

Un exemple clar és la indústria audiovisual.

3. Entorns de seguretat i protecció de dades

La gestió de dades sensibles en sectors com la banca, la salut i l'administració pública implica l'ús de sistemes de maquinari amb alts estàndards de seguretat. 

Els bancs. En el sector sanitari.

4. Infraestructures per a aplicacions en temps real

Els sistemes que necessiten respostes instantànies, com els de telecomunicacions o els de control de trànsit aeri, han de comptar amb servidors i xarxes d’alta velocitat per minimitzar la latència.

Per exemple, en la borsa de valors. De manera similar, els sistemes de seguretat pública, com el control de videovigilància urbana.

5. Requisits d’alta disponibilitat i tolerància a fallades

Els sistemes crítics, com els dels hospitals, aeroports o centrals elèctriques, requereixen una infraestructura dissenyada per mantenir-se operativa sense interrupcions. Això s'aconsegueix mitjançant arquitectures de redundància amb servidors replicats, alimentació ininterrompuda (UPS) i sistemes de recuperació automàtica davant fallades.

Per exemple, en els hospitals.

6. Adaptació a entorns físics i condicions ambientals extremes

No tots els CPD es troben en llocs amb condicions ambientals òptimes. Algunes instal·lacions han de suportar temperatures extremes, alta humitat o presència de pols i contaminants. Això requereix maquinari especialitzat amb sistemes de refrigeració líquida, carcasses resistents i protecció contra vibracions.

Un exemple és el desplegament de CPD en bases militars situades en deserts o regions polars.

### 3.1 Casos pràctics i exemples reals

L’elecció del maquinari correcte no és una qüestió teòrica, sinó que té aplicacions pràctiques en diversos sectors. A continuació, es presenten alguns exemples:

- **Google Data Centers**: Utilitzen intel·ligència artificial per optimitzar el consum energètic i gestionar automàticament la refrigeració dels seus servidors.
- **NASA**: Gestiona enormes quantitats de dades provinents de satèl·lits i missions espacials mitjançant supercomputadors especialitzats en càlcul científic.
- **Banca internacional**: Les entitats financeres utilitzen sistemes amb alts estàndards de seguretat i duplicació de dades per garantir la integritat de les transaccions.

---

# **Components de Maquinari en un CPD a una empresa (Centre de Processament de Dades)**

Els Centres de Processament de Dades (CPD) són infraestructures essencials per a les empreses, encarregades d’emmagatzemar, processar i distribuir informació de manera eficient. Per garantir eficiència, seguretat i escalabilitat, utilitzen components de maquinari específics. A continuació, veurem en detall els elements fonamentals.

---

## **1. Servidors i Processadors d’Alt Rendiment**

Els servidors són els ordinadors especialitzats que gestionen les aplicacions i dades d’una empresa. Estan dissenyats per funcionar 24/7 i suportar càrregues de treball elevades.

### **Components principals d’un servidor:**
1. **Processador (CPU - Central Processing Unit):**  
   - És el cervell del servidor.  
   - Exemples: Intel Xeon, AMD EPYC.  
   - Optimitzat per múltiples fils d’execució simultanis.  
   - Inclou tecnologies com virtualització i multithreading per gestionar moltes tasques alhora.  

2. **Memòria RAM (Random Access Memory):**  
   - Emmagatzema informació temporal mentre el servidor processa les dades.  
   - Tipus més usat: RAM ECC (Error-Correcting Code), que corregeix errors automàticament per evitar fallades crítiques.  

3. **Placa base (Motherboard):**  
   - Connecta tots els components del servidor.  
   - Inclou ranures d’expansió PCIe per targetes de xarxa i emmagatzematge d’alt rendiment.  

4. **Fonts d’alimentació redundants:**  
   - Eviten fallades per talls elèctrics.  
   - Es poden substituir en calent sense apagar el servidor.  

5. **Xassís i sistema de refrigeració:**  
   - Carcassa dissenyada per una ventilació òptima.  
   - Pot incloure refrigeració líquida en servidors d’alt rendiment.  

Exemple d’ús: Un servidor d’una empresa de comerç electrònic processa milers de transaccions per segon, assegurant-se que el web funcioni sense interrupcions.

---

## **2. Sistemes d’Emmagatzematge**

Els CPD gestionen grans quantitats de dades i necessiten sistemes d’emmagatzematge ràpids i segurs.

### **Tipus de discos d’emmagatzematge:**
1. **HDD (Hard Disk Drive):**  
   - Dispositius mecànics tradicionals.  
   - Major capacitat d’emmagatzematge a un cost menor.  
   - Més lents que els SSD.  

2. **SSD (Solid State Drive):**  
   - No tenen parts mòbils, més velocitat i durabilitat.  
   - Ideals per a bases de dades i sistemes operatius crítics.  
   - SSD NVMe: Format més ràpid, es connecta per PCIe en lloc de SATA.  

3. **RAID (Redundant Array of Independent Disks):**  
   - Combina diversos discos per millorar rendiment i seguretat.  
   - Exemples:  
     - RAID 0 (més velocitat, sense redundància).  
     - RAID 1 (mirall: còpia exacta dels discos).  
     - RAID 5/6/10 (combinació de velocitat i redundància).  

### **Tipus d’arquitectures d’emmagatzematge:**
1. **DAS (Direct Attached Storage):**  
   - Emmagatzematge connectat directament a un servidor.  
   - Sense xarxa compartida.  
   - Exemple: Un disc SSD instal·lat dins d’un servidor.  

2. **NAS (Network Attached Storage):**  
   - Sistema d’emmagatzematge connectat a la xarxa.  
   - Accessible per múltiples servidors i dispositius.  
   - Exemple: Un servidor de fitxers en una empresa.  

3. **SAN (Storage Area Network):**  
   - Xarxa d’alta velocitat dedicada a emmagatzematge.  
   - Ús empresarial, permet accés ràpid i escalabilitat.  
   - Exemple: Data Centers que gestionen grans bases de dades.  

Exemple d’ús: Un banc necessita un sistema SAN amb RAID per garantir que les dades dels comptes es repliquin en diversos servidors i mai es perdin per una fallada.

---

## **3. Infraestructura de Xarxa d’Alt Rendiment**

La xarxa d’un CPD connecta els servidors entre si i amb els usuaris finals. Una infraestructura de xarxa deficient pot provocar col·lapses i retards en la transmissió de dades.

### **Components principals d’una xarxa en un CPD:**
1. **Encaminadors (Routers):**  
   - Gestionen el trànsit de dades entre xarxes internes i externes.  
   - Exemple: Un encaminador que connecta la xarxa d’un CPD a Internet.  

2. **Commutadors (Switches):**  
   - Connecten dispositius dins de la mateixa xarxa.  
   - Tipus:
     - Switch Layer 2: Assigna connexions entre dispositius dins de la mateixa xarxa.  
     - Switch Layer 3: Pot prendre decisions de xarxa més avançades (ruting).  

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

Exemple d’ús: Un servei de streaming de vídeo com Netflix necessita un balancejador de càrrega per garantir que milions d’usuaris puguin accedir als seus vídeos sense retards.

---

# **Resum per la Pissarra**
**1. Servidors i Processadors**
   - CPU (Intel Xeon, AMD EPYC): Execució eficient de processos.  
   - RAM ECC: Evita errors de memòria.  
   - Fonts d’alimentació redundants: Prevenció de fallades elèctriques.  
   - Refrigeració (aire/líquid): Manté la temperatura òptima.  

**2. Sistemes d’Emmagatzematge**
   - HDD (més capacitat), SSD NVMe (més velocitat).  
   - RAID: Redundància i seguretat de dades.  
   - DAS, NAS, SAN: Diferents maneres d’organitzar l’emmagatzematge.  

**3. Infraestructura de Xarxa**
   - Encaminadors: Connecten xarxes.  
   - Switches: Interconnecten servidors.  
   - Firewalls: Protecció contra atacs.  
   - Balancejadors de càrrega: Reparteixen el trànsit.  
   - Fibra òptica: Connexió d’alta velocitat.  



