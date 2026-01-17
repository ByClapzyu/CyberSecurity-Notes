En el arranque de Linux Hay 4 Etapas.

# Version Integrada

**Etapa 0: Boton de Encendido 
- La fuente de poder envía electricidad real a la Placa Madre
- Los ventiladores giran y los LEDs se prenden.
**Etapa1: (BIOS / UEFI )
- Se ejecuta un pequeño software que vive en un chip de la placa (Firmware), Hace el **POST** (Power-On-Self-Test) checa si tiene Ram, Teclado, CPU hardware necesario para funcionar, Una vez que el hardware esta Ok, busca un disco duro (SATA/NVMe)y lee el primer sector.
**Etapa 2:  El Bootloader(GRUB)
- La BIOS carga los primeros 512 bytes del disco (MBR) o busca una partición especial (EFI). Ahí vive el Bootloader (En linux suele ser GRUB)
- 
