# Navegación
En linux hay muchos comnados, pero es necesario aprender los mas basicos que nos serviran para poder navegar dentro de la terminal.

- **pwd** Sirve para poder ver en que **directorio/ruta estamos trabajando**.

- **ls**   Es para poder **listar el contenido** que se encuentra en nuestra ruta.
- **ls -a** Es como ls, pero este **muestra files ocultos**

- **cd** /directory  Para poder **poder movernos/acceder** a directorios y otras rutas (es como hacer doble click).
	- si el **directorio o file tiene espacios**, para acceder a es es necesario usar **"comillas dobles"**
	
- **cd ..**  Poder **regresar** al directorio anterior (flecha de retorno) (si repetimos varias veces esto podemos llegar a **/** que es la ruta raiz el final/principio de todo).

- **clear** Limpiar la terminal

# Help

- **man comando**: Abre manual detallado de un comando

- **--help | -h**: Es un switch que se añada al final de un comando para ver una ayuda de forma mas resumida.

- **apropos palabra clave**: Es util cuando uno no recuerda el nombre de un comando, se **realiza una busqueda de la palabra y sugiere comandos**
# Información_sesión

- **adduser name**: agregar nuevo user 

- **whoami** Nos **muestra el usuario actual**

- **id**: Proporciona **información detallada sobre la identidad del usuario** en el sistema.

- **hostname**: Muestra el nombre de la maquina o servidor en el que se esta trabajando.

- **uname**: Muestra informaicon basica del sistema.
# Manipulación de Files

En linux cuando un programa se ejecuta , el SO le asigna 3 canales de datos numericos, estos son llamados **File Descriptors (FD)

| **FD** | **Nombre**      | **Abreviatura** | **Por defecto conectado a...** |
| ------ | --------------- | --------------- | ------------------------------ |
| **0**  | Standard Input  | `stdin`         | El teclado                     |
| **1**  | Standard Output | `stdout`        | **La pantalla (terminal)**     |
| **2**  | Standard Error  | `stderr`        | **La pantalla (terminal)**     |
Al entender esto es cuando uno se da cuenta el porque del comando **2>/dev/null** puede redireccionar la salida (**>**) de los errores 

- **cat**: Cat (concatenar) es usado para **leer datos de un file** (stdin) y los escribe en la salida estándar (stdout)

- **cp**: Sirve para **copiar/duplicar** manteniendo el file original intacto (resultado 2 files)

- **mv** Sirve para poder **renombrar files/directorios** (resultado 1 file)

- **rm**: Su función es **eliminar files**
	- **rm -rf** Muy usado para **borrar todo el contenido de una carpeta** sin preguntar nada
	
 - **which** Sirve para **rastrear la ruta absoluta de archivos ejecutables** si solo si esta dentro del $Path (variables de entorno). Si es un Alias o una Buiolt-ins no podra darnos lo que queremos.

- **type** Sirve para **poder identificar que clase de archivo** es si es un builtin, alias u otro.

# Sistema

- **env**: Lista las **variables de entorno**
- **lsblk**: Lista los **dispositivos de bloque**, como los discos duros.
- **lsusb**: Muestra los **dispositivos USB** conectados
- **lsof**: Lista todos los **archivos abiertos** en el sistema

# Red

- **ifconfig / ip**:  Se utiliza **para ver y configurar la información de la red** y direcciones ip

- **netstat / ss**: Muestra el **estado de la red y las sesiones activas**