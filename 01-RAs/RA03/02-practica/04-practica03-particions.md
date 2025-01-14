### Pràctica: **Gestió Avançada de Particions**  

💡 **IMPORTANT:** Tota la pràctica l'has de desenvolupar mitjançant **commmandes a la terminal**. **NO utilitzis aplicacions d'escriptori**

#### **Objectius**
En aquesta pràctica treballaràs amb la gestió de particions en un entorn virtual. Aprendràs a:
- Crear i configurar particions en un disc virtual.
- Aplicar sistemes de fitxers a cada partició.
- Montar i desmuntar particions manualment fent servir codi.
- Configurar l’automuntatge de particions al sistema.
- Comparar el rendiment de diferents sistemes de fitxers.

#### **Què necessitaràs?**
- Una màquina virtual amb **Ubuntu 22.04** configurada.
- Un disc virtual addicional, **disc-secundari.vdi**, creat amb una mida de 10 GB.

---

### **Fases de la Pràctica**

#### **1. Configuració del disc virtual**
1. Crea un disc virtual de **10 GB** anomenat **disc-secundari.vdi** i afegeix-lo com a disc secundari a la màquina virtual.
2. Comprova que el disc és visible dins del sistema Ubuntu.

---

#### **2. Creació de particions**
1. Utilitza les eines del sistema per crear particions al disc secundari seguint aquestes especificacions:
   - **Partició 1**: 4 GB amb sistema de fitxers ext4.
   - **Partició 2**: 4 GB amb sistema de fitxers NTFS.
   - Espai restant: partició de swap.
2. Assegura’t que les particions s’han creat correctament i documenta el procés.

---

#### **3. Preparació i formatació**
1. Dona format a cada partició amb el sistema de fitxers corresponent.
2. Activa l’espai de swap.
3. Verifica que totes les particions estan llestes per al seu ús.

---

#### **4. Muntatge i desmuntatge**
1. Munta cada partició en un punt de muntatge específic.
2. Verifica que les particions estan correctament muntades.
3. Desmunta-les manualment i comprova que s’han desmuntat.

---

#### **5. Automuntatge al sistema**
1. Configura el fitxer de configuració del sistema perquè les particions es muntin automàticament cada vegada que el sistema s’inicia.
2. Comprova que l’automuntatge funciona sense problemes.

---

#### **6. Anàlisi de rendiment**
1. Fes proves de rendiment a cada partició per mesurar la velocitat de lectura i escriptura.
2. Analitza els resultats i compara els rendiments dels diferents sistemes de fitxers.

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

---

### **Criteris d’Avaluació**
1. Les particions compleixen les especificacions donades.
2. Els sistemes de fitxers estan configurats correctament.
3. Es poden muntar i desmuntar les particions utilitzant codi.
4. L’automuntatge funciona correctament.
5. El document entregat és complet, ben estructurat i inclou captures de pantalla i explicacions clares.

---

### **Referències i recursos recomanats**

1. Documentació oficial i recursos generals
- [Documentació de Linux](https://www.kernel.org/doc/html/latest/)
- [Guia de particions amb `fdisk`](https://linux.die.net/man/8/fdisk)
- [Manual del sistema de fitxers ext4](https://ext4.wiki.kernel.org/)

2. Articles i tutorials
- [Creació de particions amb `fdisk` en Linux (TecMint)](https://www.tecmint.com/create-partitions-in-linux/)
- [Guia per formatar particions en Linux (Linuxize)](https://linuxize.com/post/how-to-format-disk-partitions-in-linux/)
- [Configurar swap en Linux (TecMint)](https://www.tecmint.com/create-and-activate-swap-partition-in-linux/)

3. Configuració del fitxer `/etc/fstab`
- [Introducció a `/etc/fstab` (Linux Handbook)](https://linuxhandbook.com/fstab/)
- [Muntar particions automàticament amb `/etc/fstab` (Cyberciti)](https://www.cyberciti.biz/faq/linux-fstab-example/)

4. Anàlisi de rendiment amb `dd`
- [Com fer proves de rendiment amb `dd` (TecMint)](https://www.tecmint.com/test-hard-disk-performance-in-linux/)

5. Altres recursos útils
- [Sistema de fitxers NTFS a Linux (ntfs-3g)](https://wiki.archlinux.org/title/NTFS-3G)
- [Eines addicionals per gestionar particions (`parted`)](https://www.gnu.org/software/parted/manual/)
