# Creació d’Imatges de Programari. Suport del Programari Bàsic d’un Sistema

## Índex

- [Creació d’Imatges de Programari. Suport del Programari Bàsic d’un Sistema](#creació-dimatges-de-programari-suport-del-programari-bàsic-dun-sistema)
  - [Índex](#índex)
  - [Introducció](#introducció)
    - [Recursos per ampliar](#recursos-per-ampliar)
  - [1.1 Partició de Disc](#11-partició-de-disc)
      - [Definició i Importància](#definició-i-importància)
    - [Tipus de Particions](#tipus-de-particions)
      - [Sistemes de Fitxers](#sistemes-de-fitxers)
    - [Comandes d'Ús](#comandes-dús)
  - [1.2 Imatges de Suport](#12-imatges-de-suport)
      - [Què són les Imatges de Suport?](#què-són-les-imatges-de-suport)
    - [Tipus d’Imatges](#tipus-dimatges)
      - [Eines per Crear Imatges](#eines-per-crear-imatges)
  - [1.3 Opcions d’Arrencada d’un Sistema](#13-opcions-darrencada-dun-sistema)
      - [Funció de les Opcions d’Arrencada](#funció-de-les-opcions-darrencada)
    - [Gestors d’Arrencada](#gestors-darrencada)
      - [Configuració Avançada](#configuració-avançada)
  - [1.4 Creació d’Imatges](#14-creació-dimatges)
      - [Processos de Creació](#processos-de-creació)
    - [Eines Recomanades](#eines-recomanades)
      - [Exemple de Configuració](#exemple-de-configuració)
  - [1.5 Recuperació d’Imatges](#15-recuperació-dimatges)
      - [Procés de Recuperació](#procés-de-recuperació)
    - [Eines per a la Restauració](#eines-per-a-la-restauració)
  - [1.6 Videos tutorials](#16-videos-tutorials)

---

## Introducció

La creació d’imatges de programari és fonamental per a la gestió, clonació, i restauració d’entorns informàtics. Aquest procés permet replicar una còpia exacta d’un sistema operatiu, conjunt de programari i configuracions d'un ordinador o servidor. La capacitat de restaurar i desplegar imatges de programari és especialment útil en entorns empresarials i laboratoris d’informàtica, on es requereix mantenir múltiples sistemes amb la mateixa configuració. Aquesta secció inclou els conceptes bàsics de la partició de discs, tipus d’imatges, gestors d’arrencada, així com els passos per crear i restaurar aquestes imatges.

![Diagrama de clonació de disc](https://www.backupassist.com/_assets/img/articles/what-is-an-image-backup.jpg)

### Recursos per ampliar

- [Què és la clonació de discos?](https://www.acronis.com/en-us/articles/disk-cloning/) (Acronis)
- [Clonezilla, una eina de codi obert per a la clonació d'imatges](https://clonezilla.org/) (Clonezilla Official)
- [Conceptes bàsics d'imatges de disc](https://www.techtarget.com/searchdatabackup/definition/disk-image) (TechTarget)

---

## 1.1 Partició de Disc

#### Definició i Importància

La partició de disc és el procés de dividir un disc dur o SSD en parts separades, cadascuna amb el seu sistema de fitxers. Les particions permeten dividir físicament i lògicament els espais d’emmagatzematge, fent que cada partició sigui independent de les altres. Això és útil per allotjar diferents sistemes operatius, emmagatzemar dades o organitzar espais dedicats per a determinades aplicacions.

![Esquema de particions de disc](https://upload.wikimedia.org/wikipedia/commons/thumb/2/28/Partitions_of_a_Hard_Disk_2009.jpg/800px-Partitions_of_a_Hard_Disk_2009.jpg)

### Tipus de Particions

1. **Particions Primàries**: Aquestes particions són les més bàsiques i ocupen directament un lloc en la taula de particions del disc. Es poden definir fins a quatre particions primàries per disc. Normalment, una d'aquestes es marca com a "activa", la qual cosa significa que és la partició d’arrencada.
   - Exemple de configuració: Windows en una partició primària per defecte.
   - [Més sobre particions primàries](https://www.pcmag.com/encyclopedia/term/primary-partition) (PCMag)

   ![Partició Primària a Disk Management](https://www.easeus.com/resource/images/en-us/partition/partition-primary.png)

2. **Particions Esteses**: Una partició estesa permet que el disc contingui més de quatre particions. A diferència de les primàries, una partició estesa serveix de contenidor per a altres particions, anomenades particions lògiques.
   - Exemple de configuració: Allotjar múltiples sistemes operatius.
   - [Què és una partició estesa?](https://www.computerhope.com/jargon/e/extendepartition.htm) (Computer Hope)

   ![Exemple de partició estesa](https://www.diskpart.com/screenshot/extended-partition.gif)

3. **Particions Lògiques**: Aquestes particions es creen dins d’una partició estesa. No es poden utilitzar per a l’arrencada d’un sistema operatiu, però són útils per emmagatzemar dades.
   - Exemple de configuració: Una partició lògica per a emmagatzemar dades.
   - [Detalls sobre particions lògiques](https://www.easeus.com/partition-manager-software/logical-partition.html) (EaseUS)

   ![Diagrama de partició lògica](https://i.postimg.cc/6psfMvWP/extended-logical-partitions.png)

#### Sistemes de Fitxers

Els sistemes de fitxers organitzen i gestionen les dades en una partició. Aquests són alguns dels més utilitzats:

- **FAT32**: Compatible amb la majoria de sistemes operatius, però limitat a fitxers de màxim 4 GB.
- **NTFS**: Útil en entorns Windows, admet fitxers grans i permisos de seguretat.
- **ext4**: Sistema nadiu de Linux, dissenyat per grans volums de dades.

![Diagrama de sistemes de fitxers](https://www.tecmint.com/wp-content/uploads/2016/04/Linux-Filesystem.png)

### Comandes d'Ús

- **Linux - fdisk**:

  ```bash
  sudo fdisk /dev/sda
  ```

  - [Guia completa per a fdisk](https://www.geeksforgeeks.org/fdisk-command-in-linux-with-examples/) (Geeks for Geeks)
  
- **Windows - Disk Management**: Interfície gràfica per a la gestió de particions.
  - [Guia de Disk Management en Windows](https://www.howtogeek.com/101862/how-to-manage-disks-and-partitions-in-windows/) (How-To Geek)

- **Linux - parted**:

  ```bash
  sudo parted /dev/sda
  ```

  - [Documentació de parted](https://www.gnu.org/software/parted/manual/parted.html) (GNU)

---

## 1.2 Imatges de Suport

#### Què són les Imatges de Suport?

Les imatges de suport són còpies exactes d’una partició o d'un disc complet, permetent replicar el contingut per a restauració o clonació en altres màquines. Això és essencial en administració de sistemes, on una recuperació ràpida d’un sistema pot ser crítica.

![Exemple d'imatge de disc](https://www.acronis.com/en-us/articles/disk-cloning/Disk_cloning_02.png)

### Tipus d’Imatges

1. **Imatges Completes**: Copien la totalitat de la informació d’un disc o d’una partició. Són les més exhaustives, i també les que ocupen més espai.
   - Exemple: Còpia completa d'un servidor abans d'una actualització.
   - [Més informació sobre imatges completes](https://www.backblaze.com/blog/full-image-backup/) (Backblaze)

   ![Diagrama d'una imatge completa](https://www.backupassist.com/_assets/img/articles/what-is-an-image-backup.jpg)

2. **Imatges Incrementals**: Copien només els canvis realitzats des de la darrera còpia completa o incremental. Aquestes imatges redueixen espai, però requereixen la darrera còpia completa i totes les incrementals per ser restaurades.
   - Exemple: Copia incremental diària en un entorn de desenvolupament.
   - [Detalls sobre imatges incrementals](https://blog.macrium.com/incremental-vs-differential-backups-6e84e08a4469) (Macrium)

   ![Diagrama d'una imatge incremental](https://www.cloudwards.net/wp-content/uploads/2018/10/Types-of-Backups-720x720.png)

3. **Imatges Diferencials**: Còpia dels canvis des de la darrera imatge completa. Permet restaurar el sistema amb només la còpia completa i l’última còpia diferencial.

- Exemple: Còpies diferencials setmanals en una empresa.
- [Què són les imatges diferencials?](https://www.nakivo.com/blog/backup-types-full-incremental-differential-backup/) (Nakivo)

   ![Diagrama d'una imatge diferencial](https://4sysops.com/wp-content/uploads/2021/05/Explanation-of-full-incremental-and-differential-backups.jpg)

#### Eines per Crear Imatges

- **Clonezilla**: Eina de codi obert per crear imatges completes, diferencials o incrementals.
  - [Guia de Clonezilla](https://clonezilla.org/clonezilla-live-doc.php)
  
- **Acronis True Image**: Eina comercial per a còpies de seguretat completes i restauracions.
  - [Acronis True Image Overview](https://www.acronis.com/en-us/personal/computer-backup/)

---

## 1.3 Opcions d’Arrencada d’un Sistema

#### Funció de les Opcions d’Arrencada

Les opcions d’arrencada defineixen el sistema operatiu que es carregarà en engegar l'ordinador. Els gestors d’arrencada són essencials en entorns amb més d’un sistema operatiu i ofereixen opcions per restaurar i personalitzar l'arrencada.

![Exemple de menú d'arrencada amb GRUB](https://upload.wikimedia.org/wikipedia/commons/thumb/2/22/Grub_menu.png/800px-Grub_menu.png)

### Gestors d’Arrencada

1. **GRUB**: Gestor d’arrencada de Linux, altament configurable. Permet opcions com arrencades segures i recuperacions.
   - [Instal·lació i configuració de GRUB](https://www.dionysopoulos.me/grub2-configuration.html)
  
2. **BOOTMGR (Windows Boot Manager)**: Gestiona l’arrencada en sistemes Windows per llançar sistemes basats en Windows.
   - [Detalls sobre Windows Boot Manager](https://docs.microsoft.com/en-us/windows-hardware/drivers/devtest/windows-boot-manager)

   ![Exemple de menú d'arrencada amb BOOTMGR](https://thegeekpage.com/wp-content/uploads/2020/07/boot.png)

3. **EFI/UEFI**: Permet l'arrencada més ràpida i segura amb opcions de configuració avançada com Secure Boot.
   - [Què és EFI i UEFI?](https://www.pcgamer.com/what-is-uefi-and-how-does-it-differ-from-bios/)

   ![Exemple de configuració EFI/UEFI](https://support.lenovo.com/medias/Port-Settings.png?context=bWFzdGVyfHJvb3R8MTgyMzMyfGltYWdlL3BuZ3xoYTQvaGY4LzEwNDY2NjMxNzA1NTUwLnBuZ3w2NmE2ZDliMzdkOWJjYjYwYzU4MzJiYTA1Yjk1MDA4MTNlYTI0OWY3YWMwY2JkODhiYzAxZjgzMWI1ODAzOWJl)

#### Configuració Avançada

- **Arrencada PXE**: Inicia el sistema operatiu des d’un servidor a través de la xarxa. Útil en entorns amb múltiples màquines en xarxa.
  - [Guia per configurar PXE](https://wiki.ubuntu.com/UEFI/PXE-netboot-install)

  ![Diagrama de funcionament PXE](https://wiki.ubuntu.com/UEFI/PXE-netboot-install?action=AttachFile&do=get&target=pxe_diagram.png)

---

## 1.4 Creació d’Imatges

#### Processos de Creació

La creació d’imatges implica fer una còpia de les dades bit a bit d’un disc o partició. Aquest procés és important per desplegar sistemes o restaurar en cas de fallades. Es recomana utilitzar imatges completes per a sistemes crítics i incrementals o diferencials per al manteniment diari.

![Diagrama del procés de clonació](https://www.backupassist.com/_assets/img/articles/what-is-an-image-backup.jpg)

### Eines Recomanades

1. **dd** (Linux): Comanda de baix nivell per crear imatges bit a bit. Ideal per professionals que volen un control precís.
   - [dd Command Examples](https://www.geeksforgeeks.org/dd-command-in-linux-with-examples/)

   ```bash
   sudo dd if=/dev/sda of=/mnt/backup.img bs=4M
   ```

2. **Clonezilla**: Permet crear imatges i configurar el procés de clonació per a múltiples màquines simultàniament.
   - [Clonezilla Documentation](https://clonezilla.org/clonezilla-live-doc.php)

#### Exemple de Configuració

Crear una imatge de suport de Linux amb dd:

```bash
sudo dd if=/dev/sda of=/mnt/backup.img bs=4M
```

---

## 1.5 Recuperació d’Imatges

#### Procés de Recuperació

La restauració d’imatges és crucial per a la recuperació de desastres. Aquest procés utilitza una còpia d'un sistema per retornar-lo a un estat funcional. En un entorn empresarial, les còpies de suport regulars són fonamentals per a garantir el mínim temps d'inactivitat.

![Diagrama de recuperació d'imatges](https://support.apple.com/library/APPLE/APPLECARE_ALLGEOS/SPOTLIGHT/imageofdiskhero.png)

### Eines per a la Restauració

1. **Acronis True Image**: Ideal per recuperar fitxers individuals o fer una restauració completa.
   - [Restauració amb Acronis True Image](https://www.acronis.com/en-us/support/documentation/ATI2018/12299.html)

2. **Clonezilla**: Pot restaurar imatges de manera ràpida i efectiva en múltiples màquines.
   - [Clonezilla Restore](https://www.clonezilla.org/clonezilla-live-doc.php)
  
![Diagrama de restauració amb Clonezilla](https://www.backup-utility.com/screenshot/cloning-clonezilla.jpg)

## 1.6 Videos tutorials

Aquí teniu 2 vídeos que proporcionen guies pràctiques per gestionar particions, crear imatges de discs i restaurar sistemes en Linux.

 1. **How to Partition and Format a Disk in Linux**  
    Aquest vídeo t’ofereix un tutorial detallat sobre com particionar i formatar discos a Linux, mostrant com afegir nous discos i gestionar les particions. És ideal per als usuaris de Linux que volen aprendre a configurar discos des de zero.  
    [Veure el vídeo aquí](https://www.youtube.com/watch?v=JCFlsslBvX8)【123†source】.

 2. **Disk Partitioning in Linux: Adding Disks, Partitions & File Systems (RHEL7/CentOS7)**  
    Aquest tutorial t’ensenya a afegir discos nous, crear particions i gestionar sistemes de fitxers en entorns RHEL7 i CentOS7. Proporciona una guia visual sobre com gestionar eficientment els discos en un sistema Linux.  
    [Veure el vídeo aquí](https://www.youtube.com/watch?v=cP1TqdOJNj8)【124†source】.
