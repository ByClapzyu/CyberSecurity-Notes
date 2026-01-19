# Navegación
En linux hay muchos comnados, pero es necesario aprender los mas basicos que nos serviran para poder navegar dentro de la terminal.

- **pwd** Sirve para poder ver en que **directorio/ruta estamos trabajando**.

- **ls**   Es para poder **listar el contenido** que se encuentra en nuestra ruta.
- **ls -a** Es como ls, pero este **muestra files ocultos**

- **cd** /directory  Para poder **poder movernos/acceder** a directorios y otras rutas (es como hacer doble click).
	- si el **directorio o file tiene espacios**, para acceder a es es necesario usar **"comillas dobles"**
	
- **cd ..**  Poder **regresar** al directorio anterior (flecha de retorno) (si repetimos varias veces esto podemos llegar a **/** que es la ruta raiz el final/principio de todo).

- **whoami** Nos **muestra el usuario actual**

- **clear** Limpiar la terminal

- **which** Sirve para rastrear la ruta absoluta de archivos ejecutables si solo si esta dentro del $Path (variables de entorno). Si es un Alias o una Buiolt-ins no podra darnos lo que queremos.

- **type** Sirve para poder identificar que clase de archivo es si es un builtin, alias u otro.

- **adduser name**: agregar nuevo user 

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
	- 