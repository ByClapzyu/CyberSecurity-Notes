
# Usuarios

Vamos a verlo de una manera muy informal para poder entender la diferencia de un usuario normal y el usuario root:
- **User**: Este es un usuario normal simple y corriente en el cual puede desarollar las tareas normales que no necesiten de permismos elevados.
- **Root**: Es aquel que literal puede hacer cualquier cosa en el sistema tiene el poder absoluto y puede destruir el sistema de forma intecional o no.

Nosotros podemos añadir un usuario con el comando **adduser name** pero si lo intentamos nos dira que solo el root puede agregar un usuario o grupo al sistema. En esos caso se tiene que usar el comando **sudo** antes del comando para poder hacer que funcione.
![[adduser.png]]

# sudo

El significado de sudo es el acronimo de **Super User Do** el cual nos da el superpoder de forma temporal para realizar cualquier accion en el sistema. Estos poderes son prestados el super usuario root el cual como se ha mencionado antes este puede hacer cualquier cosa así como borrar todo el sistema.

Hay un archivo en el cual podemos ver a todos los usuarios que hay en el sistema tanto personas como de servicios, ese archivo se llama /etc/**passwd**
![[passwd.png]]