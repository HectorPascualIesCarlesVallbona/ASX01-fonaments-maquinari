# PRACTICA02 - Sales ordinadors

[Sales ordinadors](https://moodle.iescarlesvallbona.cat/pluginfile.php/186525/mod_resource/content/4/Pr%C3%A0ctica%20UF2.pdf)

## Personalitza per a OEM

### Passos per Configurar un Nom de Host Dinàmic amb un Servei de systemd

1. Crea el Fitxer de Servei

Crea el fitxer de servei en la ubicació correcta:

```bash
sudo nano /etc/systemd/system/set-hostname.service
```

2. Afegeix el Contingut del Fitxer

Copia i pega el contingut següent

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

3. Activa el Servei

Activa el servei perquè s'executi automàticament en el pròxim inici:

```bash
sudo systemctl enable set-hostname.service
```

4. Reinicia i Configura el Nom de Host

Quan el sistema arrenqui, el servei demanarà el cognom i configurarà el nom de host amb el format wildpenguin[Cognom1]. Un cop configurat, el servei es desactivarà automàticament i ja no tornarà a executar-se en futurs inicis.
