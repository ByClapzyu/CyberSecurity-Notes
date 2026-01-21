# Useradd

comando: **useradd felix** : Esto crea un nuevo usuario llamado felix.

En la distribución de parrot, al intentar correr el comando $**useradd felix** este me devuelve `bash: useradd: command not found`, para solucionar eso necesitamos usar **sudo**.  Dato importante no se puede repetir usuario ya que si se hace nos arroja `useradd: user 'felix' already exists`.

comando: **tail /etc/passwd**: Para ver el final del archivo 

Se puede apreciar el resultado que es: `felix:x:1003:1003::/home/felix:/bin/sh`. 

comando


Al ser el comando menos practico este no crea una carpeta home, se puede apreciar si hacemos un **ls /home** 




no se puede inicar sesión porque o hay una password y tambien este tiene una shell muy basica.