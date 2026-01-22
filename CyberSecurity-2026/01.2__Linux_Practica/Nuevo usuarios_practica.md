# Useradd

- comando: **useradd felix** : Esto crea un nuevo usuario llamado felix.
    - **user add -m -s uname** : Crea usuario con carpeta home y shell moderna

    En la distribución de parrot, al intentar correr el comando $**useradd felix** este me devuelve `bash: useradd: command not found`, para solucionar eso necesitamos usar **sudo** porque esta herramienta vive en `/usr/sbin`, una zona exclusiva de root.
    
    Dato importante no se puede repetir usuario ya que si se hace nos arroja `useradd: user 'felix' already exists`.

- comando: **tail /etc/passwd**: Para ver el final del archivo 

    Se puede apreciar el resultado que es: `felix:x:1003:1003::/home/felix:/bin/sh`. Aunque `/etc/passwd` diga que mi home es `/home/felix`, si no usé `-m`, esa carpeta **no existe físicamente** y dará error al entrar. Tambien la shell establecida es basica lo ideal es usar la bandera **-s** para definir una shell moderna.

- comando: **sudo userdel -r felix**: Elimina el usuario y todo lo que le pertenece. 

    Al ser el comando menos practico este no crea una carpeta home, se puede apreciar si hacemos un **ls /home**. Para fines practico es mejor borrar y volver a crear usando la bandera -m.

- comando: **su - uname**: Para hacer login con el nuevo usuario

    Si intentamos hacer login con el usuario nuevo nos dira que introduzcamos la contraseña, pero nosotro no sabemos cual es ya que no se ha establecido y nos aparecera`su: Authentication failure`.

- comando: **sudo passwd uname**: Para establecer contraseña al usuario

    Con esto ya se puede hacer login con **su - uname** , para salirnos es **exit**. Para ver que se reflejo bien podemos hacer uso de **sudo tail /etc/shadow** y ahi veremos el hash de nuestra contraseña.

### Dando y Quitando Poder!!

- comando: `sudo tail /etc/shadow` : Corriendo el comando en el usuario `felix`

	Al no tener permiso sudo en le nuevo usuario creado nos arroja dos alertas: 1) `felix is not in the sudoers file`, 2) `This incident has been reported to the administrator.
	
	**Solución**: Desde el usuario admin debemos de agregar al usuario invitado (`felix`), la grupo sudo con el comando: **sudo usermod -aG sudo felix**
	
`