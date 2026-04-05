# bases_ad

- **Forest**: Configuración globa, donde se establecen las reglas. Ademas, es el maximo limite maximo de seguridad, controla todo.
- **Dominio**: Donde se establacen los datos de la infrestructura. Cada dominio tiene su grupo de datos.
- **DC (Controlador de Dominio)**: Servidor donde se guarda la informacion.



# configuracion_de_red_vm

- La arquitectura de red de la maquina virutal se basa en una configuración de doble interfaz. En la primera se habilita un adaptador en modo NAT (**Network Addreess Translation**) con el proposito de facilitar el accesso a servicios externos y la gestión de actualiazciones criticas del sistema sujeto a los requisitos de conectividad del despliegue. Se configura la segunda interfaz en modo Red Interna para garantizar el aislamiento del tráfico de los servicios de dominio, asegurando que la comunicación entre nodos  se mantenga dentro de un entorno controlado y seguro. Para esta interfaz, se requiere la configuración de un direccionamineto estático. Esto asegura la persistencia de los registros SRV en el DNS.


