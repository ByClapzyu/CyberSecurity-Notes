# Historia de los Anillos Perdidos

En informatica se suele conocer  dos anillos el Ring 0 (kernel space) y el Ring 3 (user space),  Pero originalmente, cuando intel diseño la arquitectura x86  (las que usan casi todas las PC y Laptops), diseñaron **4 Anillos de Protección**

- **Ring 0**: Kernel (Privilegio Total)
- **Ring 1**: Controladores de dispositivo (Drivers) critircos.
- **Ring 2**: Controladores de dispositivo menores criticos.
- **Ring 3**: Aplicaciones de Usuario (nivel mas bajo)

Cuando se crearon los sistemas operativos modernos (Unix, Linux, Windows NT), los desarolladores querian que sus sistemas funcionaran en **cualquier procesador** no solo en intel x86.
- Otras arquitecturar de CPU solo tenian **2 modos** Modo supervisor (Todo) y Modo Usuario (Nada).
- Para no tener que reescribir el kernel para cada tipo de procesador, los creadores de Linux y Windows dijeron: "hay que ignorar los anillos 1 y 2 de Intel. Usemos solo el 0 y 3. Así nuestro SO es compatible con todo"

En la **Seguridad Moderna** han aparecido nuevos anillos conceptuales .Con la llegada de la virtualización, surgio un problema: Si se tiene 3 máquinas virtuales corriendo Linux, cada una cree que tiene el Ring 0. Pero no puede tener control real del Hardware al mismo tiempo.

- **Ring -1**: Aqui vive el Hypervisor. Este controla los Kernels de las máquinas virtuales.

Para saber si nuestro procesador tiene capacidad para usar el Ring -1 podemos usar uno de los siguientes comandos.
- lscpu | grep -i virtualization
- grep -E --color 'vmx|svm' /proc/cpuinfo
# Vulnerabilidad (Blue Pill)

Es un ataque donde un rootkit (virus) se instalara en el Ring -1. El sistema operativo cree que está en el Ring 0 y que tiene el control, pero en realidad esta viviendo dentro de una tipo matrix controlada por el virus.  Es indetectable para el antivirus porque el antivirus vive en el Ring 3 (aveces en 0), y no puede ver hacia abajo.
# Kernel Space vs User Space

En la arquitectura de computadoras moderna **(x86)**  , la CPU opera en diferentes **niveles de privilegio** (protection rings)

- Kernel Space (**Ring 0** ):  Es el modo de ejecución privilegiado. Aquí reside el núcleo del sistema operativo. El código que se ejecuta aquí tiene **acceso total y sin restricciones**  a la memoria, al procesador y a los periféricos (**hardware**)
- User Space (**Ring 3**): Es el modo restringido donde corren las aplicaciones (navegador, scriptrs, apps). Aquí, el código **no puede tocar el hardware directamente** ni acceder a la memoria reservada para el kernel.

Para que un programa de usuario haga su función (como guardar un archivo), debe pedirselo al kernel que lo haga por él. Este pedido se llama **System Call** (llamada de sistema).

**Analogía de Avión**
- **Hardware** (CPU, RAM, Disco): Es el avión (motor,combustible,alerones)
- **Kernel Space**: Es la cabina del piloto donde tiene acceso directo a todo, puede apagar los motores, girar el avión a cambiar de dirección.
- **User Space**: Es la cabina de pasajeros
- **System Call**: Las azafatas . Si un pasajero quiere agua (acceso a disco), no se levanta y va a la cabina a por ella. Este tiene que llamar a la azafata (system call), la azafata verifica si el pasajero tiene derecho a pedir eso, va y trae el agua

El peligro de que tenga acceso directo puede ser la **inestabildad** ya que se puede mover algo que no debe y el avión puede caer (pantallazo azul) y la **seguridad** porque no se sabe si el pasajero tiene intenciones malas y puede estrellar el avión o desviar el vuelo. (manipular los datos).

Ángulo de Seguridad
- Aislamiento (**Isolation**): La separación existe para que, si el navegador web se crashea, solo se muera ese pasajero y el avión (SO) siga funcionando. Si no hubiera separación, un error en la app apagaria la PC.
- **Escalada de Privilegios**: La mayoria de ataques intentan burlar esta frontera. De tener acceso como usuario normal (user space) por medios de buggs en el kernel pueden saltar la barrera y entrar en el Ring 0. Si lo logran tiene control total (Roo o System)
- **RootKit**: Son virus que se instalan en el Kernel Space. Son casi invisibles porque controlan la realidad del sistema. Pueden decirle al antivirus que no hay nada sospechoso y el antivirus puede creerle (el antivirus suele estar en User Space).
# Commandos utiles 

- **strace** (System Trace):  Sirve para poder **ver cada call system que se hace al ejecutar algo**. Es como si se pusiera una camara a la azafata para ver cada vez que el pasajero le pide algo al piloto
	- ##Ejemplo
	- ***strace ls /home***
	Al ejecutarlo podemos ver una cascada de texto rapido de todo lo que sucede atras de un ls. Al estar el ls en User Space se puede apreciar lineas que dicen:
	- **openat(....)**: Oye Kernel, abre esta carpeta
	- **getdents(....)**: Oye kernel, dame las entradas del directorio (Get Directory Entries)
	- **write(1, "Document1 Document2 ....")**: Oye kernel, escribe estos nombres en la pantalla.
	##Si se intenta acceder a cierto recurso donde no tenemos acceso puede aparecer algo asi:
	- **openat(..., "/etc/shadow", ...) = -1 EACCES (Permission denied)**
	