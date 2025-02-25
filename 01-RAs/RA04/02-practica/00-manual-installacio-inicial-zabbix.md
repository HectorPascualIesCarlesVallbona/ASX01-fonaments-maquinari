# **Configuració del servidor de monitoratge (Zabbix Server)**
[problemes intal.lació Zabbix](00-problemes-installacio-zabbix.md)
### 🔹 **Instal·lació de Zabbix**
1. **Afegir el repositori oficial:**
   ```bash
      wget wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4+ubuntu20.04_all.deb

      sudo dpkg -i zabbix-release_6.0-4+ubuntu20.04_all.deb
      sudo apt update
   ```

2. **Instal·lar el servidor i la base de dades**:
   ```bash
      sudo apt install zabbix-server-mysql zabbix-frontend-php zabbix-agent zabbix-sql-scripts mysql-server -y
   ```

3. **Configurar la base de dades**:
   ```bash
      sudo mysql -u root -p
   ```

   A MySQL:
   ```sql
      CREATE DATABASE zabbix CHARACTER SET utf8mb4 COLLATE utf8mb4_bin;
      CREATE USER 'zabbix'@'localhost' IDENTIFIED BY 'zabbixpassword';
      GRANT ALL PRIVILEGES ON zabbix.* TO 'zabbix'@'localhost';
      FLUSH PRIVILEGES;
      EXIT;
   ```

4. **Configurar el servidor**:
   ```bash
      sudo nano /etc/zabbix/zabbix_server.conf
   ```
   Modifica:
   ```
      DBName=zabbix
      DBUser=zabbix
      DBPassword=zabbixpassword
   ```

5. **Reiniciar el servei**:
   ```bash
      sudo systemctl restart zabbix-server
   ```

6. **Verificació**:
   [conectar host a mv per ssh](03-connect-server-via-ssh.md)
   [problemes conexió host a mv](00-host-pc-no-conecta-per-ssh-a-mv.md)
   - Accedeix a `http://192.168.1.30/zabbix`.
