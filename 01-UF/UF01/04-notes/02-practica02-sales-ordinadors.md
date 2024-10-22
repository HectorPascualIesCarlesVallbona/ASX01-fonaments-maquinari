# Pràctica UF2 - Part 3

### Departament d'Informàtica - Institut Carles Vallbona  

### CFGS ASIX - Pràctiques

---

## Introducció

La tasca d’aquesta pràctica és desplegar dues sales amb un total de 300 ordinadors, dividits en dues configuracions de sistema operatiu diferents: **Ubuntu** i **Windows 10**. Aquests ordinadors s'utilitzaran per a una ponència sobre un nou programari d'empresa, i s'han de personalitzar segons uns requisits concrets.

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
   - Utilitza **VirtualBox** o **VMware** per crear una màquina virtual per a Ubuntu.
   - Assigna 4 GB de RAM, 2 processadors i 20 GB d’emmagatzematge. Aquesta configuració és adequada per a l’ús de les aplicacions sol·licitades.

2. **Instal·lació d'Ubuntu**:
   - Descarrega l'última versió d'Ubuntu (preferiblement la versió LTS).
   - Inicia la màquina virtual i selecciona l'opció **Instal·lació OEM** (si està disponible en la versió descarregada) per garantir que els usuaris finals puguin configurar la màquina en el primer inici.
   - Completa la instal·lació i accedeix com a "OEM user" per a la configuració i personalització del sistema.

3. **Personalització del Sistema**:
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

4. **Instal·lació de Programari**:
   - **GIMP**: Executa la comanda següent per instal·lar GIMP:

     ```bash
     sudo apt-get update
     sudo apt-get install gimp -y
     ```

   - **Guake**: Executa:

     ```bash
     sudo apt-get install guake -y
     ```

   - Configura Guake perquè s'iniciï automàticament quan l’usuari iniciï sessió (a *Preferències → Aplicacions d’inici*).

5. **Preparació d’Imatge de Clonació amb Clonezilla**:
   - Inicia **Clonezilla** en mode *Save Disk*, selecciona l'opció de crear una imatge del sistema instal·lat i personalitzat.
   - Guarda la imatge a un servidor de xarxa o unitat d’emmagatzematge extern.
   - Per al desplegament en massa, configura un servidor **DRBL** per utilitzar Clonezilla en mode multicast, permetent clonar totes les màquines de la sala alhora.

### B) Preparació de Windows 10 (Sala 2)

1. **Creació de la Màquina Virtual**:
   - Crea una màquina virtual amb **VirtualBox** o **VMware**, assignant 4 GB de RAM, 2 CPU i un disc dur de 25 GB.
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

## 2. Desplegament en Massa

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
