# PISSARRA OPCIONS ARRENCADA SISTEMA

## 1. **Definició**
Procès seqüencial per posar en funcionament maquinari i programari => SO funcioni correctament

## 2. **Etapes del procès arrencada**: (les definim i ara les veurem totes)
1. Init hardware via BIOS-UEFI
2. Init bootloader
3. Loading kernel i init SO

- **Què és el kernel**? (*.5 punts examen*)
És el nucli del SO, la seva part més fonamental i essencial, el cor. És el component intermediari entre el hardware i el software, i s'encarrega de gestionar els recursos del sistema i proporcionar-los als programes i aplicacions de forma controlada i eficient: gestió de processos, gestió de la memòria, gestió del maquinari, gestió del sistema de fitxers, seguretat i permisos, comunicació entre processos

## 3. **FASES PROCÈS**

### 3.1 **BIOS-UEFI**

#### 3.1.1 **BIOS (Basic Input/Output System)**
- Firmware executa a 1er nivell al fer `on` a l'ordinador
- **Power-On Self Test - POST** => escaneig d'operativitat del hardware bàsic
- Limitacions: 
    1. discos < 2TB
    2. no `secure boost`
    **Què és el Secure Boost**? (*.5punts examen*)
    - És una funcionalitat de seguretat integrada en UEFI que garanteix que només es carreguin sistemes operatius i components del sistema (bootloaders, kernels, etc.) signats amb claus digitals verificades durant el procés d’arrencada. Aquesta verificació ajuda a prevenir que codi maliciós o no autoritzat prengui control del sistema durant l’arrencada.
    3. arrencada lenta
    4. limitacions del setup - configuració

#### 3.1.2 UEFI (Unified Extensible Firmware Interface)
- Successor de BIOS millorat.
- Avantatges:
    - discos < o > 2TB.
    - Arrencada ràpida.
    - Secure Boot
    - Interfícies gràfica.
    - Flexibilitat en el setup

### 3.2 BOOTLOADER (Gestor d'arrencada)
- És un programa que carrega el sistema operatiu al hardware després de la inicialització del firmware (inicialització hardware)
- Tipus:
    1. GRUB, Grand Unified Bootloader
        - Legacy i GRUB2 -> suporta configuracions avançades
    2. LILO, Linux loader
        - Antic, menys flexible
    3. Windows boot Manager
    4. System-boot -> integrat a `systemd`
    **Què és systemd**? (*.5 punts examen*)
    És un sistema d'inici (init system) i gestor de serveis per a sistemes operatius basats en Linux. És responsable de gestionar el procés d'arrencada del sistema, la càrrega de serveis, i moltes altres funcions relacionades amb la configuració i operació del sistema.

### **3.2. Kernel i càrrega del SO**
- Acaba bootloader -> transfereix control al kernel
- Kernel:
    - Munta fitxers sistema arrel: fer accessible dispositiu físic amb punt d'accès lògic. El sistema de fitxers principal del SO pugui ser gestionat i accessible al dispositiu físic o partició del disc. 
    - Loading processos inicials: `init`o `systemd`