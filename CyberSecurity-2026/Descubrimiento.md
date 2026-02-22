## Dispositivo Movil

La presencia simultánea de los puertos **8008, 8009, 8443 y 9000** bajo un sistema operativo identificado como **Linux/Android** es un indicador de alta confianza para clasificar el objetivo como un dispositivo de consumo **(Smartphone o Smart TV)**. Estos puertos están asociados a protocolos de descubrimiento y control multimedia que no son típicos en infraestructuras de servidores empresariales
#### TTL (Time To Live)
Para indentificar que el SO se puede hace ping 
TTL = 64 **Linux/Android**
TTL = 128 Windows

Para reconocimiento se usa  **nmap -sV --script nbstat IP**
- **`-sV` (Service Version Detection):** No se limita a ver si el puerto está abierto; intenta determinar qué software y versión exacta están corriendo (como cuando detectó el driver de Chromecast en tu Xiaomi).
    
- **`--script nbstat`:** Es el motor de búsqueda de **NetBIOS**. NetBIOS es un protocolo que los dispositivos (especialmente Windows y Android) usan para "gritar" su nombre en la red local.
    
- **El objetivo:** Su función principal es extraer el **Nombre del Host**, el **Nombre del Grupo de Trabajo** y, lo más importante, la **Dirección MAC** de forma remota.

Resultados posibles:
- **Capa de Aplicación:** Presencia del servicio `castv2` en el puerto **8009**, indicando funciones de Google Chromecast integradas.
    
- **Capa de Enlace (MAC):** El OUI pertenece a _China Dragon Technology_, proveedor habitual de hardware para Xiaomi.
    
- **Capa de Transporte:** El uso sistemático de SSL/TLS en puertos de control (8009, 8443, 9000) es consistente con las políticas de seguridad de Android 9 para servicios de ecosistema.
-----
## Smart Home

El puerto **10001** es muy común en dispositivos de casa inteligente de Google para configuración inicial.

Lista de puertos clave:
- 8008
- 8009
- 10001