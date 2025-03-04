# SI adaptador puente no funciona


🔹 **1️⃣ Modifica Netplan**  
Edita el fitxer:
```bash
sudo nano /etc/netplan/50-cloud-init.yaml
```
Modifica la secció `enp0s8` així:
```yaml
network:
  version: 2
  ethernets:
    enp0s3:  # NAT (Internet)
      dhcp4: true
    enp0s8:  # Host-Only (Xarxa amb el teu host)
      dhcp4: no
      addresses:
        - 192.168.56.100/24  # Nova IP dins la xarxa vboxnet0
      nameservers:
        addresses:
          - 8.8.8.8
          - 1.1.1.1
```
🚨 **Elimina la secció `routes` sota `enp0s8`**, ja que **un adaptador Host-Only no necessita passarel·la (`gateway`)**.

---

🔹 **2️⃣ Aplica els canvis**
Desa (`Ctrl + X`, `Y`, `Enter`) i aplica:
```bash
sudo netplan apply
```

---

🔹 **3️⃣ Comprova la connexió**
Des del teu **host**, prova el `ping`:
```bash
ping -c 4 192.168.56.100
```
Si funciona, prova la connexió SSH:
```bash
ssh -p 2222 user@192.168.56.100
```

---

### **✅ Conclusions**
- **Ara la màquina virtual tindrà Internet via NAT (`enp0s3`) i estarà accessible des del teu host (`enp0s8`).**  
- **Amb aquests canvis, hauria de funcionar la connexió SSH correctament. 🚀**