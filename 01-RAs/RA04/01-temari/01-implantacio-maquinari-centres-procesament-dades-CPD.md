# RA04 - Implantació de maquinari en centres de processament de dades (CPD)

## 0. Index
- [1. Introducció als Centres de Processament de Dades (CPD)](#1-introduccio-als-centres-de-processament-de-dades-cpd)
  - [1.1 Definició i funcions principals d'un CPD](#11-definicio-i-funcions-principals-dun-cpd)
  - [1.2 Tipologies de CPD](#12-tipologies-de-cpd)
  - [1.3 Tendències actuals en la gestió de CPD](#13-tendencies-actuals-en-la-gestio-de-cpd)

- [2. Diferències entre maquinari de tipus personal i empresarial](#2-diferencies-entre-maquinari-de-tipus-personal-i-empresarial)
  - [2.1 Característiques dels sistemes personals](#21-caracteristiques-dels-sistemes-personals)
  - [2.2 Característiques dels sistemes empresarials](#22-caracteristiques-dels-sistemes-empresarials)

- [3. Anàlisi d'entorns que requereixen solucions de maquinari específiques](#3-analisi-dentorns-que-requereixen-solucions-de-maquinari-especifiques)
  - [3.1 Entorns amb alta demanda de processament](#31-entorns-amb-alta-demanda-de-processament)
  - [3.2 Necessitats d’emmagatzematge massiu i accés ràpid](#32-necessitats-demmagatzematge-massiu-i-acces-rapid)
  - [3.3 Entorns de seguretat i protecció de dades](#33-entorns-de-seguretat-i-proteccio-de-dades)
  - [3.4 Infraestructures per a aplicacions en temps real](#34-infraestructures-per-a-aplicacions-en-temps-real)
  - [3.5 Requisits d’alta disponibilitat i tolerància a fallades](#35-requisits-dalta-disponibilitat-i-tolerancia-a-fallades)
  - [3.6 Adaptació a entorns físics i condicions ambientals extremes](#36-adaptacio-a-entorns-fisics-i-condicions-ambientals-extremes)
  - [3.7 Casos pràctics i exemples reals](#37-casos-practics-i-exemples-reals)

- [4. Components de maquinari específics per a solucions empresarials](#4-components-de-maquinari-especifics-per-a-solucions-empresarials)
  - [4.1 Servidors i processadors d’alt rendiment](#41-servidors-i-processadors-dalt-rendiment)
  - [4.2 Sistemes d’emmagatzematge d’alta capacitat i rendiment](#42-sistemes-demmagatzematge-dalta-capacitat-i-rendiment)
  - [4.3 Infraestructura de xarxa d’alt rendiment](#43-infraestructura-de-xarxa-dalt-rendiment)
  - [4.4 Sistemes de refrigeració i control ambiental](#44-sistemes-de-refrigeracio-i-control-ambiental)
  - [4.5 Energia i redundància en l’alimentació](#45-energia-i-redundancia-en-lalimentacio)
  - [4.6 Seguretat física i prevenció de desastres](#46-seguretat-fisica-i-prevencio-de-desastres)

- [5. Requeriments de seguretat física i condicions ambientals d’un CPD](#5-requeriments-de-seguretat-fisica-i-condicions-ambientals-dun-cpd)
  - [5.1 Seguretat física i control d’accés](#51-seguretat-fisica-i-control-dacces)
  - [5.2 Protecció contra desastres naturals](#52-proteccio-contra-desastres-naturals)
  - [5.3 Control ambiental i regulació de temperatura](#53-control-ambiental-i-regulacio-de-temperatura)
  - [5.4 Prevenció de riscos elèctrics i manteniment de la infraestructura](#54-prevencio-de-riscos-electrics-i-manteniment-de-la-infraestructura)

- [6. Implantació de sistemes d'alimentació ininterrompuda i estabilitzadors de tensió](#6-implantacio-de-sistemes-dalimentacio-ininterrompuda-i-estabilitzadors-de-tensio)
  - [6.1 Sistemes d'Alimentació Ininterrompuda (SAI)](#61-sistemes-dalimentacio-ininterrompuda-sai)
  - [6.2 Generadors de seguretat i fonts d’energia de reserva](#62-generadors-de-seguretat-i-fonts-denergia-de-reserva)
  - [6.3 Estabilitzadors de tensió i protecció contra fluctuacions](#63-estabilitzadors-de-tensio-i-proteccio-contra-fluctuacions)
  - [6.4 Eficiència energètica i fonts d’energia renovable](#64-eficiencia-energetica-i-fonts-denergia-renovable)
  - [6.5 Importància de la redundància elèctrica](#65-importancia-de-la-redundancia-electrica)

- [7. Manipulació de dispositius amb connexió en calent](#7-manipulacio-de-dispositius-amb-connexio-en-calent)
  - [7.1 Definició i importància de la connexió en calent](#71-definicio-i-importancia-de-la-connexio-en-calent)
  - [7.2 Components que suporten connexió en calent](#72-components-que-suporten-connexio-en-calent)
  - [7.3 Procediments per a la manipulació segura de dispositius en calent](#73-procediments-per-a-la-manipulacio-segura-de-dispositius-en-calent)
  - [7.4 Riscos i consideracions de la connexió en calent](#74-riscos-i-consideracions-de-la-connexio-en-calent)
  - [7.5 Exemples i casos pràctics](#75-exemples-i-casos-practics)

- [8. Documentació de procediments, incidències i paràmetres utilitzats en la instal·lació i configuració de dispositius de maquinari](#8-documentacio-de-procediments-incidencies-i-parametres-utilitzats-en-la-instal-lacio-i-configuracio-de-dispositius-de-maquinari)
  - [8.1 Importància de la documentació en els CPD](#81-importancia-de-la-documentacio-en-els-cpd)
  - [8.2 Tipus de documentació en la instal·lació i configuració de dispositius de maquinari](#82-tipus-de-documentacio-en-la-instal-lacio-i-configuracio-de-dispositius-de-maquinari)
  - [8.3 Procediments per a la documentació d’incidències](#83-procediments-per-a-la-documentacio-dincidencies)
  - [8.4 Ús d’eines per a la documentació i monitoratge](#84-us-de-eines-per-a-la-documentacio-i-monitoratge)
  - [8.5 Bones pràctiques en la documentació del CPD](#85-bones-practiques-en-la-documentacio-del-cpd)

- [9. Utilització d'eines d’inventariat i registre de característiques de dispositius de maquinari](#9-utilitzacio-de-eines-dinventariat-i-registre-de-caracteristiques-de-dispositius-de-maquinari)
  - [9.1 Importància de l’inventariat en un CPD](#91-importancia-de-linventariat-en-un-cpd)
  - [9.2 Tipus d’eines d’inventariat de maquinari](#92-tipus-de-eines-dinventariat-de-maquinari)
  - [9.3 Procediment per a la gestió de l’inventari de maquinari](#93-procediment-per-a-la-gestio-de-linventari-de-maquinari)
  - [9.4 Beneficis de la gestió automatitzada de l’inventari](#94-beneficis-de-la-gestio-automatitzada-de-linventari)
  - [9.5 Integració de l’inventariat amb altres sistemes de gestió](#95-integracio-de-linventariat-amb-altres-sistemes-de-gestio)

- [10. Infografia](#10-Infografia)


## 1. Introducció als Centres de Processament de Dades (CPD)

### 1.1 Definició i funcions principals d'un CPD
Un Centre de Processament de Dades (CPD), o Data Center, és una instal·lació que reuneix equips informàtics per gestionar grans volums de dades i oferir serveis essencials per a empreses i organitzacions. La seva funció no es limita només a l'emmagatzematge d'informació, sinó que també inclou la gestió de la seguretat, la redundància i l'accessibilitat a les dades, garantint que estiguin disponibles en tot moment. 

Amb l'evolució tecnològica, els CPD han esdevingut infraestructures clau en sectors com la banca, la sanitat, les telecomunicacions i el comerç electrònic. La seva importància radica en la capacitat d'assegurar un servei fiable i optimitzat, minimitzant el risc de pèrdues de dades o interrupcions en el servei.

### 1.2 Tipologies de CPD
Els CPD es poden classificar en diferents tipus segons la seva infraestructura i el model de desplegament.

Els **CPD tradicionals** són infraestructures físiques que es troben dins de les instal·lacions d'una organització. Aquest model permet un control absolut sobre les dades i els sistemes, però implica una inversió inicial elevada i costos operatius considerables. Són utilitzats per empreses que requereixen un control total sobre la seva informació i tenen la capacitat de mantenir un equip tècnic dedicat al seu manteniment.

Els **CPD modulars** estan dissenyats per ser escalables i fàcilment desplegables. Es basen en mòduls prefabricats que es poden ampliar segons les necessitats de l'empresa, cosa que redueix els costos i permet una instal·lació més ràpida. Aquesta opció resulta especialment útil per a organitzacions en creixement que necessiten una infraestructura flexible i escalable.

Els **CPD al núvol**, també coneguts com a Cloud Data Centers, es gestionen a través de proveïdors externs com AWS, Azure o Google Cloud. Aquests CPD eliminen la necessitat de gestionar la infraestructura física, oferint flexibilitat i escalabilitat. Tot i això, aquesta opció implica perdre part del control directe sobre les dades, la qual cosa pot ser un desavantatge per a empreses amb requisits de seguretat estrictes.

Finalment, els **CPD híbrids** combinen infraestructures físiques amb serveis al núvol, proporcionant un equilibri entre seguretat i escalabilitat. Aquest model és especialment útil per a empreses que volen protegir informació sensible, però també aprofitar els avantatges de la computació al núvol, permetent la gestió dinàmica de recursos segons les necessitats operatives.

### 1.3 Tendències actuals en la gestió de CPD
En els darrers anys, la virtualització i l'automatització han permès maximitzar l'ús dels recursos disponibles i facilitar la gestió remota de les infraestructures. A més, la intel·ligència artificial s'està implementant per a la monitorització, ajudant a predir errors i a optimitzar l'eficiència energètica dels servidors. 

Un altre aspecte fonamental és la sostenibilitat i l'eficiència energètica. Els CPD consumeixen grans quantitats d'energia, i per això s'estan implementant sistemes de refrigeració més eficients i l'ús d'energies renovables per reduir l'impacte ambiental. 

Finalment, l'Edge Computing s'ha convertit en una solució rellevant per reduir la latència en el processament de dades. Amb l'augment de dispositius IoT, és necessari processar la informació més a prop del lloc on es genera, millorant així el temps de resposta.

## 2. Diferències entre maquinari de tipus personal i empresarial

### 2.1 Característiques dels sistemes personals
Els ordinadors personals estan pensats per a ús domèstic o oficines petites. Encara que poden oferir un bon rendiment, no estan dissenyats per suportar càrregues de treball contínues i exigents. Normalment, utilitzen processadors de gamma mitjana que permeten executar tasques bàsiques com navegació web, edició de documents i multimèdia lleugera. 

La memòria i l'emmagatzematge solen ser limitats, i encara que es poden ampliar, no estan optimitzats per a grans volums de dades ni per a operacions simultànies massives. A més, aquests sistemes presenten una fiabilitat i seguretat bàsica, sense mecanismes de redundància ni proteccions avançades contra fallades de maquinari o ciberatacs. Un dels seus principals avantatges és el cost més baix en comparació amb els sistemes empresarials, tot i que la seva vida útil i capacitat d'actualització són més limitades.

### 2.2 Característiques dels sistemes empresarials
Els sistemes empresarials, com els servidors i les estacions de treball avançades, estan dissenyats per funcionar de manera contínua i garantir una seguretat i eficiència òptimes en entorns professionals exigents. A diferència dels sistemes personals, utilitzen processadors d’alta gamma com Intel Xeon o AMD EPYC, que estan optimitzats per a tasques intensives com bases de dades, virtualització i intel·ligència artificial. 

La memòria RAM utilitzada sol ser ECC (Error-Correcting Code), que permet detectar i corregir errors en la memòria que podrien provocar fallades en sistemes crítics. L'emmagatzematge en aquests sistemes es gestiona mitjançant tecnologies avançades com els sistemes RAID, que protegeixen contra pèrdues de dades i milloren el rendiment.

A més, els sistemes empresarials inclouen mecanismes de redundància, com fonts d’alimentació dobles, ventiladors addicionals i sistemes d’autodiagnòstic que minimitzen el risc d’interrupcions. La seguretat és un altre aspecte fonamental, amb característiques com el xifrat de dades, l'autenticació multifactor i la monitorització constant per detectar possibles amenaces.

## 3. Anàlisi d'entorns que requereixen solucions de maquinari específiques

L'elecció del maquinari en un Centre de Processament de Dades (CPD) no és una decisió estàndard, sinó que ha de ser adaptada a les necessitats específiques de cada organització. Cada sector té requeriments diferents en termes de potència de càlcul, capacitat d'emmagatzematge, seguretat i disponibilitat. A continuació, s'analitzen els entorns més rellevants que requereixen solucions especialitzades.

### 3.1 Entorns amb alta demanda de processament

Les empreses i institucions que necessiten una gran capacitat de càlcul recorren a servidors d'alt rendiment amb múltiples processadors i grans quantitats de memòria RAM. Això és essencial en camps com la recerca científica, la simulació d'esdeveniments físics i la intel·ligència artificial.

Per exemple, en el sector financer, els algoritmes de predicció de mercats requereixen màquines capaços d'executar càlculs complexos en fraccions de segon. Així mateix, les universitats i centres de recerca utilitzen superordinadors per a simulacions climàtiques, estudis genètics i desenvolupament de nous materials.

En aquests casos, és fonamental l'ús de processadors multinúcli, acceleradors com GPU (Graphics Processing Units) i TPU (Tensor Processing Units) i xarxes de comunicació d'alta velocitat per evitar colls d'ampolla en la transferència de dades.

### 3.2 Necessitats d’emmagatzematge massiu i accés ràpid

En sectors com el multimèdia, el big data i la gestió documental, es requereixen grans sistemes d’emmagatzematge amb temps de resposta ràpids. L’ús de sistemes NAS (Network Attached Storage) o SAN (Storage Area Network) és essencial per garantir la disponibilitat i protecció de la informació.

Un exemple clar és la indústria audiovisual, on es treballa amb arxius de vídeo d'alta resolució que han de ser editats i processats en temps real. Això requereix sistemes de disc d’alta velocitat, com SSD NVMe, així com estratègies de redundància basades en RAID per evitar la pèrdua d’arxius.

### 3.3 Entorns de seguretat i protecció de dades

La gestió de dades sensibles en sectors com la banca, la salut i l'administració pública implica l'ús de sistemes de maquinari amb alts estàndards de seguretat. Els servidors en aquests entorns estan equipats amb mecanismes com el xifrat d'emmagatzematge, l'autenticació multifactor i l'ús de firewalls físics per protegir contra atacs externs.

Els bancs, per exemple, requereixen una infraestructura robusta per garantir transaccions segures i complir amb normatives estrictes com la PCI-DSS (Payment Card Industry Data Security Standard). En el sector sanitari, la protecció de les dades dels pacients és fonamental, per la qual cosa s'utilitzen sistemes amb xifrat avançat i mecanismes de registre i auditories de l'accés a la informació.

### 3.4 Infraestructures per a aplicacions en temps real

Els sistemes que necessiten respostes instantànies, com els de telecomunicacions o els de control de trànsit aeri, han de comptar amb servidors i xarxes d’alta velocitat per minimitzar la latència.

Per exemple, en la borsa de valors, cada mil·lisegon compta, i per això es fan servir xarxes de baixa latència amb connexions de 100 Gbps i servidors optimitzats per processar ordres en temps real. De manera similar, els sistemes de seguretat pública, com el control de videovigilància urbana, han d'analitzar i processar en temps real milions de fotogrames per detectar amenaces potencials.

### 3.5 Requisits d’alta disponibilitat i tolerància a fallades

Els sistemes crítics, com els dels hospitals, aeroports o centrals elèctriques, requereixen una infraestructura dissenyada per mantenir-se operativa sense interrupcions. Això s'aconsegueix mitjançant arquitectures de redundància amb servidors replicats, alimentació ininterrompuda (UPS) i sistemes de recuperació automàtica davant fallades.

Per exemple, en els hospitals, les màquines que gestionen la informació dels pacients han d’estar disponibles en tot moment per evitar errors en el diagnòstic i tractament. Per aconseguir-ho, es despleguen solucions com miralls de bases de dades en temps real i xarxes amb rutes alternatives per garantir la continuïtat del servei.

### 3.6 Adaptació a entorns físics i condicions ambientals extremes

No tots els CPD es troben en llocs amb condicions ambientals òptimes. Algunes instal·lacions han de suportar temperatures extremes, alta humitat o presència de pols i contaminants. Això requereix maquinari especialitzat amb sistemes de refrigeració líquida, carcasses resistents i protecció contra vibracions.

Un exemple és el desplegament de CPD en bases militars situades en deserts o regions polars. Aquestes instal·lacions han de funcionar en condicions adverses, per la qual cosa es dissenyen amb sistemes de refrigeració autònoma i protecció contra interferències electromagnètiques.

### 3.7 Casos pràctics i exemples reals

L’elecció del maquinari correcte no és una qüestió teòrica, sinó que té aplicacions pràctiques en diversos sectors. A continuació, es presenten alguns exemples:

- **Google Data Centers**: Utilitzen intel·ligència artificial per optimitzar el consum energètic i gestionar automàticament la refrigeració dels seus servidors.
- **NASA**: Gestiona enormes quantitats de dades provinents de satèl·lits i missions espacials mitjançant supercomputadors especialitzats en càlcul científic.
- **Banca internacional**: Les entitats financeres utilitzen sistemes amb alts estàndards de seguretat i duplicació de dades per garantir la integritat de les transaccions.

## 4. Components de maquinari específics per a solucions empresarials

Els Centres de Processament de Dades (CPD) depenen de components de maquinari específics que permeten assegurar la seva eficiència, seguretat i escalabilitat. Cada component ha de ser seleccionat en funció de les necessitats particulars de l'entorn empresarial, amb l'objectiu de garantir un rendiment òptim i la continuïtat del servei.

### 4.1 Servidors i processadors d’alt rendiment

Els servidors constitueixen el pilar fonamental d’un CPD, ja que gestionen el processament de dades i suporten les aplicacions crítiques de les empreses. A diferència dels ordinadors personals, els servidors estan dissenyats per operar de manera contínua, suportant càrregues de treball elevades i garantint alts nivells de disponibilitat. 

Els servidors moderns integren processadors d’alt rendiment, com ara la línia **Intel Xeon** i **AMD EPYC**, que permeten executar múltiples fils de dades simultàniament. Aquests processadors incorporen tecnologies de virtualització avançades que optimitzen l’ús dels recursos, especialment en infraestructures que utilitzen contenidors o màquines virtuals.

Un altre aspecte rellevant en els servidors empresarials és la memòria RAM de tipus **ECC (Error-Correcting Code)**, que detecta i corregeix errors de dades abans que puguin afectar el funcionament del sistema. Aquesta característica és essencial per a entorns crítics on una mínima corrupció de dades pot tenir conseqüències greus, com en sistemes financers o sanitaris.

### 4.2 Sistemes d’emmagatzematge d’alta capacitat i rendiment

Els CPD gestionen volums massius d’informació, per la qual cosa requereixen sistemes d’emmagatzematge que proporcionin capacitat, rapidesa i redundància. L’emmagatzematge ha evolucionat considerablement, passant dels clàssics discs HDD a les unitats **SSD NVMe**, que ofereixen una latència mínima i velocitats de transferència de dades molt superiors.

Per a la gestió i escalabilitat de la informació, s’utilitzen diferents arquitectures d’emmagatzematge. Els sistemes **DAS (Direct Attached Storage)** es connecten directament a un servidor i són útils per aplicacions específiques, mentre que els **NAS (Network Attached Storage)** permeten accés compartit a diversos servidors. En entorns més grans, els **SAN (Storage Area Network)** proporcionen xarxes dedicades per a l’accés a dades d’alta velocitat, garantint una major fiabilitat i escalabilitat.

A més, per protegir la informació davant possibles fallades, es recorre a tecnologies de **RAID (Redundant Array of Independent Disks)**, que permeten distribució i redundància de dades a través de múltiples discs. Això garanteix que, en cas de fallada d’un disc, la informació pugui ser recuperada sense pèrdues.

### 4.3 Infraestructura de xarxa d’alt rendiment

Un CPD no només requereix potència de processament i capacitat d’emmagatzematge, sinó també una infraestructura de xarxa que garanteixi una transmissió de dades ràpida i segura. La velocitat de comunicació entre servidors i altres dispositius és un factor clau per evitar colls d'ampolla i optimitzar el rendiment global de la infraestructura.

Els encaminadors i commutadors d’alt rendiment gestionen el trànsit intern del CPD i asseguren una distribució eficient de les dades. Actualment, moltes empreses opten per solucions basades en **SDN (Software-Defined Networking)**, una tecnologia que permet una gestió dinàmica i automatitzada de la xarxa, millorant la flexibilitat i adaptabilitat del sistema.

A més, els sistemes de seguretat de xarxa són una peça fonamental. Els tallafocs de maquinari protegeixen contra atacs externs, mentre que els balancejadors de càrrega distribueixen el trànsit de manera intel·ligent per evitar sobrecàrregues en servidors específics. Sense aquestes mesures, un CPD quedaria exposat a fallades de seguretat i interrupcions en el servei.

### 4.4 Sistemes de refrigeració i control ambiental

L’escalfament del maquinari és un dels principals reptes dels CPD. El funcionament continu dels servidors genera grans quantitats de calor, que han de ser dissipades eficientment per evitar sobreescalfaments i garantir la durabilitat dels components.

Els sistemes tradicionals de refrigeració per aire, basats en ventiladors industrials i aire condicionat, continuen sent els més utilitzats. No obstant això, en infraestructures de gran densitat computacional s’està implementant cada cop més la **refrigeració per líquid**, que permet una dissipació tèrmica més eficient i un menor consum energètic.

Els passadissos calents i freds són una altra tècnica comuna per optimitzar el flux d’aire dins del CPD. Mitjançant la separació d’entrades d’aire fred i sortides d’aire calent, es redueix el consum energètic i es millora la refrigeració general del sistema. 

Per monitoritzar en temps real les condicions ambientals, els CPD incorporen sensors de temperatura, humitat i flux d’aire, que permeten ajustar els sistemes de refrigeració automàticament per maximitzar l’eficiència energètica.

### 4.5 Energia i redundància en l’alimentació

Per garantir una operació ininterrompuda, els CPD han de disposar de sistemes d’alimentació redundants que assegurin el funcionament fins i tot en cas de fallades elèctriques. Els **SAI (Sistemes d’Alimentació Ininterrompuda)** proporcionen energia temporal en situacions de tall elèctric, mentre que els generadors de seguretat ofereixen una font d’alimentació alternativa per períodes prolongats.

Els **PDU (Power Distribution Units) intel·ligents** permeten una gestió avançada del consum energètic, regulant la distribució de l’energia entre els diferents servidors i components del CPD. A més, en molts CPD moderns s’estan implementant estratègies de sostenibilitat basades en energies renovables, com ara panells solars i sistemes d’optimització energètica basats en IA.

### 4.6 Seguretat física i prevenció de desastres

A banda de la seguretat cibernètica, la seguretat física dels CPD és igualment important. Aquests centres han d’estar protegits contra accessos no autoritzats mitjançant sistemes de control biomètric i vigilància constant.

També és fonamental la protecció contra desastres naturals. Per això, molts CPD incorporen estructures antisísmiques, sistemes de protecció contra inundacions i sistemes d’extinció d’incendis especialitzats que utilitzen gasos inerts per evitar danys al maquinari.

## 5. Requeriments de seguretat física i condicions ambientals d’un CPD

Els Centres de Processament de Dades (CPD) han de complir amb estrictes requisits de seguretat física i ambientals per garantir la integritat dels equips i la disponibilitat contínua dels serveis. Aquests requisits inclouen tant la protecció davant accessos no autoritzats com la prevenció d’amenaces ambientals que podrien comprometre el funcionament de la infraestructura.

### 5.1 Seguretat física i control d’accés

Un CPD ha d’estar protegit contra accessos no autoritzats mitjançant mesures de seguretat rigoroses. Els sistemes de control d’accés inclouen identificació biomètrica, targetes d’accés RFID i sistemes de videovigilància per monitoritzar l’activitat en tot moment. Només el personal autoritzat ha de poder accedir a les àrees crítiques del CPD.

A més de la gestió d’accés, és essencial comptar amb protocols d’identificació i registre de visites, així com mecanismes de doble autenticació per accedir a zones sensibles. Això redueix el risc de manipulacions no autoritzades que podrien posar en perill la infraestructura o les dades emmagatzemades.

### 5.2 Protecció contra desastres naturals

Els CPD han d'estar preparats per resistir desastres naturals com terratrèmols, inundacions, incendis i tempestes elèctriques. Per això, les instal·lacions han de comptar amb estructures reforçades, sistemes d'absorció de vibracions en cas de moviments sísmics i ubicacions estratègiques que minimitzin el risc d'inundacions.

En el cas dels incendis, s’utilitzen sistemes d’extinció especialitzats que no danyin el maquinari, com ara gasos inerts (FM-200 o Novec 1230) en lloc d’aigua. A més, s’instal·len detectors de fum avançats que permeten una resposta ràpida davant qualsevol indici de foc.

### 5.3 Control ambiental i regulació de temperatura

La temperatura dins d’un CPD ha de mantenir-se en un rang òptim per evitar el sobreescalfament dels equips. L’ideal és mantenir una temperatura ambient entre **18 i 27°C**, segons les recomanacions de l'ASHRAE (American Society of Heating, Refrigerating and Air-Conditioning Engineers). Els sistemes de climatització han d’incloure controladors automàtics per ajustar la temperatura en temps real.

Els sensors de temperatura i humitat han de ser distribuïts estratègicament per detectar possibles anomalies. A més, s’han d’aplicar estratègies de gestió tèrmica com els passadissos calents i freds per millorar l’eficiència del sistema de refrigeració i reduir el consum energètic.

### 5.4 Prevenció de riscos elèctrics i manteniment de la infraestructura

Els CPD han de comptar amb protecció contra sobrecàrregues elèctriques, sobretensions i fallades en el subministrament. Això es pot aconseguir mitjançant sistemes d’estabilització de tensió, preses de terra adequades i sistemes de protecció contra descàrregues elèctriques.

El manteniment preventiu és essencial per garantir el bon funcionament del CPD. Es recomana realitzar inspeccions periòdiques als sistemes elèctrics, revisar l'estat de les bateries dels SAI i verificar el funcionament correcte dels generadors de seguretat.

## 6. Implantació de sistemes d'alimentació ininterrompuda i estabilitzadors de tensió

Un dels aspectes més crítics en el funcionament d'un CPD és garantir un subministrament elèctric estable i ininterromput. Qualsevol interrupció en l’alimentació pot provocar pèrdua de dades, danys en el maquinari i interrupció de serveis essencials.

### 6.1 Sistemes d'Alimentació Ininterrompuda (SAI)

Els **Sistemes d'Alimentació Ininterrompuda (SAI)** tenen un paper fonamental en la protecció dels CPD. Aquests dispositius proporcionen energia temporal en cas de talls de llum, permetent que els servidors continuïn funcionant fins que s'activi una font d'energia alternativa.

Els SAI poden ser de diferents tipus segons la seva funcionalitat:

- **SAI en espera (standby UPS):** Actuen només quan es detecta una interrupció del subministrament elèctric, sent adequats per a càrregues no crítiques.
- **SAI en línia (online UPS):** Proporcionen una protecció contínua contra variacions de tensió i interrupcions, filtrant qualsevol anomalia abans que arribi als servidors.
- **SAI interactius (line-interactive UPS):** Són una combinació dels anteriors, permetent estabilitzar petites fluctuacions de tensió sense recórrer a la bateria.

### 6.2 Generadors de seguretat i fonts d’energia de reserva

Els CPD requereixen generadors de seguretat per assegurar una font d’alimentació alternativa en cas de fallada prolongada del subministrament elèctric. Els generadors poden ser de **dièsel, gas natural o híbrids**, depenent de les necessitats i la disponibilitat de combustibles.

Un CPD ben dissenyat ha de comptar amb una transició automàtica entre el subministrament elèctric principal i els generadors. Els sistemes de commutació ràpida permeten que els generadors s’activin immediatament quan es detecta una fallada en la xarxa elèctrica.

### 6.3 Estabilitzadors de tensió i protecció contra fluctuacions

Les fluctuacions de tensió poden ser tan perjudicials com un tall elèctric complet, ja que poden causar danys en els components electrònics sensibles dels servidors i dispositius de xarxa. Per evitar aquests problemes, els CPD utilitzen **estabilitzadors de tensió**, que regulen i mantenen el subministrament dins d’un rang segur.

A més dels estabilitzadors, es fan servir sistemes de **protecció contra sobretensions**, que absorbeixen pics de tensió i eviten que arribin als equips. Aquests dispositius són essencials en zones amb infraestructures elèctriques inestables o exposades a fenòmens meteorològics extrems.

### 6.4 Eficiència energètica i fonts d’energia renovable

Cada cop més CPD estan implementant solucions d’**eficiència energètica** per reduir el seu consum elèctric. Això inclou l’ús de sistemes de refrigeració més eficients, optimització de la distribució de càrregues elèctriques i la implementació de fonts d’energia renovables com **panells solars** i **energia eòlica**.

La integració de tecnologies de gestió intel·ligent d’energia permet monitoritzar en temps real el consum elèctric i ajustar l’ús de recursos per evitar malbarataments. Algunes empreses estan aplicant solucions basades en **intel·ligència artificial** per predir i gestionar de manera més eficient la demanda energètica en els CPD.

### 6.5 Importància de la redundància elèctrica

Un CPD ha de ser capaç de continuar funcionant fins i tot en condicions extremes. Per aconseguir-ho, s’implementen arquitectures de **redundància elèctrica**, on els sistemes d’alimentació compten amb fonts alternatives d’energia i camins de distribució separats per evitar que una única fallada afecti tota la infraestructura.

Els sistemes de distribució intel·ligent, com les **PDU (Power Distribution Units) intel·ligents**, permeten administrar l’energia de manera eficient i redistribuir la càrrega segons les necessitats en temps real.

Garantir una alimentació elèctrica estable i redundant és una de les prioritats en el disseny de qualsevol CPD. Sense un sistema d’energia fiable, fins i tot els servidors més potents serien inútils davant d’una interrupció prolongada.

## 7. Manipulació de dispositius amb connexió en calent

La connexió en calent (hot swapping o hot plugging) és una tècnica fonamental en els Centres de Processament de Dades (CPD) que permet afegir o substituir components de maquinari sense necessitat d’aturar el sistema. Aquesta capacitat és essencial per garantir la disponibilitat contínua dels serveis i evitar interrupcions no programades.

### 7.1 Definició i importància de la connexió en calent

La manipulació de dispositius amb connexió en calent consisteix a substituir o afegir components mentre el sistema està en funcionament, sense comprometre l’estabilitat del servei. Aquesta tècnica s’utilitza en entorns on la disponibilitat és crítica, com ara servidors de producció, bases de dades empresarials i sistemes de xarxa d’alta disponibilitat.

L’ús de la connexió en calent permet als administradors de sistemes realitzar tasques de manteniment sense necessitat de programar parades, millorant així l’eficiència operativa del CPD. A més, minimitza el temps d’inactivitat i permet escalar la infraestructura segons les necessitats de l’empresa.

### 7.2 Components que suporten connexió en calent

No tots els dispositius informàtics permeten la connexió en calent. Perquè un component sigui compatible amb aquesta tecnologia, ha de tenir el suport del maquinari i del sistema operatiu. Alguns dels components més comuns que permeten connexió en calent inclouen:

- **Discos durs i unitats SSD**: La majoria dels servidors moderns suporten la substitució de discs durs i unitats SSD en calent mitjançant sistemes RAID, garantint així la continuïtat de les operacions sense pèrdua de dades.
- **Fonts d’alimentació redundants**: Molts servidors empresarials i sistemes de xarxa incorporen fonts d’alimentació dobles, que permeten substituir una unitat defectuosa sense apagar el sistema.
- **Mòduls de memòria RAM**: En determinats servidors avançats, és possible afegir o substituir mòduls de memòria en calent sense necessitat de reiniciar la màquina.
- **Dispositius de xarxa**: Els switches i routers empresarials sovint permeten la substitució de mòduls d'interconnexió i fonts d’alimentació sense interrupcions.
- **Targetes d’expansió PCIe**: Algunes plataformes avançades suporten la connexió en calent de targetes PCI Express per ampliar la funcionalitat sense aturar el sistema.

### 7.3 Procediments per a la manipulació segura de dispositius en calent

Per garantir una manipulació segura dels dispositius en calent, és essencial seguir una sèrie de passos per evitar errors i possibles danys al sistema:

1. **Verificar la compatibilitat**: Assegurar-se que el dispositiu i el sistema operatiu són compatibles amb la connexió en calent. Els manuals tècnics del fabricant solen especificar si un component suporta aquesta funcionalitat.
2. **Utilitzar eines de gestió del sistema**: Sistemes operatius com Windows Server i Linux disposen d’eines específiques per desconnectar i connectar dispositius en calent de manera segura.
3. **Identificar el dispositiu correcte**: En sistemes amb múltiples components, és crucial verificar el número de sèrie i la ubicació del dispositiu abans de retirar-lo o substituir-lo.
4. **Monitorització en temps real**: L’ús d’eines de monitoratge com Nagios o Zabbix permet detectar possibles problemes en el moment de la substitució.
5. **Executar proves posteriors**: Després d’instal·lar un nou dispositiu, és important comprovar el seu funcionament per assegurar-se que està operant correctament sense causar problemes al sistema.

### 7.4 Riscos i consideracions de la connexió en calent

Tot i que la connexió en calent és una tecnologia molt útil, també comporta alguns riscos que cal tenir en compte. La manipulació incorrecta dels dispositius pot provocar corrupció de dades, inestabilitat del sistema i possibles danys físics en els components.

Alguns dels principals riscos inclouen:
- **Fallades per connexió defectuosa**: Inserir incorrectament un dispositiu pot causar errors de lectura o escriptura.
- **Pèrdua de dades**: Si un dispositiu s’extrau mentre encara està processant informació, es poden perdre dades crítiques.
- **Sobreescalfament**: La manipulació de components sense una ventilació adequada pot provocar un augment de la temperatura.
- **Errors en el sistema operatiu**: No tots els sistemes operatius gestionen adequadament la connexió en calent, cosa que pot generar bloquejos o errors imprevistos.

Per mitigar aquests riscos, és fonamental seguir els protocols de seguretat establerts i formar el personal tècnic perquè realitzi aquestes operacions de manera correcta.

### 7.5 Exemples i casos pràctics

La connexió en calent es fa servir àmpliament en entorns empresarials que requereixen una alta disponibilitat. Alguns exemples d’ús inclouen:

- **Centres de dades de Google i Amazon**: Aquests proveïdors de serveis en el núvol utilitzen connexió en calent per mantenir els seus servidors en funcionament mentre actualitzen o substitueixen components.
- **Borses de valors i institucions financeres**: Els servidors que gestionen transaccions en temps real necessiten mantenir una operativitat constant, per la qual cosa la connexió en calent és essencial per a la substitució de discos durs i fonts d’alimentació.
- **Hospitals i sistemes sanitaris**: Els sistemes de gestió hospitalària han de romandre operatius 24/7, i la capacitat de substituir components sense interrupcions és fonamental per garantir la continuïtat del servei.

## 8. Documentació de procediments, incidències i paràmetres utilitzats en la instal·lació i configuració de dispositius de maquinari

La documentació és un aspecte fonamental en la gestió i manteniment dels Centres de Processament de Dades (CPD). Sense una documentació adequada, la resolució d’incidències, la configuració d’equips i el seguiment dels canvis realitzats poden esdevenir processos ineficients i susceptibles a errors. Aquesta secció explora la importància de la documentació en la instal·lació i configuració de dispositius de maquinari, així com els tipus de documents necessaris per garantir una administració òptima del CPD.

### 8.1 Importància de la documentació en els CPD

En un entorn crític com un CPD, la documentació no és només un registre administratiu, sinó una eina clau per a la continuïtat operativa i la seguretat de la infraestructura. Una documentació clara i actualitzada permet als tècnics diagnosticar problemes ràpidament, assegurar la coherència en les configuracions i reduir el temps d’inactivitat en cas d’incidències.

L’absència de documentació pot conduir a errors en la configuració de maquinari, dificultats en la recuperació de dades i problemes en la coordinació d’equips tècnics. A més, moltes normatives internacionals, com la ISO 27001 en seguretat de la informació, exigeixen que els CPD mantinguin registres detallats de totes les operacions i modificacions realitzades en la seva infraestructura.

### 8.2 Tipus de documentació en la instal·lació i configuració de dispositius de maquinari

Per garantir una gestió eficient, la documentació en un CPD s’ha de dividir en diverses categories:

- **Documentació de configuració inicial**: Registre de la instal·lació de nous equips, incloent els paràmetres de configuració de servidors, emmagatzematge i xarxes.
- **Manuals i guies tècniques**: Documents que especifiquen els procediments per a la gestió d’equips, com la substitució de components, actualitzacions de firmware i protocols de manteniment.
- **Registres d’incidències**: Informe detallat de qualsevol error, fallada o problema tècnic, amb les accions preses per a la seva resolució.
- **Canvis i actualitzacions**: Registre de qualsevol modificació realitzada en la configuració del maquinari o programari, per tal de garantir la coherència i traçabilitat dels ajustaments fets.
- **Inventari de maquinari**: Llistat complet de tots els dispositius instal·lats, amb informació sobre el seu estat, número de sèrie i ubicació física dins del CPD.

### 8.3 Procediments per a la documentació d’incidències

Una documentació eficaç d’incidències permet millorar la gestió dels errors i reduir el temps de resposta en cas de problemes recurrents. Un bon informe d’incidència ha d’incloure:

1. **Identificació del problema**: Descripció detallada de la incidència detectada.
2. **Entorn afectat**: Llistat dels sistemes o serveis impactats.
3. **Hora i data de l’incident**: Registre precís per a la seva traçabilitat.
4. **Accions realitzades**: Descripció de les mesures adoptades per resoldre el problema.
5. **Resultat final**: Confirmació de si el problema ha estat resolt amb èxit o si es requereixen accions addicionals.
6. **Responsables implicats**: Identificació del personal tècnic que ha intervingut en la resolució.

### 8.4 Ús d’eines per a la documentació i monitoratge

Avui dia, la gestió documental en els CPD es facilita gràcies a eines digitals especialitzades. Algunes de les més utilitzades són:

- **CMDB (Configuration Management Database)**: Bases de dades que emmagatzemen tota la informació relativa als actius de TI i la seva configuració.
- **Sistemes de ticketing**: Com ServiceNow, Jira o GLPI, que permeten gestionar incidències i registrar intervencions tècniques.
- **Plataformes de monitorització**: Com Nagios, Zabbix o SolarWinds, que proporcionen informació en temps real sobre l’estat del maquinari i les possibles alertes de fallades.
- **Software de gestió documental**: Com SharePoint o Confluence, que ajuden a organitzar la documentació tècnica i assegurar-ne l’actualització constant.

### 8.5 Bones pràctiques en la documentació del CPD

Perquè la documentació sigui útil i eficaç, és fonamental seguir algunes bones pràctiques:

- **Mantenir la documentació actualitzada**: Qualsevol canvi en la configuració ha de ser reflectit immediatament en els registres.
- **Utilitzar una estructura clara**: Els documents han de ser accessibles i fàcils de llegir per a tot el personal tècnic.
- **Establir responsabilitats**: Designar qui és responsable de la creació, actualització i verificació de la documentació.
- **Fer còpies de seguretat dels documents**: Assegurar-se que la informació crítica estigui protegida davant possibles pèrdues.

## 9. Utilització d'eines d’inventariat i registre de característiques de dispositius de maquinari

La gestió eficient d’un Centre de Processament de Dades (CPD) requereix un control rigorós dels recursos de maquinari disponibles. Les eines d’inventariat permeten registrar i monitoritzar tots els dispositius de maquinari, facilitant el manteniment, la detecció de problemes i la planificació de futures ampliacions de la infraestructura.

### 9.1 Importància de l’inventariat en un CPD

Un inventari ben gestionat ajuda a optimitzar l’ús dels recursos, evitar la pèrdua de dispositius i millorar la planificació de renovacions i actualitzacions de maquinari. Sense una documentació adequada, les empreses poden enfrontar-se a problemes com la falta de control sobre l’estat dels equips, la redundància en compres i dificultats en la localització de components específics.

A més, moltes normatives de seguretat i gestió de dades, com la ISO 27001, exigeixen un registre detallat de tots els dispositius de maquinari per garantir la seva traçabilitat i seguretat.

### 9.2 Tipus d’eines d’inventariat de maquinari

Les eines d’inventariat poden ser manuals o automatitzades, depenent de la mida i complexitat del CPD. Algunes de les més utilitzades són:

- **Fulls de càlcul i bases de dades manuals**: Utilitzats per a petits CPD o entorns on no es requereix una gestió complexa.
- **Software de gestió d’actius IT (ITAM - IT Asset Management)**: Solucions com GLPI, OCS Inventory o Lansweeper que permeten un registre detallat i automatitzat de cada dispositiu.
- **CMDB (Configuration Management Database)**: Bases de dades especialitzades en la gestió d’actius i configuracions, que faciliten la supervisió de canvis i la resolució d’incidències.
- **Eines de monitoratge i inventariat automàtic**: Sistemes com Nagios, Zabbix o SolarWinds que, a més d’inventariar, permeten monitoritzar en temps real l’estat del maquinari i rebre alertes en cas d’errors o fallades.

### 9.3 Procediment per a la gestió de l’inventari de maquinari

Per assegurar una gestió eficaç de l’inventari de maquinari, és necessari establir un procediment clar i estructurat:

1. **Identificació de tots els dispositius**: Cada equip ha de ser registrat amb un identificador únic i la seva ubicació en el CPD.
2. **Recopilació de dades tècniques**: Incloure informació com el model, número de sèrie, data d’adquisició i garantia.
3. **Assignació de responsables**: Determinar qui és el responsable del manteniment i supervisió de cada dispositiu.
4. **Implementació d’eines de gestió**: Utilitzar programari adequat per al registre i seguiment dels equips.
5. **Actualització i verificació periòdica**: Realitzar auditories regulars per assegurar que la informació és correcta i actualitzada.

### 9.4 Beneficis de la gestió automatitzada de l’inventari

L’automatització de la gestió d’inventari en un CPD ofereix nombrosos avantatges:

- **Millor eficiència operativa**: Redueix el temps i els recursos necessaris per al manteniment dels registres.
- **Major precisió i reducció d’errors**: Evita errades humanes en la recopilació i actualització de dades.
- **Facilitat en la detecció de problemes**: Permet identificar ràpidament dispositius obsolets o amb rendiment deficient.
- **Planificació de compres i actualitzacions**: Ajuda a preveure necessitats futures i optimitzar el pressupost de manteniment.

## 10. Infografia

- **"Data Center Handbook"**: Aquest manual ofereix una visió completa sobre el disseny, construcció i gestió de centres de dades. Proporciona informació detallada i pràctica per a professionals del sector. ([renzo.itsperu.com](http://renzo.itsperu.com/Data_Center_Handbook.pdf)

- **"Fundamentals of Data Center"**: Aquest document proporciona una visió general dels fonaments dels centres de dades, incloent-hi aspectes relacionats amb sistemes Linux. ([lsi.vc.ehu.eus](https://lsi.vc.ehu.eus/pablogn/docencia/AS/Act1%20Sysadmin%20y%20%20CPD/Act1B%20CPD/Fundamentals_of_Data_Centre_Part_1.pdf))


- **System Architecture i Computació en el Núvol:** Aquesta conferència ofereix una visió general de l'arquitectura dels sistemes, incloent-hi la integració de components de maquinari i programari, així com una introducció a la computació en el núvol. ([ocw.mit.edu](https://ocw.mit.edu/courses/1-264j-database-internet-and-systems-integration-technologies-fall-2013/072a59807e2627fd068e08eb08133f70_MIT1_264JF13_lect_31.pdf))

- **Guia d'Implementació i Ús de l'HMC dels Sistemes Power d'IBM:** Aquest manual proporciona una guia detallada sobre la implementació i l'ús de la Consola de Gestió de Maquinari (HMC) en els sistemes Power d'IBM. ([redbooks.ibm.com](https://www.redbooks.ibm.com/redbooks/pdfs/sg248334.pdf))

- **Guia d'Implementació del Sistema d'Emmagatzematge Elàstic d'IBM:** Aquest document introdueix i descriu el Sistema d'Emmagatzematge Elàstic d'IBM com una solució escalable i d'alt rendiment per a la gestió de dades i fitxers. ([redbooks.ibm.com](https://www.redbooks.ibm.com/redpapers/pdfs/redp5487.pdf))

- **Fitxers PDF i manuals d'IBM i:** El Centre d'Informació d'IBM i ofereix fitxers en format PDF per a la visualització o impressió de diversos temes relacionats amb els sistemes IBM i. ([ibm.com](https://www.ibm.com/docs/en/i/7.3?topic=documentation-pdf-files-manuals))

- **IBM Communications Server for Data Center Deployment on Linux**: Aquest manual proporciona una guia detallada sobre la implementació i administració de servidors de comunicacions d'IBM en entorns de CPD amb Linux. [IBM Communications Server for Data Center Deployment on Linux](https://www.ibm.com/support/pages/system/files/inline-files/czx00420.pdf)

