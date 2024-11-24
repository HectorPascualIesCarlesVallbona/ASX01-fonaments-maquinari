# 4. Implantació de maquinari en centres de processament de dades (CPD)

## Índex

- [4. Implantació de maquinari en centres de processament de dades (CPD)](#4-implantació-de-maquinari-en-centres-de-processament-de-dades-cpd)
  - [Índex](#índex)
    - [4.1 Arquitectura d’ordinadors personals, sistemes departamentals i grans ordinadors](#41-arquitectura-dordinadors-personals-sistemes-departamentals-i-grans-ordinadors)
      - [**Ordinadors personals (PC):**](#ordinadors-personals-pc)
      - [**Sistemes departamentals (servidors):**](#sistemes-departamentals-servidors)
      - [**Grans ordinadors (mainframes):**](#grans-ordinadors-mainframes)
    - [4.2 Estructura d’un CPD. Organització](#42-estructura-dun-cpd-organització)
      - [**Components físics principals:**](#components-físics-principals)
      - [**Organització funcional:**](#organització-funcional)
    - [4.3 Seguretat física](#43-seguretat-física)
      - [**Aspectes clau de la seguretat física:**](#aspectes-clau-de-la-seguretat-física)
    - [4.4 Components específics en solucions empresarials: bastidors o racks, dispositius de connexió en calent, discos, fonts d’alimentació, control remot](#44-components-específics-en-solucions-empresarials-bastidors-o-racks-dispositius-de-connexió-en-calent-discos-fonts-dalimentació-control-remot)
      - [**Bastidors o racks:**](#bastidors-o-racks)
      - [**Dispositius de connexió en calent (hot-swap):**](#dispositius-de-connexió-en-calent-hot-swap)
      - [**Discos durs i SSD:**](#discos-durs-i-ssd)
      - [**Fonts d’alimentació redundants:**](#fonts-dalimentació-redundants)
      - [**Control remot:**](#control-remot)
    - [4.5 Arquitectures d’alta disponibilitat](#45-arquitectures-dalta-disponibilitat)
      - [**Conceptes bàsics d’alta disponibilitat:**](#conceptes-bàsics-dalta-disponibilitat)
      - [**Clústers de servidors:**](#clústers-de-servidors)
      - [**Redundància de xarxa:**](#redundància-de-xarxa)
      - [**Balanceig de càrrega:**](#balanceig-de-càrrega)
    - [4.6 Inventariat de maquinari](#46-inventariat-de-maquinari)
      - [**Sistemes d'inventari automatitzats:**](#sistemes-dinventari-automatitzats)
      - [**Seguiment del cicle de vida del maquinari:**](#seguiment-del-cicle-de-vida-del-maquinari)
      - [**Inventariat de maquinari crític:**](#inventariat-de-maquinari-crític)

---

### 4.1 Arquitectura d’ordinadors personals, sistemes departamentals i grans ordinadors

L'arquitectura del maquinari utilitzat en els centres de processament de dades varia significativament segons el tipus de sistema utilitzat. Els tres tipus principals són els ordinadors personals (PC), els sistemes departamentals i els grans ordinadors o mainframes. Cadascun d’aquests sistemes està dissenyat per servir funcions específiques dins d’un CPD.

#### **Ordinadors personals (PC):**

Els ordinadors personals són sistemes informàtics individuals que sovint es fan servir com a estacions de treball en entorns d’oficina o per a tasques computacionals menors dins d’un CPD. Malgrat això, quan es combinen en grans quantitats, els PC poden formar clústers de còmput altament potents, una pràctica habitual en entorns de computació distribuïda o processament massiu de dades, com en projectes de *big data* o recerca científica.

**Característiques tècniques:**

- Processadors de gamma mitjana o alta, normalment basats en arquitectura x86 o ARM.
- Capacitats de memòria i emmagatzematge limitades en comparació amb servidors dedicats.
- Interfícies d’usuari gràfiques, sovint amb sistemes operatius com Windows, macOS o distribucions Linux.
- En clústers, poden ser controlats remotament per maximitzar el rendiment computacional.

**Exemples d’ús:**
Els PC són utilitzats freqüentment en entorns de CPD com a nodes de càlcul en projectes de computació distribuïda o com a terminals d'accés per al personal tècnic. Un exemple destacat és el projecte SETI@home, que utilitza ordinadors personals arreu del món per analitzar dades astronòmiques en busca de senyals d’intel·ligència extraterrestre.

#### **Sistemes departamentals (servidors):**

Els servidors departamentals estan dissenyats per manejar múltiples sol·licituds simultànies i oferir serveis a un gran nombre d’usuaris o sistemes connectats. Aquests servidors solen estar dissenyats per funcionar de manera contínua, amb redundància integrada i capacitats d’administració remota.

**Característiques tècniques:**

- Processadors de gamma alta, sovint amb múltiples nuclis i fils d’execució.
- Gran capacitat de memòria (RAM), sovint amb suport per a memòries ECC (Error-Correcting Code) per garantir la fiabilitat.
- Suport per a unitats de disc d’alt rendiment, com ara discs SSD NVMe, RAID per a redundància i emmagatzematge escalable.
- Capacitat per a virtualització, permetent que un servidor físic allotgi múltiples màquines virtuals (VM).

**Exemples d’ús:**
Aquests servidors són utilitzats habitualment per proporcionar serveis de bases de dades, correu electrònic, emmagatzematge de fitxers, o com a servidors d’aplicacions empresarials (ERP). Els sistemes departamentals són fonamentals en petites i mitjanes empreses, on les seves necessitats són més grans que les que pot oferir un PC però menors que les que gestionen els mainframes.

#### **Grans ordinadors (mainframes):**

Els mainframes són màquines dissenyades per a la gestió de grans volums de transaccions i dades. La seva robustesa i capacitat per oferir disponibilitat contínua els fan indispensables en sectors com el bancari, assegurador o governamental, on qualsevol interrupció del servei pot tenir conseqüències catastròfiques.

**Característiques tècniques:**

- Arquitectures dissenyades específicament per suportar milions de transaccions per segon.
- Gran escalabilitat, permetent afegir recursos sense interrupcions.
- Capacitats de redundància total en components clau (fonts d’alimentació, processadors, memòria, discos).
- Sistemes operatius especialment dissenyats, com z/OS, que poden gestionar milers de processos concurrents sense comprometre el rendiment.

**Exemples d’ús:**
Els mainframes són utilitzats per institucions financeres com bancs, que confien en aquests sistemes per gestionar milions de transaccions diàries de manera segura i fiable. Un altre exemple és la indústria del transport aeri, on sistemes com el SITA Passenger Service System confien en mainframes per gestionar les reserves de vols i mantenir la continuïtat de les operacions.

**Referències externes:**

- [IBM Z Architecture Overview](https://www.ibm.com/it-infrastructure/z/capabilities)
- [Intel Processor Overview](https://www.intel.com/content/www/us/en/products/processors/core.html)

---

### 4.2 Estructura d’un CPD. Organització

La infraestructura i organització d’un CPD és crucial per assegurar-ne el funcionament eficient i segur. Un CPD ben dissenyat proporciona una estructura flexible que permet el creixement, la gestió eficient de l’energia, la refrigeració i la seguretat, tant a nivell físic com lògic.

#### **Components físics principals:**

1. **Sales de servidors:** Aquestes sales són el cor d’un CPD. En elles s’instal·len els racks que allotgen els servidors, sistemes d'emmagatzematge i altres dispositius de xarxa. És fonamental que aquestes sales estiguin dissenyades per a un fàcil accés i manteniment, així com per a la màxima eficiència de refrigeració.

   **Exemple:** En grans centres de dades, com els de Google o Amazon, els servidors estan organitzats en files dins de racks de 42U o més, on cada unitat (U) és una ranura de 1.75 polzades d'alçada. Això permet allotjar nombrosos dispositius en un espai reduït.

2. **Sales de refrigeració:** Els sistemes de refrigeració són essencials per mantenir els equips a la temperatura òptima. Una temperatura inadequada pot reduir la vida útil dels components o fins i tot causar fallades immediates. Sovint es fan servir sistemes d’aire condicionat industrial o refrigeració líquida.

   **Exemple:** Centres de dades com el de Facebook a Suècia utilitzen l'aire fred natural del clima local per refrigerar els seus servidors, una tècnica coneguda com a *free cooling*. Això redueix dràsticament els costos energètics.

3. **Sales elèctriques:** Les sales d’energia alberguen fonts d’alimentació ininterrompuda (UPS) i generadors, que asseguren la disponibilitat d’energia fins i tot en cas de fallada elèctrica. La redundància en aquests sistemes és fonamental per evitar qualsevol interrupció en el servei.

   **Exemple:** En els centres de dades d'Amazon, els generadors dièsel poden subministrar energia durant hores en cas d’interrupció prolongada, mentre que els UPS de bateria garanteixen la continuïtat del servei durant els primers moments d'una fallada.

4. **Zones de suport:** A més de les sales de servidors i energia, els CPDs tenen zones dedicades a suport tècnic, àrees d’oficines, i sales per a la monitorització de sistemes (NOC - Network Operations Center). En aquestes àrees, els tècnics poden supervisar els sistemes en temps real i gestionar incidents de manera ràpida i eficient.

#### **Organització funcional:**

1. **Divisió en zones:** Un CPD sovint es divideix en zones per tal de segmentar les funcions crítiques dels equips. Aix

ò inclou la separació física dels servidors en funció de la seva funció (servidors de base de dades, servidors web, emmagatzematge, etc.). Aquesta segmentació també facilita l'administració i el manteniment.

   **Exemple:** En CPDs grans com els de Microsoft Azure, els servidors es classifiquen en grups que ofereixen serveis específics, com ara servidors de bases de dades, computació, emmagatzematge, i processament de dades en temps real.

2. **Redundància geogràfica:** Els centres de processament de dades crítics sovint estan distribuïts en múltiples ubicacions geogràfiques per assegurar la continuïtat de les operacions fins i tot en cas de desastres naturals o altres esdeveniments disruptius. Això es coneix com a redundància geogràfica.

   **Exemple:** Netflix utilitza múltiples centres de dades geogràficament dispersos per garantir que els seus serveis estiguin disponibles globalment. Aquesta estratègia assegura que si un CPD es veu afectat, els serveis continuen funcionant des d'un altre CPD.

**Referències externes:**

- [Data Center Infrastructure Efficiency Best Practices](https://uptimeinstitute.com/)
- [ASHRAE Guidelines for Data Center Cooling](https://www.ashrae.org/)

---

### 4.3 Seguretat física

La seguretat física és un aspecte crucial en la gestió d'un CPD. La seva finalitat és garantir la protecció dels equips i les dades contra accessos no autoritzats, desastres naturals, i altres amenaces externes. La seguretat física no només inclou la protecció contra atacs externs, sinó també la protecció contra fallades internes, incendis i altres incidents que poden comprometre la integritat dels equips.

#### **Aspectes clau de la seguretat física:**

1. **Control d’accés:**
El primer nivell de seguretat en qualsevol CPD és el control d’accés. Només el personal autoritzat ha de tenir permís per accedir a les sales on es troben els servidors i altres components crítics. Sovint es fa servir un sistema d'autenticació multifactor, que combina targetes d’identificació (RFID) amb claus d’accés o biometria com la lectura d’empremtes dactilars o el reconeixement facial.

   **Exemple:** A les instal·lacions de Google, per accedir a les zones més crítiques dels seus CPDs, el personal ha de passar per múltiples capes de seguretat, incloent escàners d’empremtes dactilars i càmeres de seguretat amb reconeixement facial.

2. **Sistemes de videovigilància i enregistrament:**
Els CPDs solen estar equipats amb sistemes de videovigilància en temps real, amb càmeres que enregistren les zones crítiques, els accessos, i les sales de servidors. Aquestes càmeres estan monitoritzades 24/7 per personal especialitzat en seguretat.

   **Exemple:** Microsoft Azure utilitza càmeres amb intel·ligència artificial (IA) per identificar comportaments inusuals, com moviments no autoritzats o anomalies en els patrons d'accés.

3. **Protecció contra incendis:**
Els CPDs estan equipats amb sistemes avançats de detecció i extinció d’incendis. La detecció primerenca de fum és essencial, ja que un incendi en una sala de servidors pot causar danys catastròfics. A més, sovint es fan servir sistemes de supressió d’incendis basats en gasos inerts (com el FM-200 o Novec 1230) que permeten sufocar les flames sense danyar els equips electrònics.

   **Exemple:** El centre de dades de Facebook a Luleå, Suècia, utilitza un sistema de supressió d'incendis amb gas inert per protegir els servidors de danys causats per l’aigua o altres materials extintors més invasius.

4. **Sistemes de control ambiental:**
Les sales de servidors han de mantenir condicions ambientals òptimes per evitar el sobreescalfament dels equips i garantir-ne la longevitat. Els sensors de temperatura i humitat monitoritzen constantment les condicions, i els sistemes de refrigeració s’ajusten automàticament per mantenir les temperatures ideals.

   **Exemple:** Centres de dades com els de AWS utilitzen sistemes de control ambiental que no només monitoritzen la temperatura i la humitat, sinó que també regulen la pressió de l'aire per optimitzar el flux d’aire dins de les sales de servidors.

**Referències externes:**

- [Physical Security Standards for Data Centers - NIST](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
- [Data Center Fire Suppression Overview](https://www.fmglobal.com/research-and-resources)

---

### 4.4 Components específics en solucions empresarials: bastidors o racks, dispositius de connexió en calent, discos, fonts d’alimentació, control remot

Un CPD està format per una sèrie de components específics dissenyats per maximitzar l'eficiència, la flexibilitat i la fiabilitat del centre. Aquests components estan optimitzats per a entorns empresarials on el rendiment i la disponibilitat contínua són essencials.

#### **Bastidors o racks:**

Els bastidors o racks són estructures metàl·liques que permeten allotjar diversos servidors, dispositius d’emmagatzematge i altres components. Els racks estan dissenyats segons l'estàndard de 19 polzades, i poden tenir diferents altures, normalment mesurades en unitats (U), amb una U equivalent a 1.75 polzades d'alçada.

**Exemple:** Els racks de Dell PowerEdge poden allotjar des de servidors fins a solucions d'emmagatzematge SAN (Storage Area Network) en un únic rack, optimitzant l'espai físic dins de la sala de servidors.

#### **Dispositius de connexió en calent (hot-swap):**

Els dispositius de connexió en calent permeten la substitució de components com discs durs, fonts d'alimentació o targetes de xarxa sense necessitat d'apagar el sistema. Aquesta capacitat és essencial per mantenir la disponibilitat contínua del sistema.

**Exemple:** Els sistemes RAID (Redundant Array of Independent Disks) permeten afegir o substituir discos durs en calent, mantenint la integritat del sistema d'emmagatzematge sense interrupcions.

#### **Discos durs i SSD:**

Els discos durs (HDD) i les unitats d'estat sòlid (SSD) són els dos tipus principals d'emmagatzematge utilitzats en CPDs. Els SSD són més ràpids i tenen temps de resposta més baixos que els HDD tradicionals, cosa que els fa ideals per a aplicacions d'alt rendiment. Els HDD, per contra, ofereixen una major capacitat d'emmagatzematge per unitat de cost, cosa que els fa útils per a emmagatzematge a llarg termini o arxiu de dades.

**Exemple:** Els CPDs de Dropbox utilitzen una combinació de discos SSD per al processament d’arxius actius i discos durs tradicionals per a l’arxiu de dades menys utilitzades.

#### **Fonts d’alimentació redundants:**

Les fonts d’alimentació redundants són sistemes dissenyats per assegurar que, en cas de fallada d'una font, una altra pugui prendre el relleu sense interrompre el funcionament del sistema. Aquestes fonts poden ser reemplaçades en calent, cosa que permet que el sistema continuï funcionant sense necessitat de ser apagat.

**Exemple:** Els servidors empresarials de HPE ProLiant integren fonts d'alimentació redundants que es poden substituir en calent, assegurant que fins i tot si una font falla, el servidor continua funcionant sense interrupcions.

#### **Control remot:**

Els sistemes de control remot com l’IPMI (Intelligent Platform Management Interface) o Dell iDRAC (Integrated Dell Remote Access Controller) permeten als administradors gestionar els servidors de forma remota. Això inclou la capacitat de reiniciar servidors, supervisar-ne el rendiment, i realitzar diagnòstics sense necessitat d'accés físic al servidor.

**Exemple:** A les instal·lacions d'Amazon Web Services (AWS), els enginyers poden administrar milers de servidors distribuïts geogràficament gràcies a les capacitats d’administració remota de sistemes com iDRAC.

**Referències externes:**

- [Dell PowerEdge Rack Systems](https://www.dell.com/en-us/shop/rack-servers/sr/rack-servers)
- [HPE Hot-Swap Components Overview](https://www.hpe.com/us/en/solutions/data-center-infrastructure.html)

---

### 4.5 Arquitectures d’alta disponibilitat

Les arquitectures d'alta disponibilitat (HA) són fon

amentals en un CPD per assegurar que els serveis crítics estiguin disponibles fins i tot en cas de fallades del sistema o interrupcions imprevistes. Aquests sistemes estan dissenyats per minimitzar el temps d'inactivitat i garantir la continuïtat del servei.

#### **Conceptes bàsics d’alta disponibilitat:**

L'alta disponibilitat es defineix com la capacitat d'un sistema per funcionar durant un llarg període de temps sense interrupcions significatives. Els sistemes HA es caracteritzen per redundància en els components crítics, de manera que si un component falla, un altre pugui prendre immediatament el relleu.

**Exemple:** Sistemes de gestió de bases de dades com MySQL i PostgreSQL sovint s'executen en arquitectures HA mitjançant replicació de dades i configuració de clústers, assegurant que si un node falla, un altre pot continuar oferint el servei sense interrupcions.

#### **Clústers de servidors:**

Un dels elements centrals de l'alta disponibilitat és l'ús de clústers de servidors. En una arquitectura de clúster, diversos servidors estan configurats per treballar junts de manera que, si un servidor falla, els altres poden assumir-ne la càrrega de treball.

**Exemple:** En el sistema de pagaments en línia de PayPal, els servidors estan configurats en clústers distribuïts geogràficament per garantir la continuïtat del servei a escala global. Aquesta arquitectura assegura que els usuaris no experimentin interrupcions fins i tot si hi ha fallades a escala regional.

#### **Redundància de xarxa:**

Un altre aspecte clau de les arquitectures HA és la redundància de xarxa. Això implica tenir múltiples connexions a internet o xarxes internes, així com l'ús de commutadors i encaminadors redundants que poden assumir immediatament la funció d'un dispositiu fallit.

**Exemple:** En els centres de dades d’Azure, cada servidor té múltiples connexions a la xarxa per garantir que, si un enllaç de xarxa falla, la connexió pugui continuar per una ruta alternativa sense que els usuaris notin cap interrupció.

#### **Balanceig de càrrega:**

El balanceig de càrrega és una altra tècnica important en les arquitectures HA. El balanceig de càrrega distribueix les sol·licituds d'usuari entre diversos servidors per evitar sobrecàrregues i garantir que cap servidor es vegi aclaparat per massa sol·licituds.

**Exemple:** Amazon Elastic Load Balancer és una solució que distribueix el trànsit de xarxa entre múltiples servidors EC2 per assegurar que cap servidor estigui sobrecarregat, maximitzant la disponibilitat del servei.

**Referències externes:**

- [Cisco High Availability Architectures](https://www.cisco.com/)
- [Redundancy and Load Balancing Best Practices - AWS](https://aws.amazon.com/architecture/)

---

### 4.6 Inventariat de maquinari

La gestió del maquinari en un CPD és un procés crític per garantir que tots els recursos estan disponibles, en bon estat i correctament configurats. Un bon sistema d’inventariat permet identificar, supervisar i mantenir tot l'equipament físic dins del CPD, cosa que facilita les tasques de manteniment i planificació d’actualitzacions.

#### **Sistemes d'inventari automatitzats:**

En un CPD modern, el seguiment manual del maquinari és ineficient i propens a errors. És per això que molts centres de dades utilitzen eines automatitzades per gestionar l'inventari de maquinari, com ara Ansible, Puppet, o Microsoft SCCM (System Center Configuration Manager). Aquestes eines permeten registrar automàticament tots els dispositius, controlar-ne la configuració, i fer-ne seguiment al llarg del seu cicle de vida.

**Exemple:** Netflix utilitza Puppet per gestionar el seu inventari de maquinari, assegurant que tots els servidors estan correctament configurats i que qualsevol incidència es pot detectar i corregir de manera immediata.

#### **Seguiment del cicle de vida del maquinari:**

Un cop un component és registrat en el sistema d’inventariat, se li assigna un cicle de vida que inclou etapes com la instal·lació, manteniment preventiu, i eventualment la seva substitució o eliminació. Això permet que els equips tècnics puguin planificar amb antelació el manteniment o les actualitzacions, evitant interrupcions inesperades.

**Exemple:** Google utilitza un sistema de seguiment del cicle de vida del maquinari que monitora el rendiment dels servidors i en recomana la substitució abans que experimentin fallades que puguin afectar el servei.

#### **Inventariat de maquinari crític:**

A més del seguiment general del maquinari, els CPDs sovint mantenen un inventari separat dels components crítics, com les fonts d’alimentació, discs durs i unitats SSD de substitució. Això assegura que, en cas de fallada, els components puguin ser substituïts immediatament sense necessitat d'esperar subministraments externs.

**Exemple:** En els centres de dades de Facebook, es manté un inventari de components crítics a cada centre, assegurant que qualsevol fallada pugui ser corregida en menys d'una hora gràcies a la disponibilitat immediata de peces de recanvi.

**Referències externes:**

- [IT Asset Management Systems - Ansible](https://www.ansible.com/)
- [System Center Configuration Manager Overview](https://www.microsoft.com/en-us/microsoft-365/system-center)
