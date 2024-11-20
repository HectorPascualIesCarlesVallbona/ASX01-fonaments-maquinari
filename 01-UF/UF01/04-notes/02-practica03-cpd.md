# Pràctica UF2 - Part 4: Implementació del Sistema de Desplegament amb DRBL Clonezilla

---

## 1. Preparació de l'Entorn de Proves

### A) Instal·lació i Configuració de les Màquines Virtuals

L'entorn de proves tindrà tres màquines virtuals:

- Un [**servidor DRBL**](02-practica03-DRBL.md) per gestionar la clonació en mode multicast.
- Dos **clients** que rebran la imatge clonada d'Ubuntu.

#### 1.1 Configuració del Servidor DRBL

1. **Creació de la Màquina Virtual del Servidor DRBL**:
   - Obre **VirtualBox** i crea una nova màquina virtual per al servidor.
   - **Nom**: Assigna un nom (p. ex., `Servidor_DRBL`).
   - **Sistema Operatiu**: Tria Linux i la versió adequada (p. ex., Ubuntu 64-bit).
   - **Recursos**: Assigna 4 GB de RAM, 2 CPU i un disc dur de 20 GB per garantir un rendiment adequat.

2. **Instal·lació del Sistema Operatiu (Ubuntu o DRBL Live)**:
   - Inicia la màquina virtual i carrega la ISO d'Ubuntu o DRBL Live.
   - Segueix el procés d'instal·lació fins a completar-lo i després reinicia la màquina virtual.

3. **Instal·lació de DRBL i Clonezilla en Ubuntu**:
   - Un cop el sistema estigui operatiu, obre el terminal.
   - Actualitza els paquets amb:

     ```bash
     sudo apt-get update
     sudo apt-get upgrade
     ```

   - Instal·la DRBL amb Clonezilla amb la següent comanda:

     ```bash
     sudo apt-get install drbl clonezilla -y
     ```

   - Configura DRBL per al seu ús amb:

     ```bash
     sudo /opt/drbl/sbin/drblsrv -i
     ```

   - Segueix les indicacions per configurar el servidor, assignant-li una IP fixa com **192.168.1.1** i configurant la xarxa en mode **DHCP** per als clients.

4. **Configuració de la Xarxa del Servidor DRBL**:
   - Durant la configuració de DRBL, selecciona l'opció per treballar en mode multicast.
   - Verifica que el servidor DRBL estigui preparat per arrencar com a servidor de xarxa PXE, permetent que els clients puguin arrencar i connectar-se al servidor DRBL automàticament.

#### 1.2 Configuració dels Clients

1. **Creació de les Màquines Virtuals Clients**:
   - Crea dues màquines virtuals noves per a ús com a clients, amb els noms **Client1** i **Client2**.
   - **Recursos**: Assigna 2 GB de RAM, 1 CPU i un disc dur de 15 GB a cadascun.
   - **Connexió de xarxa**: Configura cada màquina perquè es connecti a la mateixa xarxa que el servidor, en mode **Bridge** o xarxa interna, segons el tipus de xarxa del servidor.

2. **Configuració de la Xarxa dels Clients**:
   - Configura cada client perquè obtingui la seva adreça IP automàticament mitjançant **DHCP**.
   - Això permet que, en arrencar, els clients se connectin directament al servidor DRBL per PXE i rebin la imatge clonada.

### B) Preparació de la Imatge del Sistema Ubuntu

1. **Creació de la Imatge de Clonezilla**:
   - Inicia la màquina virtual d'Ubuntu configurada en la pràctica anterior.
   - Obre el terminal i executa Clonezilla en mode *save disk*:

     ```bash
     sudo clonezilla
     ```

   - Selecciona l’opció de desar la imatge en un disc local o al servidor de xarxa.
   - Completa el procés de creació de la imatge seguint les indicacions de Clonezilla.

2. **Emmagatzematge de la Imatge en el Servidor**:
   - Després de crear la imatge, emmagatzema-la en una carpeta compartida del servidor DRBL o a l’emmagatzematge local del servidor, si és possible.

---

## 2. Configuració del Desplegament Multicast amb DRBL Clonezilla

### A) Configuració del Mode Multicast

1. **Configuració del Mode Multicast a Clonezilla**:
   - Obre el terminal al servidor DRBL i executa el següent per a accedir al menú de Clonezilla:

     ```bash
     sudo /opt/drbl/sbin/dcs
     ```

   - Tria l’opció **Clonezilla multicast** per iniciar el mode de clonació per a múltiples clients.
   - Selecciona la imatge d’Ubuntu que has creat i tria l’opció de copiar-la a tots els clients connectats.

2. **Verificació de la Configuració DHCP**:
   - Assegura’t que el servidor DRBL estigui configurat per proporcionar adreces IP automàtiques (DHCP) a tots els clients.
   - Comprova que els clients puguin detectar el servidor i rebre una IP assignada en el moment de l’arrencada.

### B) Arrencada dels Clients en Mode PXE

1. **Configuració de l’Arrencada PXE**:
   - Configura cada client perquè arrenci des de la xarxa. A **VirtualBox**, accedeix a **Configuració → Sistema → Ordre d’arrencada** i selecciona la xarxa (PXE).
   - Reinicia cada client per arrencar-lo des de la xarxa i connectar-se al servidor.

2. **Procés de Clonació Multicast**:
   - Un cop els clients es connectin al servidor, la clonació s'iniciarà automàticament.
   - Clonezilla enviarà la imatge d’Ubuntu de manera simultània a tots els clients, assegurant que tots rebin exactament la mateixa configuració.

---

## 3. Validació del Desplegament

### A) Comprovació del Sistema i Aplicacions

1. **Inicia els Clients i Verifica el Sistema**:
   - Un cop completada la clonació, inicia cada client i comprova que Ubuntu s'ha instal·lat correctament.
   - Assegura't que el sistema es comporta com esperat i que no hi ha errors en iniciar les aplicacions.

2. **Prova de Funcionalitat de les Aplicacions**:
   - Verifica que **GIMP** i **Guake** estan instal·lats i funcionen correctament.
   - Obre **Guake** i comprova que es llança correctament des de la part superior de la pantalla.
   - Inicia **GIMP** per assegurar-te que es carrega sense errors i que es pot utilitzar per editar imatges.

### B) Verificació de la Configuració del Sistema

1. **Comprovació del Fons de Pantalla i Nom del Host**:
   - Assegura’t que cada client mostra el fons de pantalla personalitzat amb el teu nom i cognoms.
   - Revisa que el nom del host per a cada màquina sigui correcte, per exemple: `wildpenguin[COGNOM1]1` i `wildpenguin[COGNOM1]2`.

2. **Prova de Connexió a la Xarxa**:
   - Comprova que cada client pot connectar-se a Internet i altres dispositius de la xarxa.
   - Fes un test de ping per assegurar que la configuració de xarxa funciona correctament:

     ```bash
     ping google.com
     ```

---

## 4. Creació del Manual d’Instal·lació

1. **Documentació del Procés**:
   - Crea un document que detalli cada pas seguit durant la instal·lació, incloent-hi les captures de pantalla de cada etapa.
   - Inclou captures de pantalla de les configuracions del servidor, el procés de clonació i la verificació de la configuració final.

2. **Incloure Captures de Pantalla Completes**:
   - Per a cada captura, assegura’t que el nom del host o el fons de pantalla personalitzat siguin visibles.
   - La documentació ha de ser clara i fàcil de seguir, amb explicacions sobre cada pas per a que qualsevol altra persona pugui repetir el procés amb facilitat.
