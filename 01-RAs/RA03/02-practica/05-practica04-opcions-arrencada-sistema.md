### **Pràctica: Opcions d'Arrencada d'un Sistema**

#### **Objectiu**
L'objectiu d'aquesta pràctica és aprendre a configurar i entendre les opcions d'arrencada d'un sistema operatiu amb GRUB (GRand Unified Bootloader). També veurem com modificar aquestes opcions per adaptar-les a situacions diferents.

---

### **Desenvolupament de la pràctica**

#### **1. Configuració inicial**
1. Crea una màquina virtual amb un disc de 20 GB i instal·la-hi Ubuntu Server sense interfície gràfica.
2. Comprova que a la configuració de la màquina virtual estigui seleccionada l'opció correcta de BIOS o UEFI, segons el sistema operatiu.

---

#### **2. Exploració del menú de GRUB**
1. Inicia la màquina virtual. Durant l'arrencada, prem **Shift** o **Esc** per accedir al menú de GRUB.
2. Mira les opcions que hi ha al menú i identifica:
   - L'opció d'arrencada predeterminada.
   - Les opcions avançades (si n'hi ha).
   - L'opció per arrencar en mode de recuperació.
3. Anota què has vist, junt a imatges, i explica per a què serveix cadascuna d’aquestes opcions.

---

#### **3. Modificació temporal del GRUB**
1. Al menú de GRUB, selecciona l'opció d'arrencada predeterminada i prem la tecla **e** per editar-la.
2. Canvia la configuració del kernel afegint-hi un d’aquests paràmetres:
   - **single**: Arrenca el sistema en mode d'usuari únic.
   - **quiet splash**: Mostra menys missatges al terminal mentre arrenca.
3. Desa els canvis temporalment i inicia el sistema.
4. Explica les diferències que has notat amb cadascuna de les configuracions, junt a imatges.

---

#### **4. Configuració permanent del GRUB**
1. Obre el fitxer de configuració de GRUB:
   ```bash
   sudo nano /etc/default/grub
   ```
2. Fes els següents canvis:
   - Redueix el temps d’espera del menú d’arrencada a 5 segons.
   - Canvia l’opció predeterminada d’arrencada per una altra (si n’hi ha).
3. Desa els canvis i actualitza GRUB amb aquesta comanda:
   ```bash
   sudo update-grub
   ```
4. Reinicia la màquina virtual per comprovar si els canvis s’han aplicat correctament amb imatges junt amb text explicatiu.

---

#### **5. Recuperació del GRUB**
1. Crea un error intencionat al fitxer de configuració de GRUB (per exemple, modifica `/boot/grub/grub.cfg` esborrant alguna afegint una linea de codi per provocar-lo).
2. Reinicia la màquina i observa què passa.
3. Utilitza un disc de rescat ([Ubuntu Live ISO](https://ubuntu.com/download/desktop)) per accedir al sistema i reparar el GRUB seguint aquests passos:
   - Munta la partició del sistema:
     ```bash
     sudo mount /dev/sdXn /mnt
     ```
   - Reinstal·la el GRUB:
     ```bash
     sudo grub-install --root-directory=/mnt /dev/sdX
     ```
   - Actualitza la configuració:
     ```bash
     sudo chroot /mnt update-grub
     ```
4. Documenta els passos, imatge amb text descriptiu, que has seguit i comprova que el sistema torni a arrencar correctament.

---

#### **6. Opció addicional (voluntària)**
Explora altres eines d’arrencada, com ara **systemd-boot** o el programa **grub-customizer**, i compara-les amb el GRUB. Explica quines diferències i avantatges té cadascuna.

---

### **Entrega**
Has de presentar un document amb aquesta estructura:

1. **Portada**
   - Nom complet, data i títol de la pràctica.
2. **Índex**
   - Inclou totes les seccions del document, numerades i ordenades.
3. **Introducció**
   - Explica breument els objectius i la importància de la pràctica.
4. **Desenvolupament**
   - Detalla cada fase amb explicacions clares, captures de pantalla i el codi utilitzat.
5. **Conclusions**
   - Reflexiona sobre el que has après, els reptes que has trobat i els resultats obtinguts.

El document ha d'incloure:
- **Captures de pantalla** de cada pas important.
- Una explicació clara del que has fet i dels resultats obtinguts.
- Totes les comandes que hagis utilitzat.

---

### **Avaluació**
- Completar les tasques demanades (40%).
- Explicacions clares i ben documentades (30%).
- Resolució correcta d'errors durant l'arrencada (30%).

💡 Si falta **l'índex** o està **mal documentada**, la nota màxima a obtenir passarà de **10** a **5**.

