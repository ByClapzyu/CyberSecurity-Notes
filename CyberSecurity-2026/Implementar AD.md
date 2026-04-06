# bases_ad

 - **Forest:** Es la frontera de seguridad (security boundary) definitiva. Define el **esquema** único y la configuración de configuración para todos los dominios contenidos.
- **Dominio:** Unidad lógica de particionamiento del directorio que facilita la replicación de objetos y la aplicación de Directivas de Grupo (GPO). 
	- "laboratorio.local"
- **Controlador de Dominio (DC):** Servidor crítico encargado de centralizar la gestión de identidades y la seguridad del entorno.
- **DSRM:** Protocolo de acceso de seguridad diseñado para la recuperación del Directorio Activo en escenarios de fallo crítico o corrupción de la base de datos.{}
- **Nombre NetBIOS:** Identificador simplificado del dominio utilizado para asegurar la compatibilidad con sistemas legados y facilitar el inicio de sesión en entornos de red específicos.
	- "pruebas o laboratorio o sucursal"

- **OU** (Unidad Organizativa): es un objeto contenedor dentro de un dominio que permite agrupar cuentas de usuarios, equipos y grupos en una estructura jerárquica. Su función es servir como unidad minima para la vinculación de Objetos de Directiva de Gruppo/GPO y la delegación de autoridad administrativa.

# configuracion_de_red_vm

- La arquitectura de red de la maquina virutal se basa en una configuración de doble interfaz. En la primera se habilita un adaptador en modo NAT (**Network Addreess Translation**) con el proposito de facilitar el accesso a servicios externos y la gestión de actualiazciones criticas del sistema sujeto a los requisitos de conectividad del despliegue. Se configura la segunda interfaz en modo **Red Interna** para garantizar el aislamiento del tráfico de los servicios de dominio, asegurando que la comunicación entre nodos  se mantenga dentro de un entorno controlado y seguro. Para esta interfaz, se requiere la configuración de un direccionamineto estático. Esto asegura la persistencia de los registros SRV en el DNS.


# configuracion_implementacion_ad

### dns
- Una vez que se implementa el AD, procedo a realizar pruebas para checar que el DNS funcione de manera efectiva.
- `nslookup laboratorio.local`
	- *Si el resultado mostrado es el nombre del dominio y su ip correspondiente, significa que todo esta funcionando de forma correcta.*
# nuevo-ou
- Para la creación de una OU se hace por medio de  **`Tools->Active Directory Users and Computers`** 