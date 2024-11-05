# 02 - Pràctica02 - SALES ORDINADORS

## Anotacions per si esteu perduts

### Programes per la instal·lació i personalització dels sistemes operatius

Haureu d'utilitzar eines com VirtualBox per crear les màquines virtuals amb Ubuntu 18 i Windows 10.

### Personalització d'imatges de sistema

1. **Clonezilla**: Pot ser utilitzat per a la clonació de sistemes un cop s'ha creat la imatge model, i desplegar-la de forma massiva als 150 ordinadors per sala.
2. **Sysprep (Windows)**: Per a Windows 10, l'eina Sysprep permet crear imatges de sistema personalitzades, com les que s'utilitzen en OEM per preconfigurar els ordinadors.
3. **OEM preinstallation kit (OPK) per Windows**: Aquesta eina permet crear versions personalitzades de Windows per a la seva distribució.

### Programari de gestió d'imatges

Per la part de Linux, es pot utilitzar **partclone** o altres eines incloses amb **Clonezilla** per crear imatges de disc personalitzades d'Ubuntu, amb tot el programari necessari ja instal·lat.

### Programes addicionals

1. **GIMP**: Ha de ser instal·lat en ambdós sistemes operatius per la personalització del fons de pantalla.
2. **Guake**: En Ubuntu, aquest terminal desplegable és necessari per facilitar l'accés al terminal.
3. **VLC**: En Windows 10, aquest reproductor ha d'estar inclòs com a part del paquet de programari preinstal·lat.

### OEM

**OEM** (Original Equipment Manufacturer) és un terme utilitzat per referir-se a fabricants d'equipament original, però també té un significat específic en el context de sistemes operatius com Windows o Ubuntu. En aquest cas, una **instal·lació OEM** fa referència a una instal·lació de sistema operatiu que és preconfigurada per un fabricant o administrador per ser distribuïda a diversos usuaris finals. El sistema està personalitzat però permet que, en el primer inici de sessió, l'usuari final completi certs passos com la creació d'un nom d'usuari i contrasenya.

#### Detalls de les instal·lacions OEM

1. **Per què es fa servir?**
   - Els fabricants d'ordinadors (com Dell, HP, Lenovo, etc.) fan servir instal·lacions OEM per preconfigurar els sistemes operatius que venen amb els seus dispositius. Això permet que els dispositius arribin als usuaris amb tot el programari preinstal·lat, les configuracions ajustades, però deixant passos senzills perquè l'usuari final els completi.
   - En projectes com el que planteges, utilitzar instal·lacions OEM facilita la distribució massiva d'ordinadors o sistemes personalitzats, ja que et permet preconfigurar els ordinadors amb programari, fons de pantalla, i altres elements, però deixa l'última configuració (com ara l'usuari i contrasenya) per a l'usuari final.

2. **Característiques principals d'una instal·lació OEM**:
   - **Preconfiguració per part del fabricant o administrador**: Es configura el sistema amb programes, fons de pantalla, controladors, etc.
   - **Personalització d'usuari final**: Quan l'usuari final arrenca la màquina per primera vegada, aquest completa la configuració bàsica (com el nom d'usuari i la contrasenya).
   - **Utilitat en entorns empresarials o escolars**: En desplegaments massius, com a les aules o oficines, la instal·lació OEM facilita el manteniment d'un conjunt homogeni de màquines amb configuracions predefinides, reduint el temps de configuració manual per part de l'usuari final.

#### Exemple

Quan instal·les un sistema operatiu Ubuntu o Windows en mode **OEM**, pots preparar la màquina amb tot el programari que vulguis (com GIMP, VLC, Guake, etc.), configurar el fons de pantalla, i fins i tot assignar noms de host als equips. L'usuari final, però, només haurà de completar els passos restants quan engegui l'ordinador per primera vegada, com ara crear el seu compte d'usuari i contrasenya.

---

## Resum del flux d'implementació

### 1. **Investigació prèvia**

- Realitzar una **fase d'investigació** per determinar quines eines i mètodes s’utilitzaran per desplegar els sistemes operatius de manera eficient.
- Considerar eines com **Sysprep** per a Windows i **Clonezilla** per a Ubuntu per facilitar el desplegament massiu i la personalització.

### 2. **Creació de màquines virtuals**

- Preparar **dues màquines virtuals** per a cada sistema:
  - Una amb **Ubuntu**, amb tots els requisits.
  - Una amb **Windows 10**, també amb tots els requisits.
- Aquestes màquines virtuals seran les imatges mestres que es faran servir per a la clonació en massa.

### 3. **Personalització de la instal·lació**

- **Ubuntu** (Sala 1: "Linus, the wild penguin"):
  - Instal·lar **Ubuntu** en mode **OEM**, perquè els usuaris només hagin d'introduir el seu nom i contrasenya.
  - Personalitzar el **fons de pantalla** amb el nom de l'alumne i instal·lar **GIMP** i **Guake**.
  - Assignar els noms de host com `wildpenguin[Cognom1]1`, `wildpenguin[Cognom1]2`.

- **Windows 10** (Sala 2: "The fabulous meadow of bill gates"):
  - Instal·lar **Windows 10** en mode **OEM**.
  - Personalitzar el **fons de pantalla** amb el nom de l'alumne i instal·lar **VLC**.
  - Assignar els noms de host com `billy_meadow_[Cognom1]1`, `billy_meadow_[Cognom1]2`.

### 4. **Execució del desplegament** (Punt 5)

- **Implementar el mètode decidit** per preparar els sistemes operatius segons els requisits.
- Utilitzar les imatges creades a les màquines virtuals per desplegar els **150 ordinadors amb Ubuntu** i els **150 amb Windows 10** de manera massiva, fent servir eines de clonació.

---

## Introducció

La tasca d’aquesta pràctica és desplegar dues sales amb un total de 300 ordinadors, dividits en dues configuracions de sistema operatiu diferents: **Ubuntu** i **Windows 10**. Aquests ordinadors s'utilitzaran per a una ponència sobre un nou programari d'empresa, i s'han de personalitzar segons uns requisits concrets.

---

## Requisits de la Pràctica

### Sales i Sistemes Operatius

- **Sala 1 - Linus, the wild penguin**: 150 ordinadors amb Ubuntu.
- **Sala 2 - The fabulous meadow of Bill Gates**: 150 ordinadors amb Windows 10.
  
### Requisits Generals de Personalització

1. **Configuració OEM**: Les màquines han de venir preparades perquè l'usuari final només hagi de crear el nom d'usuari i la contrasenya la primera vegada que inicia el sistema.
2. **Fons de pantalla personalitzat**: El fons de pantalla ha d'incloure el teu nom i cognom.
3. **Programes Instal·lats**:
   - **Ubuntu**: GIMP i Guake.
   - **Windows 10**: GIMP i VLC.
4. **Noms dels Hosts**:
   - **Ubuntu**: "wildpenguin[COGNOM1]1" fins a "wildpenguin[COGNOM1]150".
   - **Windows 10**: "billy_meadow_[COGNOM1]1" fins a "billy_meadow_[COGNOM1]150".

---

## 1. Configuració de les Màquines Virtuals

### A) Preparació d’Ubuntu (Sala 1)

1. **Creació de la Màquina Virtual**:
   - Utilitza **VirtualBox** per crear una màquina virtual per a Ubuntu.
   - Assigna 4 GB de RAM, 2 processadors i 20 GB d’emmagatzematge. Aquesta configuració és adequada per a l’ús de les aplicacions sol·licitades.

2. **Instal·lació d'Ubuntu**:
   - Descarrega l'última versió d'Ubuntu (preferiblement la versió LTS).
   - Personalitza per a OEM
     - Obre la terminal i crea un script nou en el directori /etc/profile.d/ per tal que s'executi en el primer inici de sessió

      ```bash
         sudo nano /etc/profile.d/set_hostname.sh
      ```

     - Afegeix aquest contingut a l’script. Després desa i tanca

      ```bash
         #!/bin/bash
         if [ ! -f /etc/hostname_set ]; then
            echo "Introdueix el teu primer cognom per configurar el nom de host:"
            read COGNOM1
            HOSTNAME="wildpenguin${COGNOM1}"
            sudo hostnamectl set-hostname "$HOSTNAME"
            echo "$HOSTNAME" | sudo tee /etc/hostname
            sudo sed -i "s/127.0.1.1.*/127.0.1.1 $HOSTNAME/" /etc/hosts
            sudo touch /etc/hostname_set
            echo "Nom de host establert a $HOSTNAME. Reinicia per aplicar els canvis."
         fi
      ```

      - Fes Executable l'script

      ```bash
         sudo chmod +x /etc/profile.d/set_hostname.sh
      ```

   - Com Funciona l'script
      Quan un usuari iniciï sessió per primera vegada:
       - L’script demanarà el primer cognom de l'usuari.
       - El nom de host es crearà amb el format wildpenguin[Cognom1].
       - El sistema desarà el nou nom de host i evitarà que l’script s’executi en futures iniciades de sessió.

1. **Personalització del Sistema**:
   - **Fons de Pantalla**: Crea un fons de pantalla amb el teu nom i cognom utilitzant GIMP. Un cop dissenyat, guarda'l com a **wallpaper.png** a la carpeta d'imatges i selecciona’l com a fons predeterminat a *Configuració → Aparença → Fons de pantalla*.
   - **Nom del Host**:
     - Obre el terminal i executa:

       ```bash
       sudo hostnamectl set-hostname wildpenguin[COGNOM1]
       ```

     - Per assegurar que el canvi es manté després del reinici, edita `/etc/hostname` i `/etc/hosts` amb el nom desitjat:

       ```bash
       sudo nano /etc/hostname
       sudo nano /etc/hosts
       ```

2. **Instal·lació de Programari**:
   - **GIMP**: Executa la comanda següent per instal·lar GIMP:

     ```bash
     sudo apt-get update
     sudo apt-get install gimp -y
     ```

   - **Guake**: Executa:

     ```bash
     sudo apt-get install guake -y
     ```

   - **Configura** Guake perquè s'iniciï automàticament quan l’usuari iniciï sessió:

      - Executa aquesta comanda per crear una entrada d'inici automàtic per a Guake:

      ```bash
      mkdir -p ~/.config/autostart
      echo -e "[Desktop Entry]\nType=Application\nExec=guake\nHidden=false\nNoDisplay=false\nX-GNOME-Autostart-enabled=true\nName=Guake\nComment=Start Guake at login" > ~/.config/autostart/guake.desktop
      ```

      Aquesta comanda crea un fitxer `.desktop` a la carpeta `~/.config/autostart` que farà que Guake s'iniciï automàticament en iniciar sessió.

     - Verifica que l'arxiu s'hagi creat correctament:

      ```bash
      cat ~/.config/autostart/guake.desktop
      ```

3. **Preparació d’Imatge de Clonació amb Clonezilla**:
   - Instal.lació Clonezilla:
     - Descarrega l'última versió de Clonezilla Live en format ISO des de la seva [pàgina oficial](https://clonezilla.org/downloads.php).

   - Adjunta la ISO a la MV:
     - A VirtualBox, selecciona la MV que vols clonar i vés a **Configuració > Emmagatzematge**.
     - Afegeix la ISO de Clonezilla com a unitat òptica en IDE fent clic al controlador òptic i seleccionant **Afegeix una imatge de disc òptic**.
      En VirtualBox, és recomanable afegir la ISO de Clonezilla com a unitat òptica en el controlador IDE. Això és perquè les unitats òptiques solen estar configurades en IDE de manera predeterminada, i alguns sistemes poden tenir problemes per detectar-les correctament si es troben en un controlador SATA.

   - Inicia la màquina virtual des de la ISO:
     - Reinicia la MV. Amb la ISO de Clonezilla adjunta arrencarà directament en Clonezilla.

   - Crea la imatge del sistema:
     - Selecciona la primera opció per arrencar en mode "Clonezilla live".
     Aquí tens una guia pas a pas per crear una imatge del sistema amb Clonezilla dins de VirtualBox, detallant totes les
     - Selecciona l'idioma:
       - Escull l’idioma amb les fletxes de direcció (en el meu cas, `English`).
       - A la següent pantalla, selecciona `Keep the default keyboard layout`.

     - A la pantalla que diu "Start Clonezilla", selecciona aquesta mateixa per començar.
     - Selecciona l'opció `device-image` (dispositiu a imatge). Això permet crear una imatge del sistema per guardar-la en un dispositiu extern o una ubicació de xarxa.
     - Clonezilla et preguntarà on vols guardar la imatge. Seleccionarem la següent:
       - `local_dev`: per desar la imatge en un dispositiu USB o disc dur extern connectat a la màquina virtual.
     - Seleccionat `local_dev`:
       - Connecta el dispositiu USB o unitat externa abans de continuar. A VirtualBox, has d'assignar la unitat al sistema virtual per assegurar que estigui disponible. Si tens problemes per detectar l'unitat USB consulta [aquest document](00-problemes-deteccio-usb-a-MV.md)

       - Un cop connectat, clicka `Enter` per escanejar i detectar els dispositius.
       - Selecciona el dispositiu de destinació (la unitat USB o disc dur extern).
       - Navega fins a la carpeta on vols guardar la imatge i selecciona-la.
     - Clonezilla et demanarà que introdueixis un nom per a la carpeta on es guardarà la imatge. Pots acceptar el nom predeterminat o introduir-ne un de nou.
     - Mode de treball: selecciona l’opció `Beginner` per fer una configuració més senzilla i evita errors
     - Selecciona "Save disk" per guardar la imatge completa del disc
     - Tria el disc font: Clonezilla mostrarà una llista de discos disponibles a la màquina virtual. Selecciona el disc que vols clonar (normalment serà `sda`).
     - Clonezilla et demanarà diverses opcions per a la configuració d’imatge:
       - Escull `Skip checking/repairing source file system` (omitir verificació/reparació del sistema de fitxers) per accelerar el procés.
     - Comença la clonació: Clonezilla crearà la imatge i la guardarà a la destinació seleccionada. Aquest procés pot trigar uns minuts o hores, depenent de la mida del disc.
     - Un cop finalitzat el procés, Clonezilla et donarà l'opció de reiniciar o apagar el sistema.

- Per al desplegament en massa, configura un servidor **DRBL** per utilitzar Clonezilla en mode multicast, permetent clonar totes les màquines de la sala alhora.

### B) Preparació de Windows 10 (Sala 2)

1. **Creació de la Màquina Virtual**:
   - Crea una màquina virtual amb **VirtualBox**, assignant 4 GB de RAM, 2 CPU i un disc dur de 25 GB.
   - Afegeix el fitxer ISO de Windows 10 i inicia la instal·lació.

2. **Instal·lació de Windows 10**:
   - Completa la instal·lació i selecciona la configuració **OEM** per assegurar que l’usuari pugui crear el seu perfil al primer inici.
   - Un cop instal·lat, accedeix a l'usuari administrador per configurar el sistema i afegir els programes requerits.

3. **Personalització del Sistema**:
   - **Fons de Pantalla**: Crea un fons de pantalla amb el teu nom i cognom a GIMP. A *Configuració → Personalització → Fons de pantalla*, estableix aquest fons com a predeterminat.
   - **Nom del Host**:
     - Accedeix a *Sistema → Configuració avançada del sistema → Nom de l'equip* i estableix el nom de l'equip segons el format "billy_meadow_[COGNOM1]".

4. **Instal·lació de Programari**:
   - **VLC**: Baixa i instal·la VLC mitjançant la comanda de PowerShell:

     ```powershell
     winget install --id VideoLAN.VLC -e
     ```

   - **GIMP**: Instal·la GIMP mitjançant:

     ```powershell
     winget install --id GIMP.GIMP -e
     ```

   - Verifica que ambdues aplicacions funcionin correctament.

5. **Preparació d’Imatge de Clonació amb Acronis True Image**:
   - Descarrega i executa **Acronis True Image** per crear una imatge del sistema personalitzat.
   - Emmagatzema la imatge al servidor de xarxa per facilitar el procés de clonació en massa.
   - Utilitza el mode multicast d’Acronis per desplegar la imatge en els 150 ordinadors simultàniament.

---

## 2. Desplegament en Massa (pràctica posterior)

### Utilització de DRBL amb Clonezilla i Acronis True Image

1. **Configuració del Servei Multicast**:
   - **Clonezilla**: Configura el servidor **DRBL** per clonar la imatge d'Ubuntu de manera simultània a tots els ordinadors de la sala. Els ordinadors han d'estar connectats a una xarxa que suporti multicast i PXE.
   - **Acronis True Image**: Crea una sessió multicast des del servidor central amb la imatge de Windows 10. Això permetrà que totes les màquines es clonin al mateix temps, estalviant temps i assegurant una instal·lació uniforme.

### Procediment de Clonació

1. **Clonació de Sala 1 (Ubuntu)**:
   - Inicia el servei DRBL i accedeix al menú de Clonezilla.
   - Selecciona l’opció de desplegament multicast per carregar la imatge a tots els ordinadors. Assegura’t que el nom de cada màquina s'assigni correctament en el procés de clonació.

2. **Clonació de Sala 2 (Windows 10)**:
   - Amb **Acronis True Image**, configura una sessió de restauració en massa amb l’opció de *Deploy to Multiple Devices*.
   - Assegura’t que els noms dels equips es puguin configurar al primer inici, o utilitza un script de PowerShell per canviar els noms de cada màquina després del primer arrencament.

---

## 3. Verificació i Validació

1. **Primera Iniciació**:
   - Verifica que cada ordinador s'iniciï correctament i que l'usuari pugui crear el seu perfil.
   - Comprova que el **fons de pantalla** amb el teu nom aparegui en iniciar sessió.
2. **Prova de Funcionalitat del Programari**:
   - Obre **GIMP** i **Guake** (en Ubuntu) i verifica que funcionen correctament.
   - Assegura’t que **VLC** i **GIMP** (en Windows) funcionin també de manera òptima.
3. **Nom dels Hosts**:
   - Revisa els noms dels hosts per confirmar que segueixen el format establert per a cada sala i que són coherents amb la configuració.
