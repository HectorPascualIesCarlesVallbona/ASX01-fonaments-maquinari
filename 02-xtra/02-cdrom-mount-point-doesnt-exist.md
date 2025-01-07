# Error al muntar cdrom

1. **Crea el punt de muntatge**:
   ```bash
   sudo mkdir -p /media/cdrom
   ```

2. **Munta el dispositiu**:
   ```bash
   sudo mount /dev/cdrom /media/cdrom
   ```

3. **Verifica que s'ha muntat correctament**:
   ```bash
   df -h
   ```