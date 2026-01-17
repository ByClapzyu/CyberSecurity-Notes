# Programa vs Proceso

- **Programa**: Es el archivo guardado en el disco duro (/bin/bash o app.exe). Es pasivo, está muerto, no hace nada.
- **Proceso**: Es lo que ocurre cuando el Kernel toma ese programa, lo carga en la RAM y le da vida (ciclos de CPU). es activo.

Cada proceso tiene un DNI único llamado PID (Process ID).

Analogia "La receta vs El cocinero"
- **Programa**: Es la receta escrita, está ahí, quieta, no alimenta a nadie.
- **Proceso**: Es el cocinero ejecutando ese receta.

**La Familia de Procesos** (El arbol Genealógico): En Linux, los procesos no apareen de la nada (excepto uno).
- **PID 1**(systemd/init): Es el Adan o la Eva de todos los procesos. Es el primer proceso que arranca el kernel
- **Fork** (Clonación): Cuando **abres una terminal**, el proceso ventana se clona a si mismo (fork) para crear un hijo llamado Bash.
- Todos los procesos tienen un **Padre**  (PPID- Parent Process ID).
# commando top
##(No sirve muy bien para ver quien es hijo de quien)
- **PID** (Process ID): El número de identificación. (Si se requiere matar un proceso hay que apuntar a este numero)
- **USER**: El dueño de proceso (si se ve un proceso raro corriendo ocmo root es alarmante).
- **PR (Priority)** y **NI (Nice)**: "Analogia fila VIP"
	Imagina una fila para entrar al antro (CPU). eL Kernel decide quien entra primero.
- **NI** (Niceness): Es que tan amable es un proceso. Un numero alto + significa soy muy amable, dejen pasar a los demas primero (baja prioridad). Un numeor negativo  significa soy egoita y urgente, ¡muevanse! (altaprioridad).
- **S (State/Estado)**:
	- **R (Running)**: Esta corriendo ahora mismo
	- **S (Sleeping)**: Esta esperando input del teclado o datos del disco.
	- **Z (Zombie)**: Esta muerto, no consume RAM ni CPU, pero ocupa número de PID en la tabla.
		##el proceso ya murio, pero el padre no ha leído su certificado de defuncion (exit code).

Angulo de Seguridad
- **Aislamiento**: Un proceso no debe poder leer la memoria de otro.
- **Privilegios (SUID)**:  A veces, un usuario normal necesita hacer cosas de administrador (como cambiar su contraseña). Los programas son bit SUID permiten que un plebeyo ejecute un proceso con poderes de Rey temporalmente.

# Commando ps auxf
![[Pasted image 20260116183953.png]]
Ideal para ver los hijos
En la imagen puedo ver que en mi terminal cuelga bash y de bash cuelga el comando ejecutado de ps auxf.

**Satus de ps aux**
- **R (Running)**: El proceso esta usando la CPU ahora mismo o esta en la fila.
- **S (Sleeping**): Esperando una llamada/evento
- **D (Disk Sleep)**: Esperando una operacion (I/O) de hardware como disco duro o red que no se puede interrumpir.
- **Z (Zombie)**: Termino, pero el padre no ha recogido su codigo de salida.
- **T (Stopped)**: Proceso pausado manualmente con ctrl + z o esta siendo auditado por un depurador

**Simbolos**
- **< (High Priority): El VIP
- **N (Low Priority)**: humilde
- **s (sesion Leader)**: Jefe de la sesión
- **l (Multi-threaded)**: Multitask
- **+ (Foreground)**: EL prota

**Funcionamiento de la creación y muerte  de un proceso**

	## Voy a crear un proceso y lo mandare a segundo plano (background) con **&** 
	- nano test_proceso.txt & 
	Este me dio un PID que es el [1] 3792
	buscare el proces son ps aux | grep nano y lo
	matare con kill 3792
# Commando de practica

ps aux | awk '{print $8}' | cut -c1 | sort | uniq -c