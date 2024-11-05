# PROBLEMES DETECCIÓ USB A LA MV

## 1. Assegura’t que tens el *VirtualBox Extension Pack* instal·lat

1. Descarrega el **VirtualBox Extension Pack** des de la [pàgina oficial de VirtualBox](https://www.virtualbox.org/wiki/Downloads).
2. A VirtualBox, vés a **Preferències > Extensions**.
3. Fes clic a l'icona `+` per instal·lar el paquet d'extensions.

## 2. Activa el suport USB en la configuració de la màquina virtual

1. Amb la màquina virtual aturada, vés a **Configuració > USB**.
2. Activa **USB 2.0 (EHCI) Controller** o **USB 3.0 (xHCI) Controller** en funció del tipus d'USB.
3. Afegeix el dispositiu USB fent clic al signe `+` i seleccionant el teu dispositiu USB de la llista.

## 3. Verifica els permisos USB (si estàs en Linux)

1. Afegeix el teu usuari al grup `vboxusers` per permetre l'accés als dispositius USB:

   ```bash
   sudo usermod -aG vboxusers $USER
   ```

2. Tanca la sessió i torna a iniciar-la perquè els canvis tinguin efecte.

## 4. Si encara res ha funcionat => Executa VirtualBox com a administrador

1. Tanca VirtualBox completament.
2. Obre VirtualBox **com a administrador** (a Windows, clic dret > Executa com a administrador; a Linux, llança `sudo virtualbox` des de la terminal).
3. Torna a intentar connectar el dispositiu USB a la màquina virtual.
