# bases_ad

 - **Forest:** Es la frontera de seguridad (security boundary) definitiva. Define el **esquema** único y la configuración de configuración para todos los dominios contenidos.
- **Dominio:** Unidad lógica de particionamiento del directorio que facilita la replicación de objetos y la aplicación de Directivas de Grupo (GPO). 
	- "laboratorio.local"
- **Controlador de Dominio (DC):** Servidor crítico encargado de centralizar la gestión de identidades y la seguridad del entorno.
- **DSRM (Directory Services Restore Mode)**: Es la llave de emergencia.Si la base de datos de AD se corrompe y el servidor no arranca, usas esta clave para entrar en un modo de reparación y tratar de salvar los datos.
- **NetBIOS Name**: Nombre que vincula a un usuario con el dominio. `/` que se visualiza cuando uno se loguea 
	- "pruebas o laboratorio o sucursal"

- **OU** (Unidad Organizativa): es un objeto contenedor dentro de un dominio que permi


# configuracion_de_red_vm

- La arquitectura de red de la maquina virutal se basa en una configuración de doble interfaz. En la primera se habilita un adaptador en modo NAT (**Network Addreess Translation**) con el proposito de facilitar el accesso a servicios externos y la gestión de actualiazciones criticas del sistema sujeto a los requisitos de conectividad del despliegue. Se configura la segunda interfaz en modo **Red Interna** para garantizar el aislamiento del tráfico de los servicios de dominio, asegurando que la comunicación entre nodos  se mantenga dentro de un entorno controlado y seguro. Para esta interfaz, se requiere la configuración de un direccionamineto estático. Esto asegura la persistencia de los registros SRV en el DNS.


