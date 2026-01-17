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

# Comando

Para ver lo que paso durante esos segundo de arrango podemos usar el comando 
- dmesg | head -n 20
Lo que veremos: Es el diario del Kernel desde el segundo 0.0000. Verás cosas como:
- [0.000000] Linux version... (El Kernel presentándose).
- [0.000000] Command line: BOOT_IMAGE=... (Lo que el Bootloader le dijo al Kernel).
- [0.xxx] Memory: ... (El Kernel contando la RAM).
Podemos hacer uso de esto si algunas vez tenemos problemas si el kernel no detecto algo al inicio o si dio error.

# Versión VM

**Etapa 0: El Botón de Encendido (Click del Mouse)**
- Aquí no hay electricidad solo es dar al boton de "Start" en el virtualizador
- El software reserva un pedazo de la RAM real y le dice a la VM: "Toma, esta es tu memoria".

**Etapa 1: BIOS Virtual (El Chip de Mentira)**
- Un programa de software fingiendo ser un chip. (Se puede ver  el logo de VirtualBox o VMware al arrancar, no el de Dell o HP).
- Ejecuta un POST falso y  Checa el hardware virtual que configuraste. "¿Tengo 4GB de RAM virtual? Sí".
 - Salida: Busca el disco duro virtual (un archivo .vdi en la carpeta de documentos) y lee el primer sector.

**Etapa 2: El Bootloader (GRUB)**
- El software GRUB que vive dentro del archivo .vdi. Nos muestra el menú azul.

**Etapa 3: El Kernel (El Cerebro Engañado)**
- Se carga en la RAM virtual y escanea el hardware, pero no puede ver nuestra  NVIDIA, ve un "Adaptador Gráfico Virtual SVGA". Tampoco puede ver nuestra  WiFi Intel, ve una "Tarjeta de Red Ethernet Virtualizada" (conectada por cable simulado). y no puede ver nuestro Disco Duro "VBOX HARDDISK".
- Carga drivers genéricos o especiales para virtualización (Guest Additions / VMware Tools).

**Etapa 4: Init / Systemd (El Gerente)**
- Acción: Inicia los servicios igual que en la física.
- Final nos muestra la misma pantalla de login.