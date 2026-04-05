# bases_ad

- **Forest**: 



# configuracion_de_red_vm

- La arquitectura de red de la maquina virutal se basa en una configuración de doble interfaz. En la primera se habilita un adaptador en modo NAT (**Network Addreess Translation**) con el proposito de facilitar el accesso a servicios externos y la gestión de actualiazciones criticas del sistema sujeto a los requisitos de conectividad del despliegue. Se configura la segunda interfaz en modo Red Interna para garantizar el aislamiento del tráfico de los servicios de dominio, asegurando que la comunicación entre nodos  se mantenga dentro de un entorno controlado y seguro. En este ultimo para facilitar la conexion del dominio se debe emplear una ip estática.


