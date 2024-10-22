# 02 - Pràctica 01 - programari

## 1. Diferència entre Antivirus, Firewall i Spyware

### Antivirus

Els **antivirus** són programes dissenyats per detectar, prevenir i eliminar programes maliciosos, com virus, cucs i troians. Aquests programes analitzen arxius i aplicacions per identificar i eliminar codi nociu.  
Exemples d'antivirus comuns **McAfee**, **Norton**, i **Avast**.

### Firewall

Un **firewall** és una barrera de seguretat que controla el trànsit de xarxa entre la teva xarxa local i Internet. El seu objectiu és impedir l'accés no autoritzat, tant a nivell de xarxa com d'aplicacions. Els firewalls poden ser de programari, com el **Firewall de Windows**, o de maquinari, com els que es troben en routers.

### Spyware

El **spyware** és un tipus de programari que s'instal·la a l'ordinador sense permís i recull informació sobre l'usuari, com l'historial de navegació, contrasenyes i dades personals. Aquest programari s'utilitza sovint per fer seguiment de l'activitat de l'usuari i, en alguns casos, per robar informació confidencial.  
Exemples de programes anti-spyware: **Spybot** i **Malwarebytes**.

---

## 2. Importància de les Còpies de Seguretat i Tipus Principals

Les còpies de seguretat són essencials per protegir la informació davant de pèrdues de dades causades per errors de maquinari, atacs informàtics o errors humans. Mantenir còpies de seguretat garanteix la continuïtat de l'activitat, ja que permet recuperar les dades originals en cas de fallada.

### Tipus Principals de Còpies de Seguretat

- **Còpia de Seguretat Completa**: Fa una còpia de tots els fitxers seleccionats. És el procés més lent i ocupa més espai, però facilita la recuperació de dades.
- **Còpia de Seguretat Incremental**: Només copia els fitxers que han canviat des de l'última còpia de seguretat. Redueix el temps i l'espai de còpia, però la recuperació pot ser més lenta.
- **Còpia de Seguretat Diferencial**: Crea una còpia dels fitxers que han canviat des de l'última còpia completa. És més ràpida que una còpia completa però ocupa més espai que la incremental.

Exemples d'eines per fer còpies de seguretat: **Acronis True Image** per a Windows i **Déjà Dup** per a Linux.

---

## 3. Gestió de Discos

### 3.1 Definició de Partició i Tipus de Particions

Una **partició** és una divisió lògica d'un disc dur que permet separar l'espai d'emmagatzematge en seccions independents. Cada partició es pot formatar amb un sistema d'arxius diferent i utilitzar-se per a diferents finalitats.

- **Partició Primària**: És una partició principal del disc. Cada disc pot tenir un màxim de quatre particions primàries, una de les quals es pot marcar com activa per arrencar el sistema operatiu.
- **Partició Lògica**: Part d'una partició estesa, que permet crear més particions en un mateix disc. Les particions lògiques són útils per separar dades i programari del sistema operatiu, però no poden arrencar directament el sistema operatiu.

### 3.2 Principals Sistemes d'Arxius

- **FAT32**: Sistema de fitxers compatible amb gairebé tots els sistemes operatius, però limitat a fitxers de menys de 4GB.
- **NTFS**: Sistema de fitxers per defecte a Windows que suporta fitxers grans i permet la gestió de permisos i compressió de dades.
- **ext4**: Sistema d'arxius comú en distribucions Linux, que ofereix millor gestió de grans quantitats de dades i major velocitat en comparació amb ext3.
- **exFAT**: Compatible amb dispositius de memòria externa, com USBs, permet emmagatzemar fitxers de qualsevol mida i és compatible amb Windows i alguns sistemes Linux.

### 3.3 Eines de Gestió de Discs Durs

#### Per a Windows

- **Disk Management**: Eina integrada en Windows per gestionar particions i formatar discos. Permet crear, eliminar, i reduir particions, així com canviar les lletres d'unitat.
  
  **Exemple**:
  1. Per accedir-hi, fes clic dret sobre "Aquest ordinador" i selecciona "Administrar".
  2. A la finestra que apareix, tria "Gestió de discos".
  3. Aquí, podràs crear una partició nova fent clic dret sobre un espai no assignat i seleccionant "Nou volum simple".
  
#### Per a Linux

- **GParted**: És una eina de gestió de particions molt usada en sistemes Linux, disponible en format live CD/USB. Permet crear, esborrar, moure i redimensionar particions.
  
  **Exemple**:
  1. Obre el terminal i instal·la GParted amb la comanda `sudo apt-get install gparted`.
  2. Inicia l'aplicació amb permisos d'administrador amb `sudo gparted`.
  3. Per crear una nova partició, selecciona l'espai no assignat, fes clic dret i tria "Nou".
  