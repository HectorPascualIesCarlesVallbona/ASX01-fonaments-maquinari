## Pràctica: **Gestió Avançada de Particions**

### **Objectius**
Aquesta pràctica té com a objectiu que aprenguis a:
1. Crear i gestionar particions en un disc dur virtual.
2. Donar format i configurar sistemes de fitxers a les particions.
3. Montar i desmuntar particions utilitzant exclusivament codi.
4. Configurar particions perquè es muntin automàticament al sistema mitjançant fitxers de configuració.
5. Analitzar el rendiment de diferents sistemes de fitxers.

### **Materials Necessaris**
- **Ordinador amb VirtualBox** instal·lat.
- **Sistema Operatiu Ubuntu 22.04** configurat en una màquina virtual.
- Disc secundari anomenat **disc-secundari.vdi** creat dins de VirtualBox.

---

### **Fases de la Pràctica**

#### **1. Creació i Configuració Inicial del Disc**
1. Crea un disc virtual nou de **10 GB** dins de VirtualBox amb el nom **disc-secundari.vdi** i afegeix-lo com a disc secundari a la màquina virtual Ubuntu.
2. Verifica que el disc està disponible al sistema.

---

#### **2. Creació de Particions**
1. Utilitza eines per gestionar les particions del disc secundari.
2. Segueix aquestes especificacions per al disseny de particions:
   - **Partició 1**: 4 GB, format ext4.
   - **Partició 2**: 4 GB, format NTFS.
   - Espai restant: partició de swap.

3. Documenta els passos per verificar que les particions han estat creades correctament.

---

#### **3. Formatació i Preparació de les Particions**
1. Aplica el sistema de fitxers adequat a cada partició:
   - ext4 a la primera partició.
   - NTFS a la segona partició.
   - Activa l’espai de swap a l'última partició.
2. Comprova que cada partició està preparada per ser utilitzada.

---

#### **4. Muntatge i Desmuntatge de Particions**
1. Munta les particions de manera manual a punts de muntatge especificats.
2. Documenta com verificar que les particions estan correctament muntades.
3. Desmunta totes les particions de manera manual.

---

#### **5. Configuració Automàtica del Muntatge**
1. Configura el fitxer de configuració del sistema per tal que les particions es muntin automàticament a l'inici del sistema.
2. Assegura't que les particions es munten de manera automàtica i estable.

---

#### **6. Anàlisi de Rendiment**
1. Realitza proves de rendiment per comparar els diferents sistemes de fitxers implementats:
   - Velocitat d’escriptura.
   - Velocitat de lectura.
2. Analitza els resultats obtinguts i compara el rendiment de cada partició.

---

Aquí tens l'apartat d'entrega revisat amb els requeriments de disseny del document:

---

### **Entrega**
El document final que has d'entregar ha de seguir aquesta estructura:

1. **Portada**:  
   - Nom i cognoms.  
   - Data.  
   - Títol de la pràctica: *Gestió Avançada de Particions*.  
   - Mòdul o assignatura.

2. **Índex**:  
   - Llista ordenada i clicable (si es fa en format electrònic) de les seccions del document.

3. **Introducció**:  
   - Breu explicació dels objectius i la importància de la pràctica.

4. **Desenvolupament**:  
   - Descripció detallada de cada fase, pas a pas, amb el codi utilitzat i explicacions corresponents.  
   - **Captures de pantalla** que validin cada pas realitzat.

5. **Conclusions**:  
   - Reflexió sobre el procés d'aprenentatge, possibles dificultats trobades i com s'han resolt.  
   - Observacions sobre els resultats obtinguts.
  
---

### **Criteris d'Avaluació**
1. Creació correcta de particions segons les especificacions.
2. Formatació i preparació de les particions.
3. Muntatge i desmuntatge utilitzant exclusivament codi.
4. Configuració d’automuntatge correcta i funcional.
5. Documentació clara, completa i estructurada amb captures de pantalla.
