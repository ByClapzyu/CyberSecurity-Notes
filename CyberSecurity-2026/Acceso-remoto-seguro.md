
### **¿Qué es el acceso remoto seguro?**

- **Definición:** El acceso remoto seguro es una combinación de métodos y tecnologías de seguridad que permiten a entidades finales externas conectarse a las redes sin comprometer los activos digitales ni exponer las redes a partes no autorizadas.
    
- **Lugares de teletrabajo:** Casa, hotel, cafetería, sucursal, campus, aeropuerto, estación de tren, etc.
    
- **Contexto:**
    
    - Aumento del teletrabajo.
        
    - Los actores maliciosos aprovechan el acceso remoto no seguro.
        
    - Los métodos para salvaguardar las conexiones remotas se han vuelto más seguros a través del tiempo.
        

---

### **Protección del acceso remoto: Funciones Clave**

1. **Privacidad de datos:** Un estado en el que la información se oculta al público y solo está disponible para personas selectas.
    
2. **Integridad de datos:** La exactitud y coherencia de los datos a lo largo de su ciclo de vida.
    
3. **Autenticación:** Proceso de verificación de la identidad de una persona o cosa.
    
4. **Autorización:** La función de especificar los derechos de acceso a los recursos.
    
5. **Registro (Accounting):** El registro y seguimiento de las actividades de los agentes en una red informática.
    

- **Nota:** Las tres últimas funciones se expresan comúnmente como **AAA** (Authentication, Authorization, Accounting).
    

---

### **Métodos comunes de acceso seguro**

- **VPN IPsec:** Red privada virtual de seguridad del protocolo de Internet.
    
- **VPN SSL:** Red privada virtual de capa de conexión segura.
    
- **ZTNA:** Acceso a la red de confianza cero (que incorpora el principio de confianza cero).
    

---

### **Comparación: ZTNA vs VPN**

**VPN de acceso remoto seguro:**

- **Casos de uso:** Acceso remoto seguro, Sitio a sitio.
    
- **Componentes principales:** Cliente, Servidor, Protocolos.
    

**Acceso a la red de confianza cero (ZTNA):**

- **Características:** Principio de confianza cero, Seguridad mejorada.
    

---

### **Tabla Comparativa Detallada: IPsec VPN vs SSL VPN vs ZTNA**

|**Característica**|**IPsec VPN**|**SSL VPN**|**ZTNA**|
|---|---|---|---|
|**Nivel del modelo OSI que protege**|Red|Transporte a la aplicación|Transporte a la aplicación|
|**Implementación en el cliente**|Aplicación de cliente de VPN|Navegador web o una aplicación de cliente de la SSL VPN|Cliente de ZTNA|
|**Control de acceso tras la sesión**|No hay ningún control de acceso después de que el usuario establece una sesión de VPN|Cierto control de acceso granular (conecta a usuarios a aplicaciones/servicios específicos)|Control de acceso granular a aplicaciones específicas. Se basa en funciones de usuario, políticas y verificaciones continuas|
|**Autenticación**|Entre la aplicación de cliente de la VPN y la red privada|Mediante solicitud de inicio de sesión del navegador tras establecer sesión SSL|Usuario y dispositivo se autentican y verifican cada vez que se solicita acceso a una aplicación|
|**Tipo de túnel**|Solo túnel IPsec|Se basa en la sesión o túnel|Se basa únicamente en la sesión|
|**Categoría**|Estándar de la industria|Específica del proveedor|Específica del proveedor|
|**Configuración**|Requiere instalación. Flexible (malla/estrella). Para clientes o puertas de enlace pares.|No requiere instalación (si es tipo web). Configuración más simple (solo cliente a FortiGate, sin ajustes de usuario).|Requiere instalación de cliente ZTNA. Configuración más simple (solo cliente a FortiGate, sin ajustes de usuario).|


---

# VPN SSL

Definición:  Tecnologia que admite una sesion cifrada entre dos dispositivos informaticos, **proporciona seguridad desde la capa de transporte** del modelo OSI al mismo tiempo **comunica datos en la capa de app**. Mientras que la **info se intercabia en la capa de app** entre el cliente y el servidor, la **info se encapsula en la capa de transporte** 

Requiere un cliente y un servidor, donde el clinete suele ser un servidor web, esta provve **privacidad, integridad, autenticacion y antirepeticion(evita manipulacion)**.

### ipos de VPN SSL

**1. Portal SSL o VPN web**

- Es una sesión segura establecida directamente entre un navegador web y un servidor.
    
- **Ventaja:** Proporciona un acceso rápido y fácil a los recursos de la red.
    

**2. VPN de túnel SSL**

- Es una sesión segura entre un cliente SSL VPN (software instalado) y un servidor.
    
- **Ventaja:** Permite enviar todo el tráfico a través del túnel, otorgando acceso a más recursos de la red (no solo web).
    

### Conexión mediante el Portal VPN SSL (Modo web)

El proceso de conexión sigue estos pasos:

1. Los usuarios se conectan a través del navegador web.
    
2. Los usuarios proporcionan credenciales para autenticarse.
    
3. El servidor muestra el portal SSL VPN.
    

### Servidor web SSL VPN

- Las funciones de servicios web, VPN segura y seguridad de firewall pueden estar en servidores dedicados o unificados en uno solo.
    
- **Modelo Fortinet (FortiGate):** El dispositivo funciona simultáneamente como:
    
    - Servidor web frontend.
        
    - Servidor SSL VPN.
        
    - Firewall.
        
- Funciona como una puerta de enlace segura para el tráfico HTTPS y como un **proxy inverso**, reenviando las solicitudes desde los usuarios (endpoints) hacia los servidores web u otros servicios en el backend.
    

### Limitaciones de VPN SSL

- **Navegador exclusivo:** Las aplicaciones de red externas que se ejecutan en el dispositivo del usuario (fuera del navegador) no pueden enviar datos a través de la VPN.
    
- **Número limitado de protocolos:** El modo web restringe los recursos de la red a los que el usuario puede acceder.

## Conexion mediante modo de tunel SSL vpn

1 Los usuarios se conectan a la puerta de enalce SSL vpn
2 Autenticacion de usuariso
3 el cliente crea un tunel
4 los usuarios acceden a los recuross

-----

# VPN IPsec

### ¿Qué es una IPsec VPN?

- Es la tecnología que garantiza la privacidad y la integridad de los datos entre dos o más dispositivos informáticos.
    
- Proporciona seguridad en la capa de red del modelo OSI.
    

**Protocolos de seguridad:** La configuración determina cómo se protegen los paquetes mediante dos protocolos principales:

- **AH (Encabezado de autenticación):** Garantiza la integridad de los datos, la autenticidad del origen y la protección frente a ataques de repetición.
    
- **ESP (Seguridad encapsulada de carga útil):** Garantiza la privacidad de los datos de un punto a otro.
    

### Conexión de usuarios

1. El usuario inicia una conexión con el servidor VPN.
    
2. Inicia sesión en la aplicación de cliente de la VPN desde su dispositivo.
    
3. Generalmente se autentica con una contraseña, aunque existen otros medios de autenticación.
    

### Funcionamiento: Paso 1 (Intercambio de clave)

**A. Asociación de seguridad (SA)** Implica un acuerdo sobre los atributos de seguridad entre el cliente y el servidor. Los atributos que se acuerdan incluyen:

1. **Algoritmos criptográficos:**
    
    - Simétricos (ej. AES - Estándar de cifrado avanzado).
        
    - Asimétricos (ej. RSA).
        
    - Funciones Hash (ej. SHA - Algoritmo de hash seguro).
        
    - _Nota:_ Estos protocolos admiten cifrado, autenticación e integridad de los datos respectivamente.
        
2. **Modo IPsec:**
    
    - Existen dos modos disponibles: **Túnel** y **Transporte**.
        
    - **Diferencia clave:** El modo túnel cifra la carga útil _y_ el encabezado del paquete, mientras que el modo transporte _solo_ cifra la carga útil.
        
3. **Parámetros de red:**
    
    - Indican si se utilizará AH, ESP o ambos.
        
    - **AH:** Usa una función hash para integridad, garantiza el origen y usa números de secuencia para evitar ataques de repetición.
        
    - **ESP:** Protege la privacidad, enfocándose en la carga útil (la información real que se transmite, excluyendo los datos usados solo para la transmisión como las direcciones IP).
        

**B. Autenticación mutua**

**C. Clave de sesión compartida**

- Se establece mediante el Intercambio de clave por Internet (IKE).

