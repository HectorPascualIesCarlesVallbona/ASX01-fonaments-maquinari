### Pràctica 3: Creació i gestió de particions (amb VirtualBox)

**Objectiu:** Aprendre a crear, modificar i esborrar particions en un disc dur virtual.

1. Crea una nova màquina virtual a VirtualBox amb un sistema operatiu Linux o Windows (segons preferència).
   - **Instruccions:** Assegura’t de crear un disc virtual dinàmic amb espai lliure suficient per practicar.
   - **Pregunta:** Quants GB de disc virtual necessites per fer proves amb particions?

2. Utilitza **fdisk** en Linux o **Disk Management** en Windows dins la màquina virtual per visualitzar les particions del disc virtual.
   - **Pregunta:** Quantes particions té el disc virtual per defecte?

3. Crea una nova partició lògica dins d’una partició estesa en la màquina virtual i assigna-li un sistema de fitxers **ext4** (Linux) o **NTFS** (Windows).
   - **Pregunta:** Quin avantatge té crear una partició lògica en lloc d'una de primària?

4. Redimensiona una partició existent dins de la màquina virtual per augmentar o reduir l'espai lliure disponible.
   - **Eina recomanada:** Usa **GParted** (pots utilitzar un ISO dins de la màquina virtual) o **Disk Management**.
   - **Pregunta:** Què passa si redueixes la partició del sistema operatiu dins la màquina virtual?
