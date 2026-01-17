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
- **PID** (Process ID): El número de identificación. (Si se requiere matar un proceso hay que apuntar a este numero)
- **USER**: El dueño de proceso (si se ve un proceso raro corriendo ocmo root es alarmante)