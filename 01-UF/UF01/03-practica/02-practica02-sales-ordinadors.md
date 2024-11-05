# PRACTICA02 - Sales ordinadors

[Sales ordinadors](https://moodle.iescarlesvallbona.cat/pluginfile.php/186525/mod_resource/content/4/Pr%C3%A0ctica%20UF2.pdf)

## Personalitza per a OEM

### Passos per Configurar un Nom de Host Dinàmic amb un Servei de systemd

1. **Crea un Script de Configuració del Nom de Host**

   Crea un fitxer d’script per configurar el nom de host i desa’l a `/usr/local/bin/set_hostname.sh`:

   ```bash
    sudo nano /usr/local/bin/set_hostname.sh
   ```

   ```bash
   #!/bin/bash
   echo "Introdueix el cognom per configurar el nom de host (wildpenguin[Cognom1]):"
   read COGNOM
   HOSTNAME="wildpenguin${COGNOM}"

   # Estableix el nom de host
   hostnamectl set-hostname "$HOSTNAME"
   echo "$HOSTNAME" > /etc/hostname

   # Actualitza el fitxer /etc/hosts
   sed -i "s/127.0.1.1.*/127.0.1.1 $HOSTNAME/" /etc/hosts

   echo "Nom de host configurat com a $HOSTNAME"
   ```

   Assegura’t que l’script tingui permisos d'execució:

   ```bash
   sudo chmod +x /usr/local/bin/set_hostname.sh
   ```

2. **Crea un Servei systemd per Executar l’Script una vegada**

   Ara, crea un fitxer de servei de `systemd` per executar aquest script en iniciar el sistema.

   Crea el fitxer del servei a `/etc/systemd/system/set-hostname.service` amb el següent contingut:

   ```bash
   sudo nano /etc/systemd/system/set-hostname.service
   ```

   ```ini
   [Unit]
   Description=Configura el nom de host la primera vegada
   After=network.target

   [Service]
   Type=oneshot
   ExecStart=/usr/local/bin/set_hostname.sh
   RemainAfterExit=true

   [Install]
   WantedBy=multi-user.target
   ```

   Aquest servei executarà l’script una sola vegada i després es desactivarà.

3. **Activa el Servei per al Primer Inici**

   Activa el servei perquè s'executi quan el sistema arrenqui:

   ```bash
   sudo systemctl enable set-hostname.service
   ```

4. **Reinicia i Configura el Nom de Host**

   Quan el sistema arrenqui, el servei demanarà el cognom i configurarà el nom de host amb el format `wildpenguin[Cognom1]`. Un cop configurat, el servei es desactivarà automàticament i ja no tornarà a executar-se en futurs inicis.

Aquest mètode amb `systemd` és més fiable que afegir l’script al perfil de l’usuari, ja que no depèn de la sessió d’usuari i es garantirà que s'executi al primer inici del sistema.
