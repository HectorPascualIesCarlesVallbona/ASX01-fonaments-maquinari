# PRACTICA02 - Sales ordinadors

[Sales ordinadors](https://moodle.iescarlesvallbona.cat/pluginfile.php/186525/mod_resource/content/4/Pr%C3%A0ctica%20UF2.pdf)

## Personalitza per a OEM

### Passos per Configurar un Nom de Host Dinàmic amb un Servei de systemd

D’acord, aquí tens els passos per crear el fitxer de servei `systemd` per parts:

### 1. Crea el Fitxer de Servei

Primer, crea el fitxer de servei en la ubicació correcta:

```bash
sudo nano /etc/systemd/system/set-hostname.service
```

Això obrirà l'editor `nano` amb permisos d'administrador per crear el fitxer de servei.

### 2. Afegeix el Contingut del Fitxer

Copia el contingut següent i enganxa’l al fitxer o escriu-lo manualment:

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

Un cop hagis afegit el contingut, guarda el fitxer:

1. Prem `Ctrl + O` i després `Enter` per desar els canvis.
2. Prem `Ctrl + X` per sortir de l'editor.

### 3. Activa el Servei

Ara, activa el servei perquè s'executi automàticament en el pròxim inici:

```bash
sudo systemctl enable set-hostname.service
```

### 4. Reinicia i Configura el Nom de Host

Quan el sistema arrenqui, el servei demanarà el cognom i configurarà el nom de host amb el format wildpenguin[Cognom1]. Un cop configurat, el servei es desactivarà automàticament i ja no tornarà a executar-se en futurs inicis.
