# Instal·lació de programari d’utilitat i propòsit general per a un sistema informàtic

[Link del temari a moodle](https://moodle.iescarlesvallbona.cat/course/view.php?id=1060&section=4)

[PDF instal.lació, configuració i recuperació programari](https://moodle.iescarlesvallbona.cat/pluginfile.php/185523/mod_resource/content/1/fp_asix_m05_u2_pdfindex.pdf)

[Pràctica 2 - Document amb aspectes bàsics per alumne nou](https://moodle.iescarlesvallbona.cat/pluginfile.php/186246/mod_resource/content/3/Pr%C3%A0ctica%20UF2%20part%202.pdf)

---

## Videos intro

[Inside a google Data Center](https://www.youtube.com/watch?v=XZmGGAbHqa0)

[Google Data Center Security](https://www.youtube.com/watch?v=kd33UVZhnAA)

---

## Resum PDF instal.lació, configuració i recuperació programari

### Índex

1. [Instal·lació de programari d’utilitat i propòsit general per a un sistema informàtic](#1-instal·lació-de-programari-dutilitat-i-propòsit-general-per-a-un-sistema-informàtic)  
   1.1. [Entorns operatius](#11-entorns-operatius)  
   1.2. [Tipus d’aplicacions](#12-tipus-daplicacions)  
   1.3. [Instal·lació i proves d’aplicació](#13-instal·lació-i-proves-daplicació)  
   1.4. [Necessitats dels entorns d’explotació](#14-necessitats-dels-entorns-dexplotació)  
   1.5. [Requeriments de les aplicacions](#15-requeriments-de-les-aplicacions)  
   1.6. [Comparació d’aplicacions. Avaluació i rendiment](#16-comparació-daplicacions-avaluació-i-rendiment)  
   1.7. [Programari de propòsit general](#17-programari-de-propòsit-general)  
   1.8. [Utilitats](#18-utilitats)

---

### 1. Instal·lació de programari d’utilitat i propòsit general per a un sistema informàtic

#### 1.1 Entorns operatius

Els entorns operatius són l’entorn de base sobre el qual s’executa tot el programari d’un sistema. Els més comuns són:

- **Sistemes operatius d’escriptori:** Windows, macOS, Linux. Utilitzats per a treballs d'ofimàtica, multimèdia, i programació.
- **Sistemes operatius de servidor:** Windows Server, Ubuntu Server, Red Hat Enterprise Linux. Utilitzats per a la gestió de recursos compartits, servidors de correu, servidors web, etc.

#### 1.2 Tipus d’aplicacions

Les aplicacions poden ser **d'escriptori** o **web**:

- **Aplicacions d'escriptori:** Les que s'instal·len en el sistema operatiu d'un ordinador, com Microsoft Office, Adobe Photoshop.
- **Aplicacions web:** Aplicacions que es poden accedir via navegador, com Google Docs o Slack, sense necessitat d'instal·lació local.

#### 1.3 Instal·lació i proves d’aplicació

- **Instal·lació:** Els administradors poden utilitzar gestors de paquets com APT (per a Linux) o MSI/EXE (per a Windows) per instal·lar programari.
- **Proves d'aplicació:** Inclouen la verificació de compatibilitat amb el maquinari, funcionalitat, rendiment i estabilitat. Per exemple, una aplicació de disseny CAD s'hauria de provar en diversos sistemes operatius per garantir que funcioni eficientment.

#### 1.4 Necessitats dels entorns d’explotació

Els entorns de producció requereixen eines de monitorització, seguretat reforçada i escalabilitat. En un entorn de servidor, es pot utilitzar programari com **Nagios** o **Zabbix** per monitoritzar els recursos del sistema i detectar possibles problemes.

#### 1.5 Requeriments de les aplicacions

Les aplicacions poden tenir requeriments de maquinari (memòria RAM, CPU, espai en disc) i requeriments de programari (versions de biblioteques o altres dependències).  
Exemple: **Adobe Photoshop** requereix almenys 8 GB de RAM i una CPU compatible amb SSE4.2 per a la seva instal·lació.

#### 1.6 Comparació d’aplicacions. Avaluació i rendiment

És important comparar aplicacions segons el seu rendiment, compatibilitat i facilitat d'ús. Un exemple és comparar **Microsoft Office** i **LibreOffice**. Es poden fer proves de rendiment mesurant el temps de resposta de cada suite en obrir arxius grans o executar tasques repetitives.

#### 1.7 Programari de propòsit general

Inclou eines d’ofimàtica (Microsoft Office, Google Workspace), aplicacions per a documentació electrònica (PDF), programes de disseny (Autodesk AutoCAD), i programari multimèdia (Adobe Creative Suite). També inclou programari a mida desenvolupat per empreses per a necessitats específiques.

#### 1.8 Utilitats

Les utilitats són eines complementàries per a la gestió i optimització del sistema:

- **Compressors:** com **WinRAR** o **7-Zip** per reduir la mida d'arxius.
- **Monitoratge de sistema:** com **Task Manager** (Windows) o **htop** (Linux) per supervisar l'ús de CPU, memòria, i disc.
- **Gestió de discos:** com **Partition Magic** o **GParted** per crear, modificar o eliminar particions.
- **Seguretat:** com antivirus (Windows Defender, Avast), tallafocs (pfSense), i antiespies (Malwarebytes).
