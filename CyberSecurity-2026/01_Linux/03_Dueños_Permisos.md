
# Usuarios

Vamos a verlo de una manera muy informal para poder entender la diferencia de un usuario normal y el usuario root:
- **User**: Este es un usuario normal simple y corriente en el cual puede desarollar las tareas normales que no necesiten de permismos elevados.
- **Root**: Es aquel que literal puede hacer cualquier cosa en el sistema tiene el poder absoluto y puede destruir el sistema de forma intecional o no. Es importante recorda que el **UID 0** le pertenece a root.

# Comando agregar usuarios

- **adduser**: Este es un comando que podemos verlo como el **mas util, interactivo e intuitivo**, ya que al ejecutarlo el sistema nos guia a traves de una serie de preguntas para configurar el usuario, nos pide establecer contraseña, informacion adicional, crea el directorio personal y asignal la shell predeterminada

- **useradd**:  Es mas un comando simple que no es interactivo, solo **crea la cuenta de forma basica y termina**, no establece contraseña, ni directorio y asigna una shell mas basica como /bin/sh
	- **useradd -m uname** Hace que el usuario tenga carpeta home

Nosotros podemos añadir un usuario con el comando **adduser name** pero si lo intentamos nos dira que solo el root puede agregar un usuario o grupo al sistema. En esos caso se tiene que usar el comando **sudo** antes del comando para poder hacer que funcione.
![[adduser.png]]

# sudo

El significado de sudo es el acronimo de **Super User Do** el cual nos da el superpoder de forma temporal para realizar cualquier accion en el sistema. Estos poderes son prestados el super usuario root el cual como se ha mencionado antes este puede hacer cualquier cosa así como borrar todo el sistema.

Hay un archivo en el cual podemos **ver a todos los usuarios que hay** en el sistema tanto personas como de servicios, ese archivo se llama **/etc/passwd**
![[passwd.png]]
- **x** = password --> /etc/shadow : Cuando se puede apreciar una X depues del nombre indica que la **contraseña** se encuentra en **/etc/shadow**
- **100X: 100X**  : Esto suele indicar el primer numero es el **User Id (UID)** y el segundo el **Group ID (GID)**
- **name , , ,**: Nombre del usuario y datos adicionales
- **/home/name**: el Home directory del user
- **/bin/bash; La shell** establecida para el usuario

# Carpetas importantes

- **/etc/passwd**: Esta carpeta es vital ya que aqui se **encuentra los usuarios** y cualquier puede acceder a ella.

- **/etc/shadow**: Esta carpeta es super importante ya que aquí se pueden encontrar las **contraseñas (son los hashes de las contraseñas)** solo el root puede acceder a ella

- **/etc/group**:  Aqui se encuentra los **grupos que hay** esta esta dividida en 4 columnas donde la ultima son **los integrantes**.

-