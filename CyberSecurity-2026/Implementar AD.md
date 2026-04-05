# bases_ad

 - **Forest:** Es la frontera de seguridad (security boundary) definitiva. Define el **esquema** único y la configuración de configuración para todos los dominios contenidos.
- **Dominio:** Unidad lógica de particionamiento del directorio que facilita la replicación de objetos y la aplicación de Directivas de Grupo (GPO)..
- **Controlador de Dominio (DC):** Servidor crítico encargado de centralizar la gestión de identidades y la seguridad del entorno.




# configuracion_de_red_vm

- La arquitectura de red de la maquina virutal se basa en una configuración de doble interfaz. En la primera se habilita un adaptador en modo NAT (**Network Addreess Translation**) con el proposito de facilitar el accesso a servicios externos y la gestión de actualiazciones criticas del sistema sujeto a los requisitos de conectividad del despliegue. Se configura la segunda interfaz en modo **Red Interna** para garantizar el aislamiento del tráfico de los servicios de dominio, asegurando que la comunicación entre nodos  se mantenga dentro de un entorno controlado y seguro. Para esta interfaz, se requiere la configuración de un direccionamineto estático. Esto asegura la persistencia de los registros SRV en el DNS.


