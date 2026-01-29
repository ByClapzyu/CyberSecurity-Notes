# Bandit 0
##altgr + }
Para poder comenzar con bandit0, necesitamos acceder a traves de **SSH** usando el siguiente comando: 
- ssh bandit0@bandit.labs.overthewire.org -p 2220

En bandit 0, las instrucciones de la página de OTW nos indican que la contraseña para el siguiente nivel se encuentra almacenada en un archivo específico dentro del directorio _home_:

- File name: **readme**
    
- Location: **Home directory**
    
Para solucionar esto, aplicamos una metodología de reconocimiento antes de leer el archivo. Primero nos orientamos con **pwd** para confirmar que estamos en `/home/bandit0` y listamos el contenido con **ls**.

Antes de imprimir el contenido, realizamos dos verificaciones de seguridad y tipo:

- **file**: Nos confirma que es "ASCII text", asegurando que es legible por humanos.
    
- **du -b**: Nos indica que pesa 438 bytes, confirmando que es un archivo ligero y no saturará la terminal.
    
Una vez verificado, procedemos a leerlo.
Comando final: **cat readme**
Password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

# Bandit 1

En bandit 1 las instrucciones son similares al anterior, pero el archivo tiene una peculiaridad en su nombre:
- filename is **-** (dash)
    
Si intentamos hacer un `cat -`, el comando interpretará el guion como una instrucción para esperar entrada estándar (stdin) y no sucederá nada. Para solucionar esto tenemos dos opciones: usar la ruta relativa o el terminador de opciones `--`.

- **./-** especifica que el archivo está en el directorio actual.
    
- **du -b** nos confirma que el archivo pesa 44 bytes.
    
Comando final: **cat ./-**
Password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
# Bandit 2

En bandit 2 el archivo se encuentra en el directorio actual pero tiene una característica que puede confundir a la shell:

- filename contains **spaces**
    
La terminal usa el espacio como separador de argumentos. Para solucionar esto, debemos "escapar" los espacios o agrupar el nombre completo para que sea tratado como una sola cadena.

- **" "** (comillas dobles) le indican a la shell que todo lo que está dentro es un único argumento.
    
Comando final: **cat "spaces in this filename"**

Password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
# Bandit 3 

En bandit 3 nos indica que el archivo está dentro de la carpeta `inhere/`, pero al entrar no es visible con un listado normal.

- file is **hidden**
    
Para solucionar esto, primero accedemos al directorio (`cd inhere/`). Consultando el manual de `ls`, vemos que los archivos que inician con un punto (.) están ocultos por defecto.

- **-a** (all) es la bandera de `ls` que fuerza a mostrar todas las entradas, incluyendo las ocultas.
    
Una vez visible el archivo `...Hiding-From-You`, procedemos a leerlo.
Comando final: **ls -a** y luego **cat ...Hiding-From-You**

Password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

# Bandit 4

En bandit 4 el archivo está en el directorio `inhere/`, donde hay múltiples archivos llamados `-file00`, `-file01`, etc. La única pista es el tipo de contenido:

- **human-readable** (ASCII text)
    
No es eficiente leer uno por uno. Para solucionar esto usaremos el comando **file**, que determina el tipo de archivo basándose en su contenido (magic numbers) y no en su extensión.

- ***** (wildcard) nos permite aplicar el comando a todos los archivos que coincidan con el patrón (ej. `-file0*`).
    
El comando nos mostrará una lista; buscaremos el que diga "ASCII text".
Comando final: **file ./-file0"*"**

password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

# Bandit 5 

En bandit 5 nos dice que el file se encuentra abajo de la carpeta inhere/ nos dice que en algun lugar y nos da 3 especificaciones: 
- 
    human-readable
    1033 bytes in size
    not executable
Para solucionar esto usaremos el comando **find**. Consultando el manual (man find), una vez que se identifica las opciones/banderas clave en este caso:
- **-type f** para buscar solo archivos
- **-size** para filtrar el tamaño
Para poder buscar el tamaño como indica en el manual se debe usar el sufijo c (character) en el tamaño de byte deseado en este caso es (1033c) ya que si se usa b byte estariamos haciendo referencia a 512 bytes. Al final de comando vamos a redireccionar las salida de los errores a la papelera para ocultarlos **2>/dev/null**. Si ejecutamos el comando nos saldra solo un resultado que es la ruta **./bandit5/inhere/maybehere07/.file2**

comando final: **find . -type f -size 1033c**

Password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

# Bandit 6

En bandit 6 el archivo esta en algun lugar del server y nos dan 3 pistas:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
Dato que debemos tener encuenta que el dueño es el bandit 7, pero el grupo si es de bandit 6. Para solucionar esto usaremos el comando find. Consultando el manual (man find), debemos identificar  las nuevas banderas clave  en este caso son:

- **-user** uname buscamos por user
- **-group** gname buscamos por grupo
Entonces el comando final que con la bandera anterior de `-size` y con las nuvas.

comando final: **find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null**

Password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

# Bandit 7

En este bandit 7 nos dicen que el archivo es data.txt y la flag esta despues de la palabra millionth. Para este caso usaremos **grep** para buscar la palabra `millionth` dentro del archivo.

Comando final: **grep millionth data.txt**

Password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

# Bandit 8

En este bandit 8 tambien la flag esta guardada en el file data.txt y nos dice que es la unica que no se repite. Para esto se usara `sort` para dar orden y `uniq` para filtrar, con la bandera `-u` para filtrar los que se repiten solo una vez. 

comando final : **sort data.txt | uniq -u**

*dato importante*
Siempre que se use **uniq** se necesita usar **sort** ya que solo nos elimina las repeticiones seguidas.

password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

# Bandit 9 

La contraseña está escondida dentro de `data.txt`, pero este es un **archivo binario**.

- _Problema:_ Si usamos `cat`, la terminal se llena de símbolos raros ("ruido") y puede bloquearse, ya que interpreta bytes de control como instruccione
- Solución: filtrar  el ruido con  `strings`


password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey