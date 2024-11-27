# CONCEPTES sobre la pràctica de DRBL

## **1. PXE**
El PXE (Preebot Execution Environment), és un entorn per arrancar i instalar sistemas operatius en xarxa, de manera independent dels dispositius d'emmagatzemage. Utilitza varius protocols: IP, UDP, DHCP i TFTP.

## **2. Multicasting**
El multicasting és una tècnica utilitzada per enviar una còpia d'una imatge de disc a múltiples màquines clients de manera simultània, utilitzant un únic flux de dades per a totes les màquines. Això permet clonar diverses màquines alhora de forma eficient, estalviant temps i ample de banda en comparació amb altres mètodes com l'unicast (un flux per màquina).

## **3. DRBL**
DRBL (Diskless Remote Boot in Linux) és una eina que permet als clients arrencar sistemes operatius i utilitzar serveis sense necessitat d'un disc dur local. En aquesta opció:

Proporciona serveis d’arrencada remota per als clients.
Configura un entorn perquè els clients utilitzin sistemes Linux en mode remot (per exemple, sessions d’escriptori Linux en xarxa).
Què fa quan l’inicialitzes?

Activa el servei DHCP per assignar IPs als clients.
Configura PXE Boot per permetre als clients arrencar sistemes operatius remots des del servidor.
Proporciona un entorn de treball compartit per a múltiples clients en temps real.

Quan utilitzar Start DRBL?
Si necessites habilitar arrencades remotes o un entorn de treball compartit per als clients.
Si vols utilitzar DRBL per a finalitats diferents de la clonació, com ara executar sistemes Linux als clients sense disc.

## **4. Clonezilla Server**
Clonezilla Server és una eina basada en DRBL dissenyada específicament per gestionar la clonació de discos o particions en múltiples màquines de manera simultània (unicast o multicast).

Proporciona una imatge de disc als clients perquè puguin restaurar-la o clonar-la.
Permet clonar diverses màquines alhora amb multicast o gestionar la clonació d'una única màquina amb unicast.
Què fa quan l’inicialitzes?

Activa serveis de xarxa similars a DRBL (DHCP, PXE).
Configura el servidor perquè serveixi imatges de disc mitjançant Clonezilla.
Permet seleccionar imatges existents o crear-ne de noves per restaurar-les en clients.

Quan utilitzar Clonezilla Server?
Si necessites clonar una o diverses màquines en una xarxa.
Si vols utilitzar el mode multicast per distribuir imatges a múltiples clients de manera eficient.

## **5. Com triar entre Start DRBL i Clonezilla Server?**
Start DRBL si:
Vols configurar un entorn de treball remot per als clients.
No necessites clonar discos, sinó simplement arrencar màquines remotes sense disc dur.

Clonezilla Server si:
Necessites clonar discos o particions en diverses màquines alhora.
Vols utilitzar imatges existents per restaurar màquines.