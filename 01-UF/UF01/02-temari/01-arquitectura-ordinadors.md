# Configuració d'equips i perifèrics: Arquitectura d'ordinadors

## Índex

- [Configuració d'equips i perifèrics: Arquitectura d'ordinadors](#configuració-dequips-i-perifèrics-arquitectura-dordinadors)
  - [Índex](#índex)
  - [1.1 Esquema i estructura d’un ordinador](#11-esquema-i-estructura-dun-ordinador)
    - [Gràfic esquemàtic d'un ordinador](#gràfic-esquemàtic-dun-ordinador)
  - [1.2 Elements funcionals i subsistemes](#12-elements-funcionals-i-subsistemes)
    - [CPU (Unitat Central de Procés)](#cpu-unitat-central-de-procés)
    - [Memòria](#memòria)
    - [Subsistema d'E/S](#subsistema-des)
    - [Gràfic del funcionament d'una CPU](#gràfic-del-funcionament-duna-cpu)
    - [Comandes de terminal per obtenir informació sobre la CPU](#comandes-de-terminal-per-obtenir-informació-sobre-la-cpu)
  - [1.3 Composició d’un sistema informàtic](#13-composició-dun-sistema-informàtic)
    - [1.3.1 Unitat central de procés (CPU)](#131-unitat-central-de-procés-cpu)
      - [Exemple de CPU](#exemple-de-cpu)
      - [Monitorització de la CPU en temps real](#monitorització-de-la-cpu-en-temps-real)
    - [1.3.2 Memòria](#132-memòria)
      - [Tipus de memòria](#tipus-de-memòria)
      - [Verificació de l'ús de memòria](#verificació-de-lús-de-memòria)
    - [1.3.3 Subsistema d'E/S](#133-subsistema-des)
      - [Verificació de dispositius USB connectats](#verificació-de-dispositius-usb-connectats)
      - [Llistat de dispositius PCI](#llistat-de-dispositius-pci)
  - [1.4 Components d'integració per assemblar equips informàtics](#14-components-dintegració-per-assemblar-equips-informàtics)
    - [1.4.1 Xassís](#141-xassís)
      - [Exemple](#exemple)
    - [1.4.2 Alimentació i refrigeració](#142-alimentació-i-refrigeració)
      - [Exemple](#exemple-1)
    - [1.4.3 Placa base](#143-placa-base)
  - [1.5 Configuració i verificació d'equips](#15-configuració-i-verificació-dequips)
    - [1.5.1 BIOS i UEFI](#151-bios-i-uefi)
      - [Exemple de configuració de la BIOS](#exemple-de-configuració-de-la-bios)
      - [Imatge de la configuració d'una UEFI moderna](#imatge-de-la-configuració-duna-uefi-moderna)
    - [1.5.2 Proves de rendiment i estabilitat](#152-proves-de-rendiment-i-estabilitat)
      - [Exemple d'ús](#exemple-dús)
    - [1.5.3 Monitoratge de temperatura](#153-monitoratge-de-temperatura)
      - [Verificació de temperatures en temps real](#verificació-de-temperatures-en-temps-real)
  - [1.6 Programari encastat de configuració d'un equip](#16-programari-encastat-de-configuració-dun-equip)
    - [1.6.1 Firmware en dispositius d'emmagatzematge](#161-firmware-en-dispositius-demmagatzematge)
      - [Exemples de firmware per SSD](#exemples-de-firmware-per-ssd)
      - [Optimització d'un SSD amb TRIM](#optimització-dun-ssd-amb-trim)
  - [1.7 Revisió i diagnòstic](#17-revisió-i-diagnòstic)
    - [1.7.1 Diagnòstic de maquinari](#171-diagnòstic-de-maquinari)
      - [Exemple d'ús](#exemple-dús-1)
    - [1.7.2 Diagnòstic de software](#172-diagnòstic-de-software)
  - [1.8 Tècniques de connexió i comunicació](#18-tècniques-de-connexió-i-comunicació)
    - [1.8.1 Connexions físiques](#181-connexions-físiques)
      - [Verificació d'estat de dispositius USB](#verificació-destat-de-dispositius-usb)
    - [1.8.2 Connexions sense fils](#182-connexions-sense-fils)
      - [Verificació de connexions de xarxa](#verificació-de-connexions-de-xarxa)
  - [1.9 Comunicacions entre sistemes informàtics](#19-comunicacions-entre-sistemes-informàtics)
    - [1.9.1 Protocols de comunicació](#191-protocols-de-comunicació)
      - [Exemple d'ús de SSH](#exemple-dús-de-ssh)
  - [1.10 Connexió a xarxes](#110-connexió-a-xarxes)
    - [1.10.1 Targeta de xarxa (NIC)](#1101-targeta-de-xarxa-nic)
      - [Exemple](#exemple-2)
    - [1.10.2 Configuració de xarxes](#1102-configuració-de-xarxes)
      - [Exemple de configuració de xarxa](#exemple-de-configuració-de-xarxa)

---

## 1.1 Esquema i estructura d’un ordinador

Un ordinador és un sistema complex compost per diversos subsistemes que treballen junts per executar tasques específiques. Els components clau d'un ordinador inclouen:

- **CPU (Unitat Central de Procés)**: El cervell de l'ordinador, que processa les instruccions i controla les operacions de tots els altres components.
- **Memòria**: Emmagatzema temporalment les dades que utilitzen els programes actius.
- **Subsistema d'E/S (Entrada i Sortida)**: Permet la comunicació entre l'ordinador i els dispositius externs com teclats, ratolins, pantalles i impressores.
- **Dispositius d'emmagatzematge**: Discos durs o unitats SSD que guarden dades de manera permanent.

### Gràfic esquemàtic d'un ordinador

![Esquema d'un ordinador](https://artoftesting.com/wp-content/uploads/2021/01/block-diagram-of-computer.jpg)

**Explicació del gràfic**: Aquest diagrama mostra els components bàsics d'un ordinador i com interactuen entre ells. La CPU es comunica amb la memòria i els dispositius d'E/S a través de busos que transporten dades i adreces. Els dispositius d'emmagatzematge es comuniquen directament amb la CPU per guardar o recuperar informació.

[Més informació detallada sobre l'estructura d'un ordinador](https://en.wikipedia.org/wiki/Computer_architecture).

---

## 1.2 Elements funcionals i subsistemes

Els ordinadors estan formats per diversos subsistemes funcionals que compleixen diferents funcions dins del sistema.

### CPU (Unitat Central de Procés)

La **CPU** és responsable de processar les instruccions dels programes. Dins de la CPU hi ha diferents components, com ara:

- **Unitat aritmètico-lògica (ALU)**: Processa operacions matemàtiques i lògiques.
- **Unitat de control (CU)**: Supervisa les operacions i coordina el flux de dades dins del sistema.

### Memòria

- **RAM (Random Access Memory)**: Emmagatzema les dades que s'estan utilitzant actualment.
- **ROM (Read-Only Memory)**: Conté informació permanent, com el programari que inicialitza el sistema.

### Subsistema d'E/S

Permet que l'ordinador es comuniqui amb dispositius externs com impressores, teclats, pantalles i altres perifèrics. Els protocols d'E/S asseguren que les dades es transfereixin de manera segura i eficient.

### Gràfic del funcionament d'una CPU

![CPU](https://computersciencewiki.org/images/1/1a/Cpu_diagram.png)

### Comandes de terminal per obtenir informació sobre la CPU

```bash
lscpu
```

Aquest comandament mostra informació detallada sobre la CPU, com el nombre de nuclis, la velocitat del rellotge, i altres detalls de configuració del processador.

![Comanda lscpu](https://geek-university.com/wp-content/images/linux/lscpu_command.jpg)

[Més informació sobre la CPU i els seus subsistemes](https://en.wikipedia.org/wiki/Central_processing_unit).

---

## 1.3 Composició d’un sistema informàtic

Un sistema informàtic està compost per diversos elements que treballen junts per processar dades i interactuar amb dispositius externs.

### 1.3.1 Unitat central de procés (CPU)

La **CPU** és responsable de processar les instruccions dels programes. Els components clau de la CPU inclouen:

- **ALU (Unitat aritmètica i lògica)**: Processa operacions matemàtiques i lògiques.
- **Unitat de control**: Coordina les instruccions de la CPU i gestiona els recursos del sistema.

#### Exemple de CPU

Un exemple d'una CPU moderna és l'**Intel Core i7**. Aquesta CPU té múltiples nuclis, que permeten executar diverses tasques alhora, i suporta tecnologies com la **hiperfilamentació**, que augmenta l'eficiència del processament.

![Imatge d'un processador Intel](https://cdn.mos.cms.futurecdn.net/JXxsTV5DK9xHBrivNHyFoD.jpg)

#### Monitorització de la CPU en temps real

```bash
top
```

Aquest comandament mostra l'ús en temps real de la CPU, memòria i altres recursos del sistema. És molt útil per veure quins processos consumeixen més recursos.

![Sortida de `top`](https://vitux.com/wp-content/uploads/2019/01/word-image-377.png)

[Més informació sobre CPU Intel Core i7](https://www.intel.com/content/www/us/en/products/sku/88191/intel-core-i7-6700k-processor-8m-cache-up-to-4-20-ghz.html).

### 1.3.2 Memòria

La **memòria** d'un sistema informàtic és responsable de guardar dades temporals o permanents.

#### Tipus de memòria

- **RAM (Random Access Memory)**: Emmagatzema temporalment les dades que s'utilitzen activament. Un exemple comú és la **DDR4 RAM**, que permet la transferència ràpida de dades entre la CPU i altres components.
- **ROM (Read-Only Memory)**: Guarda instruccions necessàries per al funcionament inicial del sistema, com el codi de la BIOS.

![Gràfic sobre tipus de memòria](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0c/ComputerMemoryHierarchy.svg/800px-ComputerMemoryHierarchy.svg.png)

#### Verificació de l'ús de memòria

```bash
free -h
```

Aquesta comanda mostra la quantitat de memòria RAM i SWAP disponible i utilitzada en el sistema, amb informació detallada per

 a cada part de la memòria.

![Sortida de `free -h`](https://atareao.es/wp-content/uploads/2016/05/terminal-free-memory.png)

[Més informació sobre tipus de memòria](https://en.wikipedia.org/wiki/Random-access_memory).

### 1.3.3 Subsistema d'E/S

El subsistema d'entrada/sortida (E/S) controla la interacció entre la CPU i els dispositius externs.

- **USB (Universal Serial Bus)**: Un protocol molt utilitzat per connectar dispositius com teclats, ratolins, impressores, i discos durs externs.
- **Ethernet**: Protocol per a la comunicació de xarxa, utilitzat per connectar ordinadors a xarxes locals (LAN).

#### Verificació de dispositius USB connectats

```bash
lsusb
```

Aquesta comanda llista tots els dispositius USB connectats a l'ordinador, mostrant detalls com el fabricant i l'ID del dispositiu.

![Sortida de `lsusb`](https://media.geeksforgeeks.org/wp-content/uploads/20190421121309/Screenshot-from-2019-04-21-11-42-47.png)

#### Llistat de dispositius PCI

```bash
lspci
```

Aquest comandament llista tots els dispositius PCIe instal·lats al sistema, incloent-hi targetes gràfiques, SSD NVMe, i altres dispositius de maquinari.

![Sortida de `lspci`](https://upload.wikimedia.org/wikipedia/commons/9/9a/Ict-innovation-LPI-Fig-101-1_5.png)

[Més informació sobre l'arquitectura PCIe](https://en.wikipedia.org/wiki/PCI_Express).

---

## 1.4 Components d'integració per assemblar equips informàtics

### 1.4.1 Xassís

El **xassís** és la caixa que conté tots els components físics d'un ordinador. Ha de tenir una bona ventilació per evitar el sobreescalfament dels components i ha de ser prou gran per allotjar tots els components necessaris.

#### Exemple

El **NZXT H510** és un xassís popular per als jugadors i entusiastes que necessiten espai per a una targeta gràfica gran i refrigeració líquida.

![Xassís NZXT H510](https://nzxt.com/assets/cms/34299/1615563443-h510-elite-white-black-kraken-x-system-purple-lighting-2.png?auto=format&fit=max&w=1200)

[Més informació sobre el xassís NZXT H510](https://www.nzxt.com/products/h510).

### 1.4.2 Alimentació i refrigeració

La **font d'alimentació (PSU)** proporciona corrent elèctric a tots els components de l'ordinador. Ha de ser prou potent per suportar tots els dispositius connectats.

#### Exemple

Una PSU de **750W** és recomanada per a equips que utilitzen una CPU d'alt rendiment i una targeta gràfica com la **NVIDIA RTX 3080**.

### 1.4.3 Placa base

La **placa base** és el component central que connecta tots els altres components d'un ordinador. Té ranures per a la CPU, la memòria RAM, dispositius d'emmagatzematge i targetes d'expansió com les targetes gràfiques.

---

## 1.5 Configuració i verificació d'equips

Quan es munta un ordinador, és important assegurar-se que els components estan correctament configurats i que l'equip és estable i funcional.

### 1.5.1 BIOS i UEFI

La **BIOS (Basic Input/Output System)** i la seva versió més moderna, **UEFI (Unified Extensible Firmware Interface)**, són responsables de la configuració inicial de l'ordinador. Quan s'encén el sistema, la BIOS o UEFI realitza una sèrie de proves i carrega el sistema operatiu des del dispositiu d'emmagatzematge.

#### Exemple de configuració de la BIOS

La configuració de la BIOS és crucial per ajustar el rendiment de l'ordinador. Per exemple, ajustar la velocitat de la RAM perquè funcioni a la freqüència especificada pel fabricant (per exemple, **DDR4 a 3200 MHz**).

- **Overclocking**: Algunes plaques base permeten ajustar la velocitat del processador (CPU) i la memòria RAM a través de la BIOS/UEFI per augmentar el rendiment, però això pot generar més calor i inestabilitat si no es fa correctament.
  
#### Imatge de la configuració d'una UEFI moderna

![Interfície UEFI](https://km-ap.asus.com/uploads/PhotoLibrarys/8a53fc79-6a00-4a96-8408-a7e886967aef/20240530113830775_EN_1.png)

[Més informació sobre BIOS i UEFI](https://en.wikipedia.org/wiki/BIOS).

### 1.5.2 Proves de rendiment i estabilitat

Després de configurar la BIOS, és essencial realitzar proves de rendiment i estabilitat per assegurar que l'ordinador pot gestionar càrregues de treball intensives sense problemes. Algunes eines populars inclouen:

- **Prime95**: Utilitzat per fer proves de tensió a la CPU. Aquesta eina simula càlculs matemàtics complexes per veure si la CPU pot mantenir-se estable sota càrrega.
  
- **MemTest86**: Prova la memòria RAM per detectar errors que podrien causar fallades del sistema.

#### Exemple d'ús

Un sistema de **jocs d'alt rendiment** amb un **Intel Core i9** i una **NVIDIA RTX 3080** ha de ser provat amb Prime95 per assegurar que no hi hagi sobreescalfament ni inestabilitat sota càrrega màxima.

[Més informació sobre Prime95](https://www.mersenne.org/download/).

### 1.5.3 Monitoratge de temperatura

El monitoratge de la temperatura és fonamental per assegurar que els components no s’escalfen excessivament, la qual cosa podria reduir el seu rendiment o fins i tot danyar-los.

- **HWMonitor** és una eina que permet veure les temperatures de la CPU, GPU i altres components.
  
#### Verificació de temperatures en temps real

```bash
sensors
```

Aquest comandament mostra les temperatures de la CPU i altres sensors del sistema. És útil per verificar que l'ordinador no estigui sobreescalfant-se.

![Sortida de `sensors`](https://www.tecmint.com/wp-content/uploads/2020/01/Check-CPU-and-GPU-Temperature-using-sensors.png)

[Més informació sobre HWMonitor](https://www.cpuid.com/softwares/hwmonitor.html).

---

## 1.6 Programari encastat de configuració d'un equip

El **firmware** és un programari específicament dissenyat per interactuar directament amb el maquinari de l'ordinador. Un exemple és la **BIOS/UEFI**, que controla els paràmetres de configuració bàsics del sistema.

### 1.6.1 Firmware en dispositius d'emmagatzematge

Els **SSD (Solid State Drives)** inclouen firmware propi que gestiona el control de les dades i les operacions d'escriptura i lectura. Aquest firmware ajuda a optimitzar el rendiment de l'SSD, així com a gestionar la seguretat de les dades a través de tecnologies com **TRIM**.

#### Exemples de firmware per SSD

Els **Samsung EVO 970** inclouen actualitzacions de firmware que milloren el rendiment de lectura/escriptura i corregeixen errors de seguretat detectats.

![SSD Samsung EVO](https://m.media-amazon.com/images/I/81YB-VvUnZL._AC_UF894,1000_QL80_.jpg)

#### Optimització d'un SSD amb TRIM

```bash
sudo fstrim -v /
```

Aquest comandament executa la comanda TRIM en un SSD, que ajuda a mantenir el rendiment de l'SSD eliminant blocs de dades innecessaris.

[Més informació sobre firmware per SSD](https://www.samsung.com/semiconductor/minisite/ssd/download/tools/).

---

## 1.7 Revisió i diagnòstic

La revisió i el diagnòstic d'un sistema són processos continus que ajuden a identificar problemes potencials abans que esdevinguin crítics.

### 1.7.1 Diagnòstic de maquinari

Per detectar problemes de maquinari, es poden utilitzar eines de diagnòstic com:

- **Intel Processor Diagnostic Tool**: Verifica si el processador està funcionant correctament.

- **CrystalDiskInfo**: Proporciona informació sobre l'estat dels dispositius d'emmagatzematge com HDDs i SSDs.

#### Exemple d'ús

Després de muntar un sistema, utilitzar **Intel Processor Diagnostic Tool** per verificar que el processador no té errors de fabricació o mal funcionament.

![Intel Processor Diagnostic Tool](https://www.intel.com/content/dam/support/us/en/images/processors/94564-img1.png)

[Més informació sobre Intel Processor Diagnostic Tool](https://www.intel.com/content/www/us/en/download/15951/intel-processor-diagnostic-tool.html).

### 1.7.2 Diagnòstic de software

El diagnòstic de programari inclou la comprovació de l'estat del sistema operatiu i la correcció d'errors. Eines com **sfc /scannow** a Windows poden ser utilitzades per buscar i reparar fitxers de sistema danyats.

---

## 1.8 Tècniques de connexió i comunicació

Els ordinadors es connecten a altres dispositius a través de diversos tipus de connexions.

### 1.8.1 Connexions físiques

- **USB (Universal Serial Bus)**: Permet la connexió de dispositius com discos externs, teclats i ratolins.
  
- **PCIe (Peripheral Component Interconnect Express)**: Permet la connexió de components com targetes gràfiques i SSDs a alta velocitat.

#### Verificació d'estat de dispositius USB

```bash
lsusb
```

Aquest comandament llista tots els dispositius USB connectats, proporcionant informació sobre els dispositius de maquinari connectats al sistema.

### 1.8.2 Connexions sense fils

- **Wi-Fi**: Permet connectar dispositius a xarxes sense fils. Les tecnologies modernes com **Wi-Fi 6** ofereixen velocitats més altes i una millor gestió de múltiples dispositius.
  
- **Bluetooth**: Utilitzat per a la connexió de dispositius com teclats, ratolins, i auriculars sense fils.

#### Verificació de connexions de xarxa

```bash
nmcli dev status
```

Aquesta comanda mostra l'estat de les connexions de xarxa, incloent dispositius Ethernet i Wi-Fi, i si estan connectats o no.

![Sortida de `nmcli`](https://www.linuxtechi.com/wp-content/uploads/2022/01/nmcli-command-output.png)

[Més informació sobre Wi-Fi 6](https://www.intel.com/content/www/us/en/wireless-network/wi-fi-6.html).

---

## 1.9 Comunicacions entre sistemes informàtics

Els sistemes informàtics es comuniquen mitjançant xarxes. Aquesta comunicació permet la transferència de dades entre dispositius o sistemes, ja sigui en una xarxa local (LAN) o a través d'internet.

### 1.9.1 Protocols de comunicació

- **TCP/IP (Transmission Control Protocol/Internet Protocol)**: És el conjunt de protocols estàndard per a la transmissió de dades a través de xarxes.
  
- **SSH (Secure Shell)**: És un protocol que permet connectar-se de manera remota a un sistema de manera segura.

#### Exemple d'ús de SSH

```bash
ssh user@192.168.1.100
```

Aquesta comanda permet connectar-se de manera remota a un altre sistema mitjançant SSH. És útil per a l'administració remota de servidors o altres ordinadors a la xarxa.

![SSH Connection](https://media.geeksforgeeks.org/wp-content/uploads/20230425123007/65.webp)

[Més informació sobre SSH](https://en.wikipedia.org/wiki/Secure_Shell).

---

## 1.10 Connexió a xarxes

### 1.10.1 Targeta de xarxa (NIC)

Una **targeta de xarxa (Network Interface Card)** permet que un ordinador es connecti a una xarxa, ja sigui per cable o sense fil.

#### Exemple

Un ordinador amb una **targeta de xarxa Ethernet gigabit** pot transferir dades a una velocitat de fins a 1 Gbps, la qual cosa és essencial per a aplicacions que requereixen molta amplada de banda, com el streaming de vídeo en alta definició.

### 1.10.2 Configuració de xarxes

La configuració d'una xarxa implica l'assignació d'adreces IP, la configuració de passarel·les (gateways), i la gestió de la seguretat mitjançant **firewalls**.

#### Exemple de configuració de xarxa

```bash
ifconfig eth0 192.168.1.100 netmask 255.255.255.0
route add default gw 192.168.1.1
```

Aquest exemple mostra com assignar una adreça IP estàtica a una interfície de xarxa en un sistema Unix/Linux.

---
