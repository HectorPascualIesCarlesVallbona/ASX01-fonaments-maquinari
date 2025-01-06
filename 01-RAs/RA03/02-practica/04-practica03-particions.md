## Pràctica: **Gestió de Particions i Creació d’Imatges de Disc amb Clonezilla i dd**

### **Objectius**
En aquesta pràctica, aprendràs a:
1. Crear particions en un disc dur.
2. Gestionar sistemes de fitxers a les particions.
3. Crear imatges de seguretat del disc amb Clonezilla i `dd`.
4. Restaurar imatges per recuperar sistemes en cas de fallida.

## **Materials Necessaris**
- **Ordinador amb VirtualBox** instal·lat.
- **ISO de Clonezilla Live** (descarregable a [clonezilla.org](https://clonezilla.org/)).
- **Sistema Operatiu Ubuntu 22.04** (com a màquina virtual).

## **Fases de la Pràctica**

### **1. Creació i Gestió de Particions**
1. **Inicialitza un disc virtual nou**:
   - Crea un disc nou de **25 GB** en VirtualBox (nom: `disc-secundari.vdi`).
   - Afegeix-lo a una màquina virtual Ubuntu.

2. **Gestiona les particions**:
   - Arrenca la màquina virtual i accedeix al terminal.
   - Executa `fdisk` per gestionar les particions del nou disc:
     ```bash
     sudo fdisk /dev/sdb
     ```
   - Crea:
     - 1 **partició primària** de 5 GB.
     - 1 **partició lògica** de la resta de l'espai dins d'una partició estesa.
   - Verifica amb:
     ```bash
     sudo lsblk
     ```

3. **Dóna format a les particions**:
   - Formata la partició primària en **ext4**:
     ```bash
     sudo mkfs.ext4 /dev/sdb1
     ```
   - Formata la partició lògica en **NTFS**:
     ```bash
     sudo mkfs.ntfs /dev/sdb5
     ```

### **2. Creació d’Imatges de Disc**

1. **Creació d'una imatge amb `dd`**:
   - Crea una imatge bit a bit de la partició `/dev/sdb1`:
     ```bash
     sudo dd if=/dev/sdb1 of=~/imatges/particio1_backup.img bs=4M
     ```
   - Observa el temps i l’espai ocupat.

2. **Verifica la integritat de la imatge**:
   - Utilitza la comanda `md5sum` per generar el hash:
     ```bash
     md5sum ~/imatges/particio1_backup.img
     ```

3. **Creació d'una imatge amb Clonezilla**:
   - Arrenca la màquina virtual des de l'ISO de Clonezilla.
   - Selecciona **"device-image"** > **"Beginner mode"**.
   - Desa una imatge de tot el disc `/dev/sdb` a la carpeta `/home/particions/clonezilla/`.

### **3. Restauració d’Imatges**

1. **Restauració amb `dd`**:
   - Elimina la partició original amb `fdisk`.
   - Restaura la partició des de la imatge creada:
     ```bash
     sudo dd if=~/imatges/particio1_backup.img of=/dev/sdb1 bs=4M
     ```

2. **Restauració amb Clonezilla**:
   - Arrenca amb Clonezilla Live.
   - Selecciona **"device-image"** > **"Beginner mode"** > **"Restore"**.
   - Restaura el disc complet des de la imatge prèviament creada.

## **Entrega**
- Documenta tot el procés amb **captures de pantalla de cada pas i cada punt** demanat a la pràctica junt amb text
- Adjunta els següents fitxers:
  - Hash de la imatge creada amb `dd`.
  - Captura del resultat de `lsblk` després de la restauració.

## **Criteris d'Avaluació**
1. Creació correcta de particions amb `fdisk` i formatació.
2. Generació d'imatges amb `dd` i Clonezilla.
3. Restauració efectiva de les imatges creades.
4. Documentació clara i detallada amb captures de pantalla.
  - portada: nom, cognom, data, mòdul
  - index
  - introducció
  - desenvolupament
  - conclusions

## **Recursos Addicionals**
- [Guia d’ús de `dd` a Linux](https://www.geeksforgeeks.org/dd-command-in-linux-with-examples/)
- [Clonezilla - Documentació oficial](https://clonezilla.org/clonezilla-live-doc.php)