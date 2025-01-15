# OPCIONS D'ARRENCADA DEL SISTEMA

---

## Índex
1. [Introducció a l'arrencada del sistema](#1-introduccio-a-larrencada-del-sistema)
2. [Fases del procés d'arrencada](#2-fases-del-proces-darrencada)
   - [Inicialització del hardware (BIOS/UEFI)](#21-inicialitzacio-del-hardware-biosuefi)
   - [Bootloader (Gestor d'arrencada)](#22-bootloader-gestor-darrencada)
   - [Kernel i càrrega del sistema operatiu](#23-kernel-i-carrega-del-sistema-operatiu)
3. [Arxius i configuracions rellevants](#3-arxius-i-configuracions-rellevants)
   - [Configuració del bootloader](#31-configuracio-del-bootloader-afegir-una-nova-entrada-al-grub)
   - [Sistemes de fitxers rellevants](#32-sistemes-de-fitxers-rellevants)
   - [MBR i GPT](#33-mbr-i-gpt)

---

### **1. Introducció a l'arrencada del sistema**

#### **Punts clau:**
- **Definició**: És el procés seqüencial de posar en funcionament tots els components de hardware i software necessaris perquè el SO funcioni correctament.
- **Importància**: Una arrencada exitosa garanteix que el SO pugui interactuar amb el hardware i executar software.
- **Etapes principals**:
  1. Inicialització del hardware (BIOS/UEFI).
  2. Inici del bootloader.
  3. Loading del kernel i inicialització del sistema operatiu.

---

### **2. Fases del procés d'arrencada**

#### **2.1. Inicialització del hardware (BIOS/UEFI)**

- **BIOS (Basic Input/Output System)**:
  - És un firmware que s'executa al primer nivell quan l'ordinador s'engega.
  - Funcions:
    - Autotest d'engegada (Power-On Self Test - POST) per verificar el funcionament del hardware bàsic.
    - Cerca d'un dispositiu d'arrencada: disc dur, SSD, USB, etc.
  - Limitacions:
    - Només pot gestionar discos durs de fins a 2 TB.
    - Absència de `Secure Boost`
    - Temps arrencada més lent
    - Limitacions de configuració 

- **UEFI (Unified Extensible Firmware Interface)**:
  - Successor de BIOS amb millores significatives.
  - Avantatges:
    - Compatibilitat amb discs de més de 2 TB.
    - Temps d'arrencada més ràpid.
    - Suport per interfícies gràfiques i mode segur (Secure Boot).
    - Programable i més flexible.

#### **2.2. Bootloader (Gestor d'arrencada)**
- **Definició**: El bootloader és un programa que carrega el sistema operatiu al hardware després de la inicialització del firmware (inicialització hardware).
- Tipus de bootloaders:
    - **GRUB (Grand Unified Bootloader)**:
        - **GRUB Legacy**: Versió antiga.
        - **GRUB2**: Actual, suporta configuracions avançades com ara la gestió de múltiples sistemes operatius.
        - Exemple de fitxer de configuració:
        ```bash
        /etc/default/grub
        ```
        Configuració bàsica:
        ```bash
            # Defineix entrada per defecte del menú de GRUB (0 és la primera entrada)
            # 0: Ubuntu, with Linux 5.15.0-56-generic
            # 1: Ubuntu, with Linux 5.15.0-56-generic (recovery mode)
            # 2: Windows Boot Manager (on /dev/sda1)
            # 3: Memory test (memtest86+)

            GRUB_DEFAULT=0 

            # Temps espera en segons abans de carregar entrada per defecte
            GRUB_TIMEOUT=5

            # Opcions de línia de comandes per al kernel Linux
            GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
        ```
        - En aquest exemple:
            - Veus una pantalla gràfica d'arrencada en comptes d'un conjunt de missatges tècnics.
            - Tens 5 segons per seleccionar una altra entrada al menú del GRUB si no vols carregar la primera entrada per defecte.
    - **LILO (Linux Loader)**:
        - Utilitzat en sistemes antics.
        - Menys flexible que GRUB.
    - **Altres gestors**:
        - Windows Boot Manager: Per arrencar Windows.
        - systemd-boot: Integrat amb `systemd`.

#### **2.3. Kernel i càrrega del sistema operatiu**
- **Kernel**: El nucli del sistema operatiu que gestiona recursos i processos.
- **Càrrega**:
  1. El bootloader transfereix el control al kernel.
  2. El kernel:
     - Muntatge del sistema de fitxers arrel.
     - Execució dels processos inicials com `init` o `systemd`.

---

### **3. Arxius i configuracions rellevants**

#### **3.1. Configuració del bootloader: afegir una nova entrada al GRUB**

1. **Fitxer `/etc/grub.d/40_custom`**:
   - És un fitxer dissenyat per afegir entrades personalitzades al menú de GRUB.
   - Per exemple, si tens un sistema operatiu en una partició especial o vols una opció de recuperació manual, pots definir-lo aquí.

2. **Exemple d'entrada personalitzada**:
   Suposem que vols afegir una entrada per arrencar un sistema des de `/dev/sda2`:

   Editem el fitxer `/etc/grub.d/40_custom`:
   ```bash
   sudo nano /etc/grub.d/40_custom
   ```

   Afegim una nova entrada:
   ```bash
   menuentry "My Linux OS" {    # Nom de l'entrada que apareixerà al menú del GRUB
    set root=(hd0,2)            # Defineix la partició on es troben els fitxers d'arrencada
                                # (hd0 = primer disc, 2 = segona partició)

    linux /vmlinuz-linux root=/dev/sda2 ro  # Carrega el kernel del sistema operatiu
                                            # - /vmlinuz-linux: Ruta al fitxer del kernel
                                            # - root=/dev/sda2: Especifica la partició arrel (on està instal·lat el # sistema)
                                            # - ro: Muntatge inicial del sistema de fitxers en mode "només lectura"
                                            
    initrd /initramfs-linux.img             # Carrega la imatge d'inicialització (initrd)
                                            # - /initramfs-linux.img: Ruta a la imatge amb controladors i fitxers
                                            #   necessaris per muntar la partició arrel
    }

   ```

3. **Actualitzar la configuració del GRUB**:
   Un cop afegides les noves entrades, és necessari regenerar la configuració del GRUB perquè reconegui els canvis. Executa:
   ```bash
   sudo update-grub
   ```

   Aquest comandament:
   - Escaneja tots els dispositius d'arrencada disponibles.
   - Genera el fitxer final de configuració: `/boot/grub/grub.cfg`, que és el que utilitza GRUB per mostrar el menú.


#### **3.2. Sistemes de fitxers rellevants**
- **/boot**:
  - Conté el kernel i els fitxers necessaris per arrencar.
  - Fitxers importants:
    - `vmlinuz`: fitxer del nucli del sistema operatiu Linux. És el cor del sistema operatiu i s'encarrega de gestionar el hardware i proporcionar serveis essencials als programes.
    - `initrd`: Initial RAM Disk - és una imatge que conté un sistema de fitxers temporal carregat a la **memòria RAM** durant la fase inicial de l'arrencada d'un sistema operatiu Linux. S'encarrega de preparar el sistema per muntar el sistema de fitxers arrel definitiu i transferir el control al kernel.
- **/etc/fstab**:
  - **Definició**: File Systems Table - és un fitxer de configuració en sistemes Linux i Unix que conté una llista de sistemes de fitxers que el sistema operatiu ha de muntar automàticament durant l'arrencada o que estan disponibles per ser muntats manualment.
  - **Funcionalitats**:
   - Defineix quines particions, discos, dispositius o sistemes de fitxers remots s'han de muntar en punts concrets del sistema (com `/`, `/home`, o `/mnt/backup`).
   - **Exemple**:
   ```bash
   # <dispositiu>         <punt_de_muntatge>   <sistema_fitxers>  <opcions>        <dump>  <pass>
    UUID=1234-5678         /                   ext4               defaults         1       1
    UUID=abcd-efgh         /home               ext4               defaults         0       2
    UUID=1122-3344         swap                swap               sw               0       0
    tmpfs                  /tmp                tmpfs              defaults,noexec  0       0
   ```
 
#### **3.3. MBR i GPT**
1. **MBR (Master Boot Record)**:
    - **Definició**: És una estructura especial situada al començament d’un disc dur o SSD (concretament al primer sector del disc, sector 0). És una part fonamental per arrencar sistemes en dispositius particionats amb aquest esquema.
    - **Funcionalitats**:
        - Normalment, GRUB o altres bootloaders utilitzen el MBR per començar el procés d’arrencada.
        - Inclou informació sobre les particions del disc (mida, tipus, ubicació). Aquesta taula pot definir fins a 4 particions primàries.
    - **Limitacions**:
        - Només pot adreçar fins a **2 TB** de capacitat de disc
        - Només pot definir 4 particions primàries com a màxim. Això es deu a la mida limitada de la taula de particions (64 bytes), que pot descriure 4 entrades de 16 bytes cadascuna.

        💡 Si necessites més de 4 particions, pots convertir una partició primària en una **partició estesa**, que actua com a contenidor per a particions **lògiques**. Si necessites més de 4 particions, pots convertir una partició primària en una **partició estesa**, que actua com a contenidor per a particions **lògiques**.
        - Si l’MBR es corromp, pot ser difícil recuperar les dades del disc
2. **GPT (GUID Partition Table)**:
    - **Definició**: És un esquema modern de particionament de discos que forma part de l’especificació **UEFI** (Unified Extensible Firmware Interface). És una evolució del MBR (Master Boot Record) i supera moltes de les seves limitacions, com ara la mida màxima de disc i el nombre de particions.
    - **Funcionalitats**: 
        - Emmagatzematge de particions. Permet crear més de 4 particions primàries sense necessitat de particions esteses.
        - Múltiples còpies de seguretat. Emmagatzema còpies redundants de la taula de particions al començament i al final del disc, millorant la recuperació en cas de corrupció.
        - Identificació única. Cada partició té un **GUID (Globally Unique Identifier)**, que és un identificador únic global per a aquesta partició

3. **Com verificar si un disc utilitza GPT o MBR**

- Utilitza eines com **`fdisk`**, **`parted`** o **`lsblk`** per comprovar l'esquema de particions.

#### Exemple amb `parted`:
```bash
sudo parted /dev/sda print
```
Sortida:
```
Partition Table: gpt
```

---

### **4. Problemes comuns i solucions**

#### **4.1. Errors més habituals**
- "Boot Device Not Found".
- Falta del fitxer `grub.cfg` o mal configurat.

#### **4.2. Eines de recuperació**
- **GRUB Rescue**:
  - Comandes per recuperar GRUB:
    ```bash
    grub> set root=(hd0,1)
    grub> linux /vmlinuz root=/dev/sda1
    grub> initrd /initrd.img
    grub> boot
    ```
- **Live CD/USB**:
  - Recuperar el bootloader amb una distribució live:
    ```bash
    sudo grub-install /dev/sda
    sudo update-grub
    ```
