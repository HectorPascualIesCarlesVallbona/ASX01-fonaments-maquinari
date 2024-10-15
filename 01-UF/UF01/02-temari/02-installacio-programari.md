# Instal·lació de programari d’utilitat i propòsit general per a un sistema informàtic

[Link del temari a moodle](https://moodle.iescarlesvallbona.cat/course/view.php?id=1060&section=4)

[PDF instal.lació, configuració i recuperació programari](https://moodle.iescarlesvallbona.cat/pluginfile.php/185523/mod_resource/content/1/fp_asix_m05_u2_pdfindex.pdf)

[Pràctica 2 - Document amb aspectes bàsics per alumne nou](https://moodle.iescarlesvallbona.cat/pluginfile.php/186246/mod_resource/content/3/Pr%C3%A0ctica%20UF2%20part%202.pdf)

---

## Resum PDF instal.lació, configuració i recuperació programari

### Índex

2. [Instal·lació de programari d’utilitat i propòsit general per a un sistema informàtic](#2-instal·lació-de-programari-dutilitat-i-propòsit-general-per-a-un-sistema-informàtic)  
   2.1. [Entorns operatius](#21-entorns-operatius)  
   2.2. [Tipus d’aplicacions](#22-tipus-daplicacions)  
   2.3. [Instal·lació i proves d’aplicació](#23-instal·lació-i-proves-daplicació)  
   2.4. [Necessitats dels entorns d’explotació](#24-necessitats-dels-entorns-dexplotació)  
   2.5. [Requeriments de les aplicacions](#25-requeriments-de-les-aplicacions)  
   2.6. [Comparació d’aplicacions. Avaluació i rendiment](#26-comparació-daplicacions-avaluació-i-rendiment)  
   2.7. [Programari de propòsit general](#27-programari-de-propòsit-general)  
   2.8. [Utilitats](#28-utilitats)

3. [Creació d’imatges de programari. Suport del programari bàsic d’un sistema](#3-creació-dimatges-de-programari-suport-del-programari-bàsic-dun-sistema)  
   3.1. [Partició de disc](#31-partició-de-disc)  
   3.2. [Imatges de suport](#32-imatges-de-suport)  
   3.3. [Opcions d’arrencada d’un sistema](#33-opcions-darrencada-dun-sistema)  
   3.4. [Creació d’imatges](#34-creació-dimatges)  
   3.5. [Recuperació d’imatges](#35-recuperació-dimatges)

4. [Implantació de maquinari en centres de processament de dades (CPD)](#4-implantació-de-maquinari-en-centres-de-processament-de-dades-cpd)  
   4.1. [Arquitectura d’ordinadors personals, sistemes departamentals i grans ordinadors](#41-arquitectura-dordinadors-personals-sistemes-departamentals-i-grans-ordinadors)  
   4.2. [Estructura d’un CPD. Organització](#42-estructura-dun-cpd-organització)  
   4.3. [Seguretat física](#43-seguretat-física)  
   4.4. [Components específics en solucions empresarials](#44-components-específics-en-solucions-empresarials)  
   4.5. [Arquitectures d’alta disponibilitat](#45-arquitectures-dalta-disponibilitat)  
   4.6. [Inventariat de maquinari](#46-inventariat-de-maquinari)

5. [Compliment de les normes de prevenció de riscos laborals i protecció ambiental](#5-compliment-de-les-normes-de-prevenció-de-riscos-laborals-i-protecció-ambiental)  
   5.1. [Identificació de riscos](#51-identificació-de-riscos)  
   5.2. [Determinació de les mesures de prevenció de riscos](#52-determinació-de-les-mesures-de-prevenció-de-riscos)  
   5.3. [Prevenció de riscos laborals en els processos de muntatge i manteniment](#53-prevenció-de-riscos-laborals-en-els-processos-de-muntatge-i-manteniment)  
   5.4. [Equips de protecció individual](#54-equips-de-protecció-individual)  
   5.5. [Compliment de la normativa de prevenció de riscos laborals](#55-compliment-de-la-normativa-de-prevenció-de-riscos-laborals)  
   5.6. [Compliment de la normativa de protecció ambiental](#56-compliment-de-la-normativa-de-protecció-ambiental)

---

### 2. Instal·lació de programari d’utilitat i propòsit general per a un sistema informàtic

#### 2.1 Entorns operatius

Els entorns operatius són l’entorn de base sobre el qual s’executa tot el programari d’un sistema. Els més comuns són:

- **Sistemes operatius d’escriptori:** Windows, macOS, Linux. Utilitzats per a treballs d'ofimàtica, multimèdia, i programació.
- **Sistemes operatius de servidor:** Windows Server, Ubuntu Server, Red Hat Enterprise Linux. Utilitzats per a la gestió de recursos compartits, servidors de correu, servidors web, etc.

#### 2.2 Tipus d’aplicacions

Les aplicacions poden ser **d'escriptori** o **web**:

- **Aplicacions d'escriptori:** Les que s'instal·len en el sistema operatiu d'un ordinador, com Microsoft Office, Adobe Photoshop.
- **Aplicacions web:** Aplicacions que es poden accedir via navegador, com Google Docs o Slack, sense necessitat d'instal·lació local.

#### 2.3 Instal·lació i proves d’aplicació

- **Instal·lació:** Els administradors poden utilitzar gestors de paquets com APT (per a Linux) o MSI/EXE (per a Windows) per instal·lar programari.
- **Proves d'aplicació:** Inclouen la verificació de compatibilitat amb el maquinari, funcionalitat, rendiment i estabilitat. Per exemple, una aplicació de disseny CAD s'hauria de provar en diversos sistemes operatius per garantir que funcioni eficientment.

#### 2.4 Necessitats dels entorns d’explotació

Els entorns de producció requereixen eines de monitorització, seguretat reforçada i escalabilitat. En un entorn de servidor, es pot utilitzar programari com **Nagios** o **Zabbix** per monitoritzar els recursos del sistema i detectar possibles problemes.

#### 2.5 Requeriments de les aplicacions

Les aplicacions poden tenir requeriments de maquinari (memòria RAM, CPU, espai en disc) i requeriments de programari (versions de biblioteques o altres dependències).  
Exemple: **Adobe Photoshop** requereix almenys 8 GB de RAM i una CPU compatible amb SSE4.2 per a la seva instal·lació.

#### 2.6 Comparació d’aplicacions. Avaluació i rendiment

És important comparar aplicacions segons el seu rendiment, compatibilitat i facilitat d'ús. Un exemple és comparar **Microsoft Office** i **LibreOffice**. Es poden fer proves de rendiment mesurant el temps de resposta de cada suite en obrir arxius grans o executar tasques repetitives.

#### 2.7 Programari de propòsit general

Inclou eines d’ofimàtica (Microsoft Office, Google Workspace), aplicacions per a documentació electrònica (PDF), programes de disseny (Autodesk AutoCAD), i programari multimèdia (Adobe Creative Suite). També inclou programari a mida desenvolupat per empreses per a necessitats específiques.

#### 2.8 Utilitats

Les utilitats són eines complementàries per a la gestió i optimització del sistema:

- **Compressors:** com **WinRAR** o **7-Zip** per reduir la mida d'arxius.
- **Monitoratge de sistema:** com **Task Manager** (Windows) o **htop** (Linux) per supervisar l'ús de CPU, memòria, i disc.
- **Gestió de discos:** com **Partition Magic** o **GParted** per crear, modificar o eliminar particions.
- **Seguretat:** com antivirus (Windows Defender, Avast), tallafocs (pfSense), i antiespies (Malwarebytes).

---

### 3. Creació d’imatges de programari. Suport del programari bàsic d’un sistema

#### 3.1 Partició de disc

Consisteix a dividir un disc dur en seccions independents per gestionar millor els recursos o instal·lar múltiples sistemes operatius.  
Exemple: En un servidor es poden crear particions separades per al sistema operatiu, els registres i les dades d'usuari.

#### 3.2 Imatges de suport

Una imatge de disc és una còpia completa d'un sistema, incloent el sistema operatiu i les aplicacions instal·lades. Això permet crear còpies de seguretat o desplegar el sistema en altres equips de manera ràpida.

#### 3.3 Opcions d’arrencada d’un sistema

Les opcions d’arrencada inclouen arrencada des de disc dur, xarxa, o unitat USB. Aquestes opcions són útils

 per a la recuperació o la instal·lació d’un nou sistema operatiu.

#### 3.4 Creació d’imatges

La creació d’imatges pot fer-se amb eines com **Clonezilla** o **Norton Ghost**, que permeten copiar tot el contingut d’un disc dur per ser usat en altres equips.

#### 3.5 Recuperació d’imatges

Les imatges de disc es poden restaurar en cas de fallada del sistema, permetent recuperar el sistema operatiu i els programes tal com estaven quan es va fer la imatge.

---

### 4. Implantació de maquinari en centres de processament de dades (CPD)

#### 4.1 Arquitectura d’ordinadors personals, sistemes departamentals i grans ordinadors

La implementació de maquinari inclou des d’ordinadors personals fins a grans sistemes de processament de dades, dissenyats per gestionar volums importants d'informació en entorns empresarials.

#### 4.2 Estructura d’un CPD. Organització

Un CPD (Centre de Processament de Dades) està estructurat amb servidors, emmagatzematge i xarxes, dissenyats per a alta disponibilitat i seguretat. Aquests centres poden estar organitzats en sales amb sistemes de refrigeració i seguretat.

#### 4.3 Seguretat física

La seguretat física en un CPD inclou sistemes d’alarma, vigilància, i control d’accés per evitar accessos no autoritzats als servidors i altres dispositius.

#### 4.4 Components específics en solucions empresarials

Els CPDs utilitzen components especials com **racks**, dispositius de connexió en calent, discos durs per a emmagatzematge massiu, fonts d’alimentació redundants i control remot per a monitorització.

#### 4.5 Arquitectures d’alta disponibilitat

Inclou configuracions amb **clústers** i **balançadors de càrrega** per assegurar que els serveis continuïn funcionant en cas de fallades en part dels sistemes.

#### 4.6 Inventariat de maquinari

L’inventariat permet fer un seguiment del maquinari en un CPD, amb informació detallada sobre cada component, la seva ubicació i estat actual.

---

### 5. Compliment de les normes de prevenció de riscos laborals i protecció ambiental

#### 5.1 Identificació de riscos

Es tracta d'identificar riscos associats amb les tasques de manteniment de maquinari, com ara riscos elèctrics, ergonomia i manipulació de pes.

#### 5.2 Determinació de les mesures de prevenció de riscos

Inclou mesures per minimitzar els riscos, com la correcta manipulació d’equips i l’ús d’eines de protecció adequades.

#### 5.3 Prevenció de riscos laborals en els processos de muntatge i manteniment

Són pràctiques segures a seguir en tasques de muntatge i manteniment, com desconnectar l’equip de la xarxa elèctrica abans de manipular components interns.

#### 5.4 Equips de protecció individual

Inclou elements com guants, ulleres de protecció, i roba adequada per a tasques de manteniment de maquinari.

#### 5.5 Compliment de la normativa de prevenció de riscos laborals

Les empreses han de seguir les normes establertes en la Llei de Prevenció de Riscos Laborals, que garanteixen un entorn segur per als treballadors.

#### 5.6 Compliment de la normativa de protecció ambiental

Inclou el correcte reciclatge i eliminació de components electrònics per reduir l’impacte ambiental, complint amb les normatives vigents.
