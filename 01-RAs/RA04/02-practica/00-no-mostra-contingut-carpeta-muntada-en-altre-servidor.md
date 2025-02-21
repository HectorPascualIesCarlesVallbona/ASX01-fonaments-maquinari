# NO MOSTRA CONTINGUT A LA CARPETA MUNGTADA EN UN ALTRE SERVIDOR    

1. **Comprovar si el muntatge s'ha fet correctament**  
   Executa:
   ```bash
        mount | grep cifs
   ```
   Hauria d'aparèixer una línia amb el recurs muntat, com per exemple:
   ```
        //192.168.1.20/nom-share on /mnt type cifs ...
   ```
   Si no apareix, el muntatge no s'ha fet correctament.

2. **Comprovar permisos i propietari de `/mnt`**  
   ```bash
        ls -ld /mnt
   ```
   Si el directori `/mnt` no té permisos suficients, pots ajustar-los:
   ```bash
        sudo chmod 777 /mnt
   ```

3. **Comprovar si realment hi ha fitxers a la carpeta compartida**  
   Fes una llista de fitxers des del servidor `nom-cpd-storage`:
   ```bash
        ls -l /srv/samba/nom-share
   ```
   Si la carpeta està buida, simplement no hi ha res per veure.

4. **Intentar crear un fitxer des del client (monitoratge)**  
   Prova de crear un fitxer de prova a `/mnt`:
   ```bash
        touch /mnt/prova.txt
   ```
   - Si dóna un error de permisos, és possible que Samba estigui bloquejant l'escriptura.
   - Si es crea correctament, fes `ls /mnt` per veure si apareix.

5. **Desmuntar i tornar a muntar**  
   Si tot sembla correcte però segueixes sense veure res, prova de desmuntar i muntar de nou:
   ```bash
   sudo umount /mnt
   sudo mount -t cifs -o username=user,password=1234 //192.168.1.20/nom-share /mnt
   ```

## **Si ens surt els següent error**
```bash
    ls -l /srv/samba/nom-share
```
Ha retornat:
```
    ls: cannot access '/srv/samba/nom-share': No such file or directory
```

1. **Crear la carpeta al servidor**  
   Executa això a `nom-cpd-storage`:
   ```bash
        sudo mkdir -p /srv/samba/nom-share
        sudo chmod 777 /srv/samba/nom-share
   ```

2. **Comprovar que la carpeta existeix**  
   ```bash
        ls -ld /srv/samba/nom-share
   ```

3. **Reiniciar el servei Samba**  
   ```bash
        sudo systemctl restart smbd
   ```

4. **Intentar muntar la carpeta des de `nom-cpd-monitor`**  
   ```bash
        sudo mount -t cifs -o username=user,password=1234 //192.168.1.20/nom-share /mnt
   ```

5. **Verificar si ara apareix contingut**
   ```bash
        ls /mnt
   ```

## **Si finalment al fer ls /mnt no mostra res 

1. **Comprova que el muntatge s'ha fet correctament**  
   A `nom-cpd-monitor`, executa:
   ```bash
        mount | grep cifs
   ```
   Si apareix la línia amb `//192.168.1.20/nom-share`, vol dir que està muntat.

2. **Desmunta i torna a muntar**  
   Si el directori `/mnt` continua buit, prova de desmuntar-lo i tornar a muntar:
   ```bash
        sudo umount /mnt
        sudo mount -t cifs -o username=user,password=1234 //192.168.1.20/nom-share /mnt
   ```

3. **Verifica que hi ha contingut dins del directori compartit**  
   A `nom-cpd-storage`, crea un fitxer de prova:
   ```bash
        echo "Fitxer de prova" | sudo tee /srv/samba/nom-share/prova.txt
   ```
   Ara, torna a `nom-cpd-monitor` i comprova si el fitxer és visible:
   ```bash
        ls -l /mnt
   ```

