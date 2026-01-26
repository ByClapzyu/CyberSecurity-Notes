
# Módulo: Redes Inalámbricas (Wi-Fi)

##  Definición y Fundamentos

**Estándar:** La tecnología Wi-Fi se basa en el conjunto de estándares **IEEE 802.11**. Es la tecnología empleada para la creación de redes de área local inalámbricas (WLAN).

**Relación con Ethernet y Modelo OSI:** Aunque el medio de transmisión cambia (aire vs. cable), Wi-Fi comparte protocolos fundamentales con Ethernet. Es crucial entender dónde opera en el modelo OSI:

- **Capa 1 (Física) y Capa 2 (Enlace de Datos):** Aquí es donde 802.11 y Ethernet son diferentes (ondas de radio vs. señales eléctricas).
    
- **Capa 3 (Red):** Ambas utilizan **IP** (Internet Protocol) para el direccionamiento.
    
- **Capa 4 (Transporte):** Ambas utilizan **TCP** y **UDP** para la transmisión de datos.
    

**Arquitectura de Conexión:**

- **Red Local (LAN):** Los dispositivos (laptops, celulares) se conectan al enrutador de forma inalámbrica.
    
- **La Puerta de Enlace (Gateway):** El enrutador inalámbrico actúa como puente.
    
- **Red de Área Amplia (WAN):** Hacia "afuera" (Internet), el enrutador se conecta físicamente a través de tecnologías cableadas como DSL o fibra óptica.
    

##  Comparativa: Redes Inalámbricas vs. Cableadas

|**Característica**|**Red Cableada (Ethernet)**|**Red Inalámbrica (Wi-Fi)**|
|---|---|---|
|**Medio de Transmisión**|Cables de cobre trenzado o fibra óptica.|Ondas de radio o microondas.|
|**Ventaja Principal**|Estabilidad y velocidad.|**Movilidad** (Conexión desde cualquier punto).|
|**Desventaja Principal**|Falta de movilidad (físicamente atado).|**Seguridad** (Las ondas viajan por el aire y cualquiera con una antena puede interceptarlas si no están cifradas).|

## Evolución de la Seguridad Wi-Fi

Debido a que el medio es abierto (aire), el cifrado es obligatorio.

### A. Estándares Antiguos

- **WEP (Wired Equivalent Privacy):** El primer intento de seguridad. Hoy se considera obsoleto y muy inseguro.
    

### B. WPA (Wi-Fi Protected Access) v1 y v2

Son los estándares que corrigieron las fallas de WEP.

- **Algoritmo AES (Advanced Encryption Standard):**
    
    - Es un estándar de cifrado simétrico por bloques utilizado mundialmente por gobiernos y bancos.
        
    - Reemplazó al algoritmo RC4 (usado en WEP/WPA1). AES es mucho más robusto y difícil de romper.
        
- **Niveles de Seguridad:**
    
    - **Personal (WPA-Personal):** Utiliza una **Pre-Shared Key (PSK)**, es decir, una contraseña única compartida por todos los usuarios (típico en casas).
        
    - **Empresarial (WPA-Enterprise):** Utiliza el estándar **IEEE 802.1X**.
        

> **Nota sobre IEEE 802.1X:** Es un mecanismo de control de acceso a redes basado en puertos. En lugar de una sola contraseña para todos, cada usuario tiene sus propias credenciales (Usuario/Contraseña o Certificado). Requiere un servidor de autenticación (generalmente RADIUS) que valida al usuario antes de permitirle entrar a la red.

### C. WPA3 (El Estándar Actual)

La versión más reciente y segura.

- Ofrece un establecimiento de comunicación más seguro (protección contra ataques de fuerza bruta al handshake).
    
- Mayor facilidad para añadir dispositivos IoT sin pantalla (Easy Connect).
    
- Aumento del tamaño de la clave criptográfica (hasta 192 bits en modo Enterprise).
    

##  Riesgos y Amenazas Comunes

**Ingeniería Social y Redes Públicas:**

- **Honeypot (Tarro de Miel):** Redes abiertas configuradas por atacantes para atraer víctimas y robar sus datos.
    

**Ataques de Identidad (SSID):**

- **SSID No Autorizado (Rogue AP):** Un punto de acceso instalado sin permiso en la red corporativa.
    
- **Evil Twin (Gemelo Malvado):**
    
    - El atacante configura un AP falso con el **mismo nombre (SSID)** que una red legítima y conocida.
        
    - Los dispositivos de las víctimas se conectan automáticamente creyendo que es su red de confianza.
        
    - Es un tipo de ataque **Man-in-the-Middle (MitM)**, permitiendo al atacante interceptar todo el tráfico.
        

**Recomendación:** No confiar en SSIDs abiertos. Usar siempre VPN si se conecta a redes públicas.

##  Mejores Prácticas de Configuración

Para asegurar una red inalámbrica, se deben seguir estos pasos:

1. **Gestión Básica:** Cambiar el nombre de red (SSID) y la contraseña predeterminada de fábrica inmediatamente.
    
2. **Contraseñas:** Elegir una frase de contraseña compleja y larga.
    
3. **Cifrado:** Activar WPA2 o WPA3 (nunca dejar la red abierta o en WEP).
    
4. **Mantenimiento:** Actualizar el firmware del enrutador periódicamente para parchar vulnerabilidades.
    

**Características Avanzadas de Defensa:**

- **Detección y supresión de AP no autorizados (Rogue AP Detection):** El sistema escanea el aire buscando señales extrañas y puede bloquearlas.
    
- **Autenticación Robusta:** Usar 802.1X en entornos corporativos.
    
- **Segmentación:** Crear una red de invitados (Guest Network) separada de la red principal para que las visitas no tengan acceso a los servidores o impresoras internas.
    
- **Listas de Control de Acceso (ACL):** Filtrar qué direcciones MAC pueden conectarse.
    
- **Monitoreo de Red:** Supervisar el tráfico para detectar anomalías.

