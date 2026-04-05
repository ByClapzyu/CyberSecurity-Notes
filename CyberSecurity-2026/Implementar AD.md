
# vm_conf_red

- La arquitectura de red de la maquina virutal se basa en una configuración de doble interfaz. En la primera se ha habilitado un adaptador en modo NAT (**Network Addreess Translation**) con el proposito de facilitar el accesso a servicios externos y la gestión de actualiazciones criticas del sistema sujeto a los requisitos de conectividad del despliegue. En el segundo se ha habilitado un adaptador en modo Red interna c
    
- **Red Interna (Internal Network):** Es como si compraras un switch físico, lo pusieras en una caja fuerte y solo conectaras tus máquinas virtuales ahí. **¿Para qué sirve?** Para que el tráfico de tu dominio (como cuando un cliente se loguea) no salga a tu red de Wi-Fi real. Es el "perímetro de seguridad" de tu laboratorio.