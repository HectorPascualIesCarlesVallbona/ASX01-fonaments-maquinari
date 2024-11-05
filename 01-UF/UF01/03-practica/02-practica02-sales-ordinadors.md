# PRACTICA02 - Sales ordinadors

[Sales ordinadors](https://moodle.iescarlesvallbona.cat/pluginfile.php/186525/mod_resource/content/4/Pr%C3%A0ctica%20UF2.pdf)

## Personalitza per a OEM

Utilitza `cloud-init` per Configurar un Usuari Final (Alternativa DIY)

Amb `cloud-init` per preconfigurar el sistema i permetre que l'usuari final creï el seu propi compte.

1. **Instal·la `cloud-init` (si no està instal·lat)**:

   ```bash
   sudo apt update
   sudo apt install cloud-init
   ```

2. **Crea un fitxer de configuració per a l'usuari final**:
   - Crea un fitxer a `/etc/cloud/cloud.cfg.d/99_oem.cfg` amb el següent contingut:

     ```yaml
     #cloud-config
     system_info:
       default_user:
         name: oem
         lock_passwd: True
         gecos: "OEM User"
         sudo: ["ALL=(ALL) NOPASSWD:ALL"]
         shell: /bin/bash
     ```

3. **Reinicia el Sistema**
   - En reiniciar, el sistema es configurarà com si fos una instal·lació OEM, i podràs personalitzar la configuració abans de lliurar-la a l'usuari final.

Aquestes opcions et permetran tenir un sistema preparat per a un usuari final, similar a una instal·lació OEM.
