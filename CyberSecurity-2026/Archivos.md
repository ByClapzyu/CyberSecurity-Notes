# "Everything is a file"

 **Filosofia** En UNIX/Linux "Todo es un archivo"

Para el Kernel todo son flujos de byte que se pueden leer o escribir.
- **Documentos**: /home/user/notas.txt (archivo normal)
- **Disco duro**: /dev/sda (archivo represanta hardware fisico)
- **Mouse**: /dev/input/mouse0 (archivo que esucupe info cada vez que se mueve la mano)
- **papelera**: /dev/null (archivo magico donde lo que se escibe desaparece).

Lo bueno de esto que es podemos usar las mismas herramientas para todo. Podemos usar un cp (copiar) para duplicar texto, o para hacer un backup de nuestro disco con (cp /dev/sda /dev/sdb)

**Los Permisos**
Al ejecutar un ***ls -l*** podremos ver - rwx r-x r--
Podemos ver que se divide en 4 partes T | UUU | GGG | OOO
	T (Tipo): El primer caracter que podemos observar.
	- **-** : Es archivo normal
	- **d**: Es directorio
	 **UUU** (User/Dueño): Los 3 primero seguidos son del dueño
	 **GGG** (Group):  Los siguientes 3 son de los miembros de grupo
	 **OOO** (Others): Los ultimos 3 cualquier otra persona

Simbolos       file                                                         directorio                                        valor 
- r (Read): Abrir contenido                                       ls dentro                                              4
- w (Write): Modificar o borrar el contenido            crear o borrar archivos dentro            2
- x (Execute): Ejecutar como programa                    entrar en la carpeta                             1

Angulo de Seguridad

- **Error de novato**: SI alguien llega a poner chmod -R 777 carpeta/ . Esto habilita que cualquier persona que pueda entar pueda borrar, modificar o inyectar.
- **El Bit SUID** (Set User ID): a veces se puede ver una "s" en lugar de una "x". Cuando se ejecuta se programa uno se puede convertir temporalmente en el dueño (usualmente root)
# Vulnerabilidad de SUID

El sistema octal de Linux, los permisos en realidad tienen 4 digitos, no 3. El primero se conoce como **permisos especiales**

| **Valor** | **Nombre**              | **Bit**        | **¿Qué hace?**                                             |     |
| --------- | ----------------------- | -------------- | ---------------------------------------------------------- | --- |
| **4**     | **SUID** (Set User ID)  | `s` (en user)  | Ejecuta como el **Dueño** (Root).                          |     |
| **2**     | **SGID** (Set Group ID) | `s` (en group) | Ejecuta como el **Grupo**.                                 |     |
| **1**     | **Sticky Bit**          | `t` (en otros) | "Solo el dueño puede borrar su archivo" (usado en `/tmp`). |     |
1 Entendiendo eso, Primero tenemos que hacer una busqueda de los archivos que tengan el bit especial activdado.
- find / -perm -4000
##aqui se busca el Bit 4 (SUID)