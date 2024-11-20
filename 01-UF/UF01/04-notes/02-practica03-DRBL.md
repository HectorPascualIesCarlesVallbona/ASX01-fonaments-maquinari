Un **servidor DRBL** (Diskless Remote Boot in Linux) és una solució que permet gestionar de manera centralitzada l'arrencada i la clonació de sistemes operatius en múltiples màquines clients. Aquest sistema s'utilitza principalment en entorns on es requereix instal·lar, actualitzar o clonar múltiples ordinadors des d'un únic servidor.

### Funcionalitats Principals

1. **Arrencada de Clients sense Disc Dur (Diskless Boot)**:
   - Els clients poden arrencar directament des del servidor DRBL mitjançant la xarxa, utilitzant el protocol **PXE** (Preboot Execution Environment). Això és útil per a màquines sense sistema operatiu instal·lat o per a entorns de treball temporals.

2. **Clonació de Sistemes amb Clonezilla**:
   - DRBL integra **Clonezilla**, que permet fer clonacions massives de discos o particions en mode multicast o unicast. Això és molt eficient per desplegar imatges de sistemes operatius idèntiques a múltiples clients alhora.

3. **Gestió Centralitzada de Sistemes**:
   - Permet gestionar configuracions de xarxa, distribució de programari i actualitzacions des d'un sol servidor. Això redueix la necessitat de configuracions manuals a cada màquina client.

### Components Clau

- **DRBL**: Proporciona la infraestructura per arrencar i gestionar màquines clients sense disc local.
- **Clonezilla**: Utilitzat per a la clonació de discos i particions.
- **DHCP i TFTP**: Protocols que permeten l'assignació dinàmica d'adreces IP i la transferència de fitxers necessaris per a l'arrencada PXE.

### Avantatges

- **Estalvi de Temps**: Amb DRBL, es poden clonar i configurar centenars d'ordinadors simultàniament.
- **Reducció de Recursos**: Els clients poden funcionar sense disc dur local.
- **Flexibilitat**: És compatible amb diferents sistemes operatius com Linux, Windows i altres.

