En el arranque de Linux Hay 4 Etapas.

# Version Integrada

**Etapa 0: Boton de Encendido 
- La fuente de poder envía electricidad real a la Placa Madre
- Los ventiladores giran y los LEDs se prenden.
**Etapa1: (BIOS / UEFI )
- Se ejecuta un pequeño software que vive en un chip de la placa (Firmware), Hace el **POST** (Power-On-Self-Test) checa si tiene Ram, Teclado, CPU hardware necesario para funcionar, Una vez que el hardware esta Ok, busca un disco duro (SATA/NVMe)y lee el primer sector.
**Etapa 2:  El Bootloader(GRUB)
- La BIOS carga los primeros 512 bytes del disco (MBR) o busca una partición especial (EFI). Ahí vive el Bootloader (En linux suele ser GRUB)
-  Carga el menu donde uno elige que arrancar, cuando se elige Linux. El Bootloader va al disco, busca al Kernel y lo carga en la RAM
**Etapa 3: El cerebro despierta (El kernel)
- El archivo del kernel (vmlinuz) se descomprime en la RAM
-  El Kernel toma el control total del Hardware, detecta la tarjeta gráfica, el WIFI, monta el sistema de archivos (lo hace legible).
- Una vez que el Kernel esta listo. Ahora este necesita que alguien administre los procesos y ejecuta al Primer proceso
**Etapa 4: El gerente (Init / Systemd)
- El Kernel ejecuta /sbin/init (o systemd en sistemas modernos) este es el padre de todos PID 1.
- systemd lee su lista de tareas, arranca la red, interfaz grafica, el sonido y pedir el login.
- Final aparece la pantalla para el Login.

**¡Peligro !**
Ataques al Bootloader ("Evil Maid"): Si un hacker tiene acceso físico a tu PC por 2 minutos, puede editar el GRUB (Etapa 2) para decirle al Kernel: "Oye, arranca, pero no me pidas contraseña y dame una terminal de Root" (se hace añadiendo init=/bin/bash al final de la línea de arranque).