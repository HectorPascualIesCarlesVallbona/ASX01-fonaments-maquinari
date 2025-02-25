# **Examen d'Arrencada del Sistema i Creació d'Imatges de Programari resolt**


**1. Quina és la funció principal del bootloader en el procés d'arrencada?**  
- **Resposta correcta:** b) Carregar el kernel del sistema operatiu a la memòria RAM.  
  - **Explicació:** El bootloader és un component clau en el procés d'arrencada, ja que s'encarrega de carregar el kernel del sistema operatiu a la memòria RAM i cedir-li el control.  
  - **Incorrectes:**  
    - a) Gestionar l'alimentació → Això ho fa la BIOS/UEFI.  
    - c) Configurar els dispositius de xarxa → No és la seva funció principal.  
    - d) Carregar la BIOS/UEFI a la memòria RAM → La BIOS/UEFI s'executa prèviament.  

---

**2. Quin dels següents no és un tipus de partició en sistemes de fitxers?**  
- **Resposta correcta:** d) Fragmentada.  
  - **Explicació:** No existeix el concepte de partició fragmentada en sistemes de fitxers; la fragmentació és un problema que afecta l'organització de dades dins d'una partició.  
  - **Incorrectes:**  
    - a) Primària → Partició principal on es pot arrencar un SO.  
    - b) Estesa → Permet múltiples particions lògiques.  
    - c) Swap → Utilitzada per la memòria virtual en Linux.  

---

**3. Quina és la limitació principal del sistema de particionament MBR?**  
- **Resposta correcta:** b) Només permet 4 particions primàries.  
  - **Explicació:** L'MBR només pot gestionar fins a 4 particions primàries, tot i que es pot utilitzar una partició estesa per superar aquesta limitació.  
  - **Incorrectes:**  
    - a) No suporta sistemes operatius Windows → MBR és compatible amb Windows.  
    - c) No permet arrencada dual → És possible amb múltiples particions.  
    - d) Només funciona amb discs SSD → No té relació amb el tipus de disc.  

---

**4. En quin fitxer es poden afegir entrades personalitzades al GRUB?**  
- **Resposta correcta:** c) `/etc/grub.d/40_custom`.  
  - **Explicació:** Aquest fitxer permet afegir entrades personalitzades al menú d'arrencada de GRUB.  
  - **Incorrectes:**  
    - a) `/boot/grub/grub.cfg` → És generat automàticament.  
    - b) `/etc/default/grub` → Conté configuracions generals, no entrades personalitzades.  
    - d) `/var/log/boot.log` → És un registre, no un fitxer de configuració.  

---

**5. Quina comanda de Linux es pot utilitzar per crear una imatge de disc bit a bit?**  
- **Resposta correcta:** b) `dd`.  
  - **Explicació:** La comanda `dd` permet copiar dades bit a bit d'un dispositiu a un altre.  
  - **Incorrectes:**  
    - a) `rsync` → Còpia de fitxers i directoris, no imatges de disc.  
    - c) `tar` → Comprimeix arxius, no fa còpies bit a bit.  
    - d) `mount` → Serveix per muntar sistemes de fitxers.  

---

**6. Què permet la tecnologia PXE en el procés d'arrencada?**  
- **Resposta correcta:** b) Arrencar un sistema operatiu a través de la xarxa sense disc dur local.  
  - **Explicació:** PXE permet que un equip arrenqui des d'un servidor de xarxa sense necessitat de disc local.  
  - **Incorrectes:**  
    - a) Arrencar des d'USB → No és la seva funció.  
    - c) Restaurar el sistema → No fa còpies de seguretat.  
    - d) Augmentar la velocitat → No afecta el rendiment.  

---

**7. Quin d'aquests protocols s'utilitza en una arrencada PXE?**  
- **Resposta correcta:** b) DHCP.  
  - **Explicació:** DHCP assigna IPs als clients durant l'arrencada PXE.  
  - **Incorrectes:**  
    - a) SSH → No intervé en l'arrencada PXE.  
    - c) FTP → Serveix per a la transferència de fitxers, no per arrencada.  
    - d) SNMP → Monitorització de xarxes, no arrencada.  

---

**8. Quina és la diferència principal entre imatges incrementals i diferencials?**  
- **Resposta correcta:** a) Les incrementals només emmagatzemen canvis des de la darrera còpia completa o incremental.  
  - **Explicació:** Les còpies incrementals depenen de còpies anteriors, mentre que les diferencials només depenen de la còpia completa.  
  - **Incorrectes:**  
    - b) Diferencials no requereixen totes les còpies anteriors.  
    - c) Incrementals ocupen menys espai que les diferencials.  
    - d) Diferencials poden ser més lentes de crear.  

---

**9. Quina eina permet la clonació de múltiples màquines a la vegada utilitzant multicast?**  
- **Resposta correcta:** a) Clonezilla.  
  - **Explicació:** Clonezilla suporta multicast per clonar múltiples equips simultàniament.  
  - **Incorrectes:**  
    - b) GParted → Particionament, no clonació.  
    - c) fsck → Revisa sistemes de fitxers.  
    - d) fdisk → Gestiona particions.  

---

**10. Quina comanda permet verificar si un disc està particionat com GPT o MBR?**  
- **Resposta correcta:** a) `parted /dev/sda print`.  
  - **Explicació:** La comanda `parted` mostra l'estructura de partició del disc.  
  - **Incorrectes:**  
    - b) `lsblk` → Mostra dispositius muntats.  
    - c) `df` → Mostra ús d'espai de disc.  
    - d) `mount` → Muntatge de sistemes de fitxers.

---

### **11. Quina de les següents afirmacions és certa sobre l'ús de UEFI en comparació amb BIOS?**  
- **Resposta correcta:** **b) UEFI té un temps d'arrencada més ràpid que BIOS.**  
  - **Explicació:** UEFI millora l'eficiència de l'arrencada en comparació amb BIOS, permetent un inici més ràpid gràcies a una millor gestió del hardware i suport per a discs grans amb particions GPT.  
  - **Incorrectes:**  
    - **a)** UEFI sí que suporta particions GPT, a diferència de BIOS, que usa MBR.  
    - **c)** UEFI no està limitat a FAT32; pot gestionar altres sistemes de fitxers.  
    - **d)** BIOS és menys flexible en dispositius moderns comparat amb UEFI.  

---

### **12. Quin fitxer de configuració és utilitzat per definir les particions que es munten automàticament en Linux?**  
- **Resposta correcta:** **b) `/etc/fstab`**  
  - **Explicació:** Aquest fitxer defineix quins sistemes de fitxers es munten automàticament en iniciar el sistema, especificant opcions com el punt de muntatge i permisos.  
  - **Incorrectes:**  
    - **a)** `/etc/mtab` → Conté una llista dinàmica dels sistemes de fitxers muntats, però no és de configuració.  
    - **c)** `/boot/grub/grub.cfg` → Configura GRUB, no particions.  
    - **d)** `/etc/default/grub` → Conté opcions generals d'arrencada, però no defineix muntatge de particions.  

---

### **13. Quin tipus d’imatge de disc requereix menys espai de magatzem en general?**  
- **Resposta correcta:** **c) Incremental.**  
  - **Explicació:** Les imatges incrementals només guarden els canvis des de la darrera còpia, per tant, ocupen menys espai que les completes i diferencials.  
  - **Incorrectes:**  
    - **a)** Completa → Guarda tot el sistema cada vegada, ocupant més espai.  
    - **b)** Diferencial → Guarda els canvis des de la darrera còpia completa, ocupant més que una incremental.  
    - **d)** Dinàmica → No és un tipus específic d’imatge de disc.  

---

### **14. Quina de les següents eines és de codi obert per a la creació d'imatges de disc?**  
- **Resposta correcta:** **b) Clonezilla.**  
  - **Explicació:** Clonezilla és una eina de codi obert per a la clonació d'imatges de disc, molt utilitzada en entorns de sistemes.  
  - **Incorrectes:**  
    - **a)** Acronis True Image → Programari comercial.  
    - **c)** Norton Ghost → Programari privat de clonació, discontinuat.  
    - **d)** EaseUS Todo Backup → No és de codi obert.  

---

### **15. Quina comanda permet actualitzar la configuració del GRUB després de fer canvis?**  
- **Resposta correcta:** **b) `update-grub`**  
  - **Explicació:** Aquesta comanda escaneja el sistema i actualitza el fitxer de configuració de GRUB perquè reconegui els canvis.  
  - **Incorrectes:**  
    - **a)** `grub-install` → Serveix per instal·lar GRUB en un dispositiu, no per actualitzar-lo.  
    - **c)** `mkinitcpio` → Genera una nova imatge del ramdisk inicial, però no afecta GRUB.  
    - **d)** `fdisk -l` → Mostra particions del disc, no té relació amb GRUB.  

---

### **16. Quina és la funció del fitxer `initrd` en el procés d'arrencada?**  
- **Resposta correcta:** **b) Contenir mòduls necessaris per muntar el sistema de fitxers arrel.**  
  - **Explicació:** `initrd` (Initial RAM Disk) carrega un sistema de fitxers temporal amb els controladors necessaris perquè el sistema pugui muntar la seva partició arrel.  
  - **Incorrectes:**  
    - **a)** No configura opcions de seguretat, només proporciona els mòduls necessaris.  
    - **c)** No emmagatzema la taula de particions, això ho fa el MBR o GPT.  
    - **d)** No està relacionat amb la connexió de xarxa en arrencades remotes.  

---

### **17. Quin component és responsable de l'assignació d'adreces IP durant una arrencada PXE?**  
- **Resposta correcta:** **c) DHCP.**  
  - **Explicació:** El protocol DHCP assigna adreces IP dinàmiques als clients PXE perquè puguin comunicar-se amb el servidor d’arrencada.  
  - **Incorrectes:**  
    - **a)** TFTP → Serveix per a la transferència d'arxius en PXE, no per assignar IPs.  
    - **b)** DNS → Traducció de noms de domini, no d'IPs en arrencada.  
    - **d)** SSH → Comunicació segura remota, no té relació amb PXE.  

---

### **18. En quin cas s'hauria d'utilitzar Clonezilla Server en lloc de Start DRBL?**  
- **Resposta correcta:** **c) Quan es requereix clonar múltiples màquines alhora.**  
  - **Explicació:** Clonezilla Server permet clonar múltiples màquines amb multicast, mentre que DRBL està més orientat a l'arrencada remota sense disc.  
  - **Incorrectes:**  
    - **a)** DRBL s’utilitza per escriptoris remots, no Clonezilla Server.  
    - **b)** Start DRBL permet arrencades remotes, no Clonezilla Server.  
    - **d)** La gestió d'usuaris en xarxa no és la funció principal de Clonezilla Server.  

---

### **19. Quina de les següents afirmacions és certa sobre els sistemes de fitxers?**  
- **Resposta correcta:** **b) ext4 permet suports més grans que FAT32.**  
  - **Explicació:** ext4 pot gestionar volums més grans i fitxers més grans en comparació amb FAT32, que està limitat a fitxers de 4GB i volums de 2TB.  
  - **Incorrectes:**  
    - **a)** NTFS no és millor per a Linux, ja que ext4 és més eficient.  
    - **c)** FAT32 no suporta fitxers de mida il·limitada, està limitat a 4GB.  
    - **d)** NTFS és compatible amb Linux, però amb algunes limitacions.  

---

### **20. Què permet el mode de recuperació de GRUB?**  
- **Resposta correcta:** **b) Recuperar l'arrencada en cas d'error del sistema.**  
  - **Explicació:** El mode de recuperació de GRUB permet executar ordres per restaurar l’arrencada quan aquesta s’ha corromput.  
  - **Incorrectes:**  
    - **a)** No serveix per iniciar un sistema operatiu alternatiu, només per recuperar GRUB.  
    - **c)** No millora el rendiment, només permet la recuperació.  
    - **d)** No està pensat per desactivar serveis no essencials.  