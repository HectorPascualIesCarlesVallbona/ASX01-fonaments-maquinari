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

### Còpia de Seguretat Completa

- **Què fa?**: Fa una còpia de tots els fitxers i dades del sistema o d'una ubicació especificada, independentment de si han canviat o no. Cada còpia completa és una còpia independent que conté totes les dades.
- **Avantatges**:
  - **Restauració ràpida i senzilla**: Com que és una còpia completa de totes les dades, per restaurar només necessites aquesta còpia sense dependre d'altres còpies.
  - **Simplicitat**: És el tipus de còpia de seguretat més fàcil de gestionar, ja que no hi ha dependències entre còpies.
- **Desavantatges**:
  - **Espai d'emmagatzematge**: Ocupa molt més espai, ja que es copien tots els fitxers cada vegada, fins i tot aquells que no han canviat.
  - **Temps de còpia**: El procés és més lent perquè copia tots els fitxers cada vegada.

### Còpia de Seguretat Incremental

- **Què fa?**: Fa una còpia només dels fitxers que han canviat o s'han creat des de l'última còpia de seguretat **(incremental o completa)**. Això vol dir que cada còpia només inclou els canvis fets des de l'última còpia, sigui quin sigui el tipus de còpia anterior.
- **Avantatges**:
  - **Estalvi d'espai**: Cada còpia ocupa menys espai, ja que només es copien els fitxers nous o modificats des de l'última còpia.
  - **Estalvi de temps**: És més ràpida que altres tipus de còpia perquè s'executa només sobre els fitxers canviats.
- **Desavantatges**:
  - **Restauració més lenta**: Per restaurar el sistema, necessites la còpia completa original i totes les còpies incrementals fins a l'últim punt de restauració. Això fa que el procés sigui més complex i llarg.
  
### Còpia de Seguretat Diferencial

- **Què fa?**: Fa una còpia dels fitxers que han canviat o s'han creat des de l'última còpia de seguretat **completa**. Cada còpia diferencial inclou tots els fitxers modificats o nous des de la còpia completa més recent.
- **Avantatges**:
  - **Restauració més ràpida**: Per restaurar el sistema, només necessites la còpia completa original i l'última còpia diferencial, fent que el procés sigui més senzill i ràpid que amb les incrementals.
- **Desavantatges**:
  - **Més espai d'emmagatzematge**: A mesura que es fan més còpies diferencials, aquestes creixen perquè acumulen tots els canvis des de l'última còpia completa, ocupant més espai que les còpies incrementals.
  - **Còpia més lenta**: A mesura que passa el temps des de l'última còpia completa, la còpia diferencial es va fent més gran i triga més temps a completar-se.

### Comparació entre Completa, Incremental i Diferencial

| Característica                   | Còpia Completa                      | Còpia Incremental                    | Còpia Diferencial                    |
|-----------------------------------|-------------------------------------|--------------------------------------|--------------------------------------|
| **Què copia?**                    | Tots els fitxers                    | Canvis des de l'última còpia (sigui quina sigui) | Canvis des de l'última còpia completa |
| **Espai ocupat**                  | Molt gran                           | Molt petit                           | Creixent amb el temps                |
| **Temps de còpia**                | Més lent                            | Ràpid                               | Més lent amb el temps                |
| **Restauració**                   | Només necessites una còpia          | Necessites totes les còpies incrementals | Necessites la còpia completa i l'última diferencial |
| **Complexitat de restauració**    | Molt baixa                          | Més alta                            | Moderada                            |

### Diferències Clau

1. **Còpia Completa**: Cada còpia inclou **tots els fitxers**. És senzilla i ràpida de restaurar, però consumeix molt espai i temps en fer-se.

2. **Còpia Incremental**: Cada còpia només inclou els **fitxers nous o modificats** des de l'última còpia, sigui del tipus que sigui. És la més eficient en espai i temps de còpia, però la restauració és més complexa, ja que es necessita la còpia completa original i totes les incrementals.

3. **Còpia Diferencial**: Cada còpia inclou els **fitxers nous o modificats des de l'última còpia completa**. Consumeix més espai que la còpia incremental, però la restauració és més senzilla, ja que només necessites la còpia completa i l'última còpia diferencial.

### Resum

- **Còpia completa**: Ideal si tens molt espai d’emmagatzematge i necessites restaurar ràpidament.
- **Còpia incremental**: Ideal per optimitzar espai i temps de còpia, però requereix una restauració més complexa.
- **Còpia diferencial**: Ofereix un bon equilibri entre espai d’emmagatzematge i facilitat de restauració.

### Dubtes entre diferencial i incremental

1. **Còpia Incremental**:
   - Cada còpia incremental només copia els **canvis des de l'última còpia**, sigui aquesta completa o incremental.
   - Exemple:
     - Fas una còpia completa el **dilluns**.
     - Dimarts, fas una còpia incremental que només inclou els canvis fets entre dilluns i dimarts.
     - Dimecres, fas una còpia incremental que només inclou els canvis fets entre dimarts i dimecres.
     - Dijous, fas una còpia incremental amb els canvis des de dimecres, i així successivament.

   Per restaurar el sistema al dijous, necessitaries:
   - La còpia completa del dilluns.
   - La còpia incremental del dimarts.
   - La còpia incremental del dimecres.
   - La còpia incremental del dijous.

   **No passa a ser diferencial en cap moment**, segueix copiant només els canvis des de l'última còpia incremental o completa.

2. **Còpia Diferencial**:
   - Cada còpia diferencial inclou els **canvis des de l'última còpia completa**.
   - Exemple:
     - Fas una còpia completa el **dilluns**.
     - Dimarts, fas una còpia diferencial que inclou els canvis des de la còpia completa del dilluns.
     - Dimecres, fas una còpia diferencial que inclou **tots els canvis des de dilluns**, no només des de dimarts.
     - Dijous, fas una còpia diferencial amb **tots els canvis des de dilluns**.

   Per restaurar el sistema al dijous, només necessitaries:
   - La còpia completa del dilluns.
   - La còpia diferencial del dijous.

### Diferència clau

- **Incremental**: Cadascuna de les còpies incremental només es basa en l'última còpia (sigui incremental o completa).
- **Diferencial**: Cada còpia diferencial es basa en l'última còpia completa.

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
  