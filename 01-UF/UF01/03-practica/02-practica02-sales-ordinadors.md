# PRACTICA02 - Sales ordinadors

[Sales ordinadors](https://moodle.iescarlesvallbona.cat/pluginfile.php/186525/mod_resource/content/4/Pr%C3%A0ctica%20UF2.pdf)

## Personalitza per a OEM

    - Obre la terminal i crea un script nou en el directori /etc/profile.d/ per tal que s'executi en el primer inici de sessió

    ```bash
        sudo nano /etc/profile.d/set_hostname.sh
    ```

    - Afegeix aquest contingut a l’script. Després desa i tanca

    ```bash
        #!/bin/bash
        if [ ! -f /etc/hostname_set ]; then
            echo "Introdueix el teu primer cognom per configurar el nom de host:"
            read COGNOM1
            HOSTNAME="wildpenguin${COGNOM1}"
            sudo hostnamectl set-hostname "$HOSTNAME"
            echo "$HOSTNAME" | sudo tee /etc/hostname
            sudo sed -i "s/127.0.1.1.*/127.0.1.1 $HOSTNAME/" /etc/hosts
            sudo touch /etc/hostname_set
            echo "Nom de host establert a $HOSTNAME. Reinicia per aplicar els canvis."
        fi
    ```

    - Fes Executable l'script

    ```bash
        sudo chmod +x /etc/profile.d/set_hostname.sh
    ```

- Com Funciona l'script
      Quan un usuari iniciï sessió per primera vegada:
  - L’script demanarà el primer cognom de l'usuari.
  - El nom de host es crearà amb el format wildpenguin[Cognom1].
  - El sistema desarà el nou nom de host i evitarà que l’script s’executi en futures iniciades de sessió.
