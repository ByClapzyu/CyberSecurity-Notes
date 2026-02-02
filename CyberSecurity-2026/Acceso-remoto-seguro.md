
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

## vpn-ssl-definición-y-conceptos

**Definición:** Tecnología que admite una sesión cifrada entre dos dispositivos informáticos.

- Requiere un cliente y un servidor (donde el cliente suele ser un navegador web).
    
- Provee: Privacidad, Integridad, Autenticación y Antirepetición (evita manipulación).
    

**Funcionamiento en el Modelo OSI:**

- Proporciona seguridad desde la **capa de transporte**.
    
- Comunica datos en la **capa de aplicación**.
    
- _Resumen:_ Mientras que la info se intercambia en la capa de app entre el cliente y el servidor, la info se encapsula en la capa de transporte.
    

---

## tipos-de-vpn-ssl

### 1. Portal SSL o VPN Web (Clientless)

- Es una sesión segura establecida directamente entre un navegador web y un servidor.
    
- **Ventaja:** Proporciona un acceso rápido y fácil a los recursos de la red sin instalar nada.
    
- **Limitaciones:**
    
    - **Navegador exclusivo:** Las aplicaciones externas al navegador no pueden enviar datos por la VPN.
        
    - **Número limitado de protocolos:** Restringe los recursos a los que se puede acceder (generalmente solo HTTP/HTTPS/FTP).
        

**Proceso de conexión (Modo Web):**

1. Los usuarios se conectan a través del navegador web.
    
2. Proporcionan credenciales para autenticarse.
    
3. El servidor muestra el portal SSL VPN.
    

### 2. VPN de Túnel SSL (Tunnel Mode)

- Es una sesión segura entre un **cliente SSL VPN** (software instalado como FortiClient) y un servidor.
    
- **Ventaja:** Permite enviar **todo el tráfico** a través del túnel, otorgando acceso a más recursos de la red (no solo web).
    

**Proceso de conexión (Modo Túnel):**

1. Los usuarios se conectan a la puerta de enlace SSL VPN mediante el software.
    
2. Autenticación de usuarios.
    
3. El cliente crea un túnel virtual en el adaptador de red.
    
4. Los usuarios acceden a los recursos como si estuvieran en la red local.
    

---

## arquitectura-del-servidor-ssl-vpn

Las funciones de servicios web, VPN y firewall pueden estar en servidores dedicados o unificados.

**Modelo Fortinet (FortiGate):** El dispositivo funciona simultáneamente como:

- Servidor web frontend.
    
- Servidor SSL VPN.
    
- Firewall.
    

**Función de Proxy Inverso:** El FortiGate actúa como una puerta de enlace segura para el tráfico HTTPS y como un **proxy inverso**, reenviando las solicitudes desde los usuarios (endpoints) hacia los servidores web u otros servicios en el backend (servidores internos).

---

## vpn-ipsec-definición-y-protocolos

**Definición:** Tecnología que garantiza la privacidad y la integridad de los datos entre dos o más dispositivos.

- Proporciona seguridad en la **Capa de Red** (Capa 3) del modelo OSI.
    

**Conexión de Usuarios (General):**

1. El usuario inicia conexión con el servidor VPN.
    
2. Inicia sesión en la aplicación cliente VPN (requiere software).
    
3. Se autentica (generalmente contraseña, token, etc.).
    

### Protocolos de Seguridad (AH y ESP)

La configuración determina cómo se protegen los paquetes:

**1. AH (Encabezado de Autenticación):**

- Garantiza la **integridad** de los datos (vía hash).
    
- Garantiza la **autenticidad del origen**.
    
- Protección frente a ataques de repetición (usando números de secuencia).
    
- _Nota:_ No cifra los datos (no hay privacidad), solo firma.
    

**2. ESP (Seguridad Encapsulada de Carga Útil):**

- Garantiza la **privacidad** (cifrado) de los datos de un punto a otro.
    
- Protege específicamente la carga útil.
    

---

## funcionamiento-de-ipsec-paso-a-paso

El establecimiento de una VPN IPsec es complejo y sigue estos pasos detallados:

### Paso 1: Intercambio de clave (IKE)

Se crea una **Asociación de Seguridad (SA)**, que es un acuerdo sobre los atributos de seguridad entre cliente y servidor.

**A. Algoritmos Criptográficos:**

- **Simétricos:** Para cifrado (ej. AES - Estándar de cifrado avanzado).
    
- **Asimétricos:** Para intercambio de claves (ej. RSA).
    
- **Funciones Hash:** Para integridad (ej. SHA - Algoritmo de hash seguro).
    

**B. Modos IPsec:**

- **Modo Túnel:** Cifra la carga útil **y** el encabezado IP original. (Usado entre Sitios o Gateway-Gateway).
    
- **Modo Transporte:** Solo cifra la carga útil. (Usado de End-to-End).
    

**C. Parámetros de Red (AH vs ESP - Ejemplo de Carga Útil):**

- _Concepto:_ **Carga Útil** son los datos reales, **Encabezado** son datos solo para transmisión.
    
- _Ejemplo:_ Si Alice envía "Hi Bob" a la IP 192.0.2.15:
    
    - **Carga útil:** "Hi Bob".
        
    - **Encabezado:** 192.0.2.15.
        

**D. Autenticación Mutua y Clave Compartida:** Se realiza mediante IKE (Intercambio de clave por Internet).

### Paso 2: Enlace de Datos (Estructura del Paquete)

Antes de cifrar, el paquete tiene esta estructura:

1. **Encabezados (IP y TCP/UDP):** Direcciones y puertos.
    
2. **Carga Útil:** Datos reales.
    
3. **Finalizador (Trailer):** Datos suplementarios para marcar el final o relleno.
    

### Paso 3: Autenticación

Se realiza la autenticación sobre el conjunto del paquete (Encabezados + Datos + Finalizador) para asegurar que nada ha sido modificado.

### Paso 4: Cifrado (Diferencia Crítica entre Modos)

El alcance del cifrado depende del modo elegido en la SA:

**A. Modo de Transporte (AH + ESP):**

- **LO QUE SE CIFRA:** Encabezado TCP/UDP + Datos + Finalizador ESP.
    
- **LO QUE NO SE CIFRA:** Encabezado IP original + Encabezado AH + Encabezado ESP.
    

**B. Modo de Túnel (AH + ESP):**

- **LO QUE SE CIFRA:** **Encabezado IP original** + Encabezado TCP/UDP + Datos + Finalizador ESP.
    
- **LO QUE NO SE CIFRA (Externos):** **Nuevo Encabezado IP** (el de la VPN) + Encabezado AH + Encabezado ESP.
    

### Paso 5: Transmisión

- Implica el uso del **Protocolo de Datagramas de Usuario (UDP)** para el transporte del túnel debido a su baja latencia.
    
- Se realiza el descifrado y verificación en el destino.