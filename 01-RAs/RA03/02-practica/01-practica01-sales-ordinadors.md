# RA03 - PRACTICA01 - Sales ordinadors

[Sales ordinadors](https://moodle.iescarlesvallbona.cat/pluginfile.php/186525/mod_resource/content/4/Pr%C3%A0ctica%20UF2.pdf)

## Opció Alternativa per a Instal·lació OEM en Ubuntu Desktop 22.04.3 LTS

1. **Utilitza la ISO d'Ubuntu Desktop per a la Instal·lació Normal**

   Descarrega la ISO `d'Ubuntu Desktop 22.04.3 LTS` i inicia la instal·lació.
   https://help.ubuntu.com/community/Ubuntu_OEM_Installer_Overview

2. **Crea un Usuari Temporal durant la Instal·lació**

   Durant la configuració d'Ubuntu, crea un usuari temporal que utilitzaràs per preconfigurar el sistema.

3. **Configura el Sistema i Instal·la el Programari Necessari**

   Després d'haver iniciat sessió amb l'usuari temporal, fes qualsevol configuració que necessitis:
   - Instal·la aplicacions i programari addicional.
   - Configura els ajustaments del sistema.
   - Personalitza el fons de pantalla o altres configuracions visuals.

4. **Preparació d’Imatge de Clonació amb Clonezilla**
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
     - Comença la clonació: Clonezilla crearà la imatge i la guardarà a la destinació seleccionada. Aquest procés pot trigar uns minuts o hores, depenent de la mida del disc.
     - Un cop finalitzat el procés, Clonezilla et donarà l'opció de reiniciar o apagar el sistema.

