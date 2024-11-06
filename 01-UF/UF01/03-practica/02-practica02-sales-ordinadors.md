# PRACTICA02 - Sales ordinadors

[Sales ordinadors](https://moodle.iescarlesvallbona.cat/pluginfile.php/186525/mod_resource/content/4/Pr%C3%A0ctica%20UF2.pdf)

## Opció Alternativa per a Instal·lació OEM en Ubuntu 24.10

1. **Utilitza la ISO d'Ubuntu Desktop per a la Instal·lació Normal**

   Descarrega la ISO d'Ubuntu 24.10 Desktop i inicia la instal·lació.

2. **Crea un Usuari Temporal durant la Instal·lació**

   Durant la configuració d'Ubuntu, crea un usuari temporal que utilitzaràs per preconfigurar el sistema.

3. **Configura el Sistema i Instal·la el Programari Necessari**

   Després d'haver iniciat sessió amb l'usuari temporal, fes qualsevol configuració que necessitis:
   - Instal·la aplicacions i programari addicional.
   - Configura els ajustaments del sistema.
   - Personalitza el fons de pantalla o altres configuracions visuals.

4. **Crea un Script de Primer Inici per a l'Usuari Final**

   Crea un script que s'executi automàticament en el primer inici per crear el compte de l’usuari final. Aquí tens un exemple d’script que demanarà el nom d'usuari i la contrasenya de l'usuari final:

   - Obre una terminal i crea un fitxer anomenat `firstboot.sh` a la carpeta `/usr/local/bin/`:

     ```bash
     sudo nano /usr/local/bin/firstboot.sh
     ```

   - Enganxa aquest contingut a l'script:

     ```bash
        #!/bin/bash
        echo "Configuració del compte d'usuari final"
        read -p "Nom d'usuari: " USERNAME
        read -s -p "Contrasenya: " PASSWORD
        echo
        sudo adduser --disabled-password --gecos "" "$USERNAME"
        echo "$USERNAME:$PASSWORD" | sudo chpasswd
        sudo usermod -aG sudo "$USERNAME"
        echo "Usuari final creat amb èxit!"

        # Configura el nom de host
        echo "Introdueix el cognom per configurar el nom de host (wildpenguin[Cognom1]):"
        read COGNOM
        HOSTNAME="wildpenguin${COGNOM}"

        # Estableix el nom de host
        sudo hostnamectl set-hostname "$HOSTNAME"
        echo "$HOSTNAME" | sudo tee /etc/hostname

        # Actualitza el fitxer /etc/hosts
        sudo sed -i "s/127.0.1.1.*/127.0.1.1 $HOSTNAME/" /etc/hosts
        echo "Nom de host configurat com a $HOSTNAME"

        # Desactiva el servei després d'executar-se
        sudo systemctl disable firstboot.service
        sudo rm -- "$0"
     ```

5. **Configura un Servei de `systemd` per Executar l'Script de Primer Inici**

   Crea un servei de `systemd` per executar l'script en el primer inici i després eliminar-se:

- Crea el fitxer de servei:

     ```bash
     sudo nano /etc/systemd/system/firstboot.service
     ```

- Enganxa aquest contingut:

     ```ini
     [Unit]
     Description=Configuració de l'usuari final en el primer inici

     [Service]
     Type=oneshot
     ExecStart=/usr/local/bin/firstboot.sh
     RemainAfterExit=true

     [Install]
     WantedBy=multi-user.target
     ```

6. **Activa el Servei**

   Activa el servei perquè s'executi en el primer inici:

   ```bash
   sudo systemctl enable firstboot.service
   ```

7. **Apaga el Sistema i lliura'l a l'Usuari Final**

   En el primer inici, l'script de `firstboot.sh` s'executarà i demanarà al nou usuari que introdueixi el seu nom d'usuari i la contrasenya. Després d’això, el servei i l'script s'eliminaran automàticament.
