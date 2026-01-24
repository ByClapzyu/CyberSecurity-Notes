## Tipos

#### Filtrado de paquetes/ firewall sin estado

primera generacion: examina los protocolo de transporte y rutamiento: origen y destiino de direcciones de red, protocolos y nuemero de puerto.
- Las politicas de firewall usan eso para ver que paquetes se aprueva, la s reglascoincidencia potencial se hace de arria a abajo.
- la ultima politca puede ser:
	- implicita: negado de forma predeterminada
	- explicita:haciedo accion configurada aprobando o denegando el paquete.
	- aprueba el paquete si el orgien, protoculo coinciden con la politca del firewall, si no es asi se decarta o se bloquea silenciosamente.

Desventajas: necesita conf adicional para proteccion, por jeemplo politca de firewall adicional para el trafico de retorno de una sesion
- no administra protoclos
- enfoque unviersal


###  Firewall de estado / 2 generacion

Esta diseñado para observar las conexiones de red a lo largo del tiempo mediante seguimiento de la comprobacion de 5 - tuplas (direccion ip origen, numero puerto, direccion ip destino, numero puerto y el protocolo en uso caracteriza y permite el seguimiento de una conexion (TCP/IP)) y el estado de conexion, examina continuamente el trafico que va y viene entre los enpoints. Si el firewall ve que la direccion de retorno no cioncide, el firewall bloque la conexion. Cualquier parauqe no no pertenezca a la conversacón o coincida con la politica se descarta.

Desventaja: No bloquea paquetes no autorizado sis usan un protocolo aceptable como HTTP. 

HTTP USOS : Contenido de texto estatico, comercio electronico, alojamiento de archivo y app webs. Al usar el mimso pueto el firewall no pued edistinguir entre aprobadas o maliciososas.

### Firewall de tercera generación

carga util de datos ,implementa el filtrado de capa de aplicacion pueden comprender protocolos como:, 
- http
- ftp
- dns

tambien protecciones combinadas como: antivirus, filtrado de correo electronico no deseado IPS VPN



Estado mas reciende del firewall : los ataques pueden venir de usuarios de confianza, dispostivo y apps


### - Next-generation firewall (NGFW)
Un firewall debe evitar los ciberatauqes en evolución en todos los extremos de la red, al mismo tiepo ofrecer seguridad, confiabildad y rendimiento de la red.

como FortiGate proporciona estas funcionalidades de seguridad avanzadas

Primera linea de defensa: revisa sus maletas para detectar si lleva algun objeto maliciso
segunda linea de defensa: haca una inspeccion profunda de paquete (DPI)
tercera linea de defensa: 