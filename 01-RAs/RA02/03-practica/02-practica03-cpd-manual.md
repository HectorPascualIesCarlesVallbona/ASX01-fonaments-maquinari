# Manual per restaurar una imatge a dues màquines amb DRBL

## Índex
1. [Configuració de la xarxa](#0-configuració-de-la-xarxa)
2. [Preparar el servidor DRBL](#1-preparar-el-servidor-drbl)
3. [Seleccionar la imatge a restaurar](#2-seleccionar-la-imatge-a-restaurar)
4. [Preparar les màquines client](#3-preparar-les-màquines-client)
5. [Iniciar la restauració](#4-iniciar-la-restauració)
6. [Finalitzar el procés](#5-finalitzar-el-procés)

---

## 0. Configuració de la xarxa
- Configura la xarxa com a **Xarxa interna** per garantir que el servidor i els clients es puguin comunicar.  
  - A **VirtualBox**, accedeix als paràmetres de la màquina i assegura't que la configuració de xarxa és correcta.

---

## 1. Preparar el servidor DRBL
1. Inicia el **DRBL Live** a la màquina servidor (màquina amfitriona).
2. Al desktop del servidor, selecciona l'opció **"Clonezilla Server"**.  
   Aquesta eina permet configurar el servidor per distribuir la imatge a través de la xarxa.
3. Durant la configuració guiada:
   - **Configuració de xarxa**:  
     - Selecciona **IP estàtica**.
     - Assigna aquests valors:
       - **IP de `eth0`**: `192.168.1.20`
       - **Màscara de xarxa**: `255.255.255.0`
       - **Gateway**: Deixa el valor predeterminat `172.16.100.254`
       - **Servidor DNS**: Deixa el valor predeterminat `8.8.8.8`
   - El servidor detectarà si hi ha algun servidor DHCP a la xarxa:
     - Si no es troba cap servidor actiu, respon amb **"n"** per continuar.
     - Si apareix un missatge com **"¡ESTO ES MUY MOLESTO!"**, selecciona també **"n"** per avançar.

---

## 2. Seleccionar la imatge a restaurar
1. Escull l'opció **local_dev** per accedir al disc on es troba la imatge.
2. Confirma el disc que conté la imatge prèviament clonada.
3. Selecciona la imatge específica que es restaurarà als clients.
4. Escull **"All Elegir todos los clientes"** per desplegar la imatge a tots els equips.
5. Configura el mode d'execució:
   - **Mode**: Beginner.
   - **Opció**: `restore disk - Restaurar imagen a disco cliente`.
6. Indica si vols verificar la integritat de la imatge:
   - Respon **"Sí, ..."** si vols comprovar si està corrupta.
7. Configura el mode de restauració:
   - Selecciona **multicast**.
   - Tria **clients+time-to-wait** com a mètode.
   - Especifica el nombre de clients: **2**.
   - Defineix el temps màxim d'espera: **300 segons**.
8. Quan acabis, no tanquis la finestra. El servidor DRBL quedarà en espera fins que detecti les màquines client connectades.

---

## 3. Preparar les màquines client
1. Configura les màquines client perquè arrencin des de xarxa (**PXE Boot**):
   - Accedeix a la BIOS/UEFI de les màquines i activa **Network Boot (PXE)**.
2. Assegura't que les màquines client estan connectades a la mateixa xarxa interna que el servidor.

---

## 4. Iniciar la restauració
1. A les màquines client:
   - Quan arrenquin per PXE, es connectaran automàticament al servidor DRBL.
   - El servidor enviarà la imatge i començarà el procés de restauració.

---

## 5. Finalitzar el procés
- Quan la restauració hagi acabat, comprova que les màquines restaurades poden arrencar correctament.
- Si detectes algun problema, revisa les configuracions de xarxa i el procés de restauració.

---
