# IP de la màquina virtual i el nostre host no està a la mateixa xarxas

---

### 🔹 **Opció 1: Afegir una IP a la mateixa xarxa que la MV al teu host**
Pots afegir una IP secundària al teu host dins la xarxa **192.168.1.X**, de manera que pugui comunicar-se amb la MV.

1️⃣ Executa això al **teu host** (ordinador personal):
```bash
sudo ip addr add 192.168.1.100/24 dev wlp1s0
```
(Aquesta IP és només un exemple, assegura't que no estigui duplicada dins la xarxa)

2️⃣ Comprova que ara tens una IP dins **192.168.1.X**:
```bash
ip a
```

3️⃣ Fes ping a la MV per veure si ara respon:
```bash
ping -c 4 192.168.1.30
```

4️⃣ Si el ping funciona, intenta connectar-te per SSH:
```bash
ssh user@192.168.1.30
```

---

### 🔹 **Opció 2: Canviar la IP de la MV perquè estigui a la mateixa xarxa**
Si vols que la MV estigui a la mateixa xarxa que el teu host (192.168.19.X), has de modificar la seva configuració de xarxa:

1️⃣ Entra a la MV i edita el fitxer de configuració de xarxa:
```bash
sudo nano /etc/netplan/01-netcfg.yaml
```
(O pot ser `/etc/netplan/50-cloud-init.yaml` depenent de la configuració)

2️⃣ Modifica la IP estàtica per una dins **192.168.19.X** (per exemple, 192.168.19.100):
```yaml
network:
  ethernets:
    enp0s3:
      dhcp4: no
      addresses:
        - 192.168.19.100/24
      gateway4: 192.168.19.1
      nameservers:
        addresses:
          - 8.8.8.8
```

3️⃣ Desa (`Ctrl + X`, `Y`, `Enter`) i aplica els canvis:
```bash
sudo netplan apply
```

4️⃣ Fes ping des del **teu host** a la nova IP de la MV:
```bash
ping -c 4 192.168.19.100
```

Si tot funciona bé, ara la MV i el teu host haurien d’estar a la mateixa xarxa i podràs accedir-hi per SSH o HTTP.

