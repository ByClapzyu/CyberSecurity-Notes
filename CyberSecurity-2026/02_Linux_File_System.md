La filosofia de Linux es **"Everything in Linux is  File"**

Hay muchos tipos de files estan los:
- **/bin**: Que son lo binarios (código maquina). Estos son **programas ejecutables** que en Windows son los .exe.
	- /bin: Donde están los comando fundamentales para el sistema (ls, cat , bash).
	- /sbin: Son los binarios del sisteama, la s es de **system** o **superuser**. Son mas herramientas de administración y mantenimiento (reboot, ifconfig, ip).
- **/boot**: Contiene los archivos estáticos necesarios para el boot loader (gerstor de arranque) aqui esta el kernel de linux **vmlinuz** y la imagen **initrd** (disco ram inicial), asi como archivos de configuracion de GRUB.
-
- **/var/log**: Es donde se **guardan los registros** de todo lo que pasa como errores, acceso yadvertencias.

- **/temp**: Se encuentran **archivos temporales** requeridos por programsa en ejecución. Cuando se reinicia el SO los  files temporales desaparecen ya que es volatil. En esta carpeta **cualquier user puede escribir sin permisos** , pero no puede borrar los archivos de lo de mas (por el Sticky Bit)

- **/lib**: Contiene **librerias copartidas** esenciales que necesitan los binarios que están en /bin y /sbin. Tambien contine

- **dev**:

- **etc**

- **var**

