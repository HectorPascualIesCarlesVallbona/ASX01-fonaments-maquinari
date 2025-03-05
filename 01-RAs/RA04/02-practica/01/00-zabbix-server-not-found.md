### **1. Comprovar si Zabbix Server està instal·lat**
Executa aquesta comanda per veure si el paquet està instal·lat:
```bash
dpkg -l | grep zabbix-server
```
Si no retorna cap línia, significa que **no està instal·lat** i hauràs d'instal·lar-lo.

---

### **2. Instal·lar Zabbix Server**
Si el paquet no està instal·lat, prova d'instal·lar-lo de nou:
```bash
sudo apt update
sudo apt install zabbix-server-mysql zabbix-frontend-php -y
```
Si tens errors de dependències, fes:
```bash
sudo apt --fix-broken install -y
```
I torna a intentar la instal·lació.

---

### **3. Verificar si el servei està disponible**
Després de la instal·lació, comprova si el servei existeix:
```bash
systemctl list-units --type=service | grep zabbix
```
Si el servei **zabbix-server** apareix a la llista, intenta reiniciar-lo:
```bash
sudo systemctl enable zabbix-server
sudo systemctl start zabbix-server
sudo systemctl status zabbix-server
```