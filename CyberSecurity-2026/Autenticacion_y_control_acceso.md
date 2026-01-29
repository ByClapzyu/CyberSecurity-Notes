[Métodos de autenticación](#métodos_de_autenticación)

[Inicio de Sesión Único (SSO)](#sso_(inicio_de_sesión_único))
- [Protocolos de SSO](#protocolos_de_sso)

[marco,protocolo_y_herramientas_de_auntenticación](#marco,protocolo_y_herramientas_de_auntenticación)


----

# métodos_de_autenticación

### Inherencia

Se refiere a **"Algo que eres"**. Se basa en una característica física única del usuario.

- **Nota:** Se considera una autenticación estática, biométrica o pasiva.
**Ejemplos:**

- Huellas dactilares.
- Retinas.
- Iris.
- Patrones faciales.
- Medidas de las manos.
### posesión

Se refiere a **"Algo que tienes"**. El usuario debe tener el objeto físico para autenticarse.

**Ejemplos:**

- Tarjeta bancaria.
- Clave privada de firma.
- Máquina o dispositivo (que contiene contraseña o PIN).
- Mensajería SMS.
- **Token de software / hardware:**
    - **OTP:** Contraseña de un solo uso.
    - **HOTP:** Contraseña de un solo uso basada en HMAC (basada en eventos/contador).
    - **TOTP:** Contraseña de un solo uso basada en el tiempo.

### conocimiento

Se refiere a **"Algo que sabes"**. Es cuando uno se autentica con información que solo el usuario debería conocer.

**Ejemplos:**

- Preguntas y respuestas de seguridad (Q&A).
- Contraseña.
- Número de identificación personal (PIN).
### comportamiento

Se refiere a **"Algo que haces"**. Analiza la forma única en la que una persona interactúa con el sistema.

- **Nota:** Se consideran datos biométricos activos.
**Ejemplos:**

- Identificación de voz.
- Pulsación de teclas (dinámica de tecleo).
- Características de uso del ratón.

## factores contextuales y mfa

### Factores Contextuales

Son elementos externos que pueden afectar o validar el proceso de autenticación.

- Ubicación de la identidad (Geolocalización).
    
- Comportamiento de la identidad (Análisis de patrones de uso).
    
### Autenticación de Múltiples Factores (MFA)

Consiste en utilizar **varios métodos de autenticación** juntos (por ejemplo: Conocimiento + Posesión).

- **Beneficio clave:** No es tan probable que un actor malicioso logre poner en peligro múltiples factores de autenticación simultáneamente.

 ----

# sso_(Inicio_de_sesión_único)

Logra el equilibrio entre productividad y seguridad.

- **Funcionamiento:** Permite inicios de sesión únicos, pasando un **token de autenticación** (como una cookie) para iniciar sesión automáticamente en otros sitios.
    
- **Compatibilidad:** Es compatible con LDAP.
    
- **Uso:** Común en empresas y nubes (se basa en la confianza entre empresas y acuerdos entre el Proveedor de Identidad - IdP y el Proveedor de Servicios - SP).
    

---

## ventajas y desventajas

### Ventajas

- Reduce la carga de recordar múltiples credenciales.
    
- Reduce la redundancia de credenciales y los costos operativos de la organización.
    
- Facilita el cumplimiento y la organización de informes de usuario.
    
- **Nota:** Se recomienda usar MFA para reforzar la seguridad.
    

### Desventaja

- Si las credenciales se ven comprometidas, dan al actor malicioso acceso a todo.
    

---

## cómo funciona (flujo)

Se necesitan los siguientes actores:

- Usuario.
    
- Proveedor de Servicio (SP).
    
- Proveedor de Identidad (IdP).
    

**El flujo es:** Usuario --> SP --> IdP ---> **Token de autenticación** (Token incrustado como prueba de su autenticación) --> SP.

---

## protocolos_de_sso

### OAuth

Son estándares abiertos de delegación de acceso que se usan para que los usuarios concedan a sitios o aplicaciones acceso a su información en otros sitios, pero **sin dar las contraseñas**.

### SAML (Security Assertion Markup Language)

Basado en **XML**. Usa afirmaciones de seguridad para intercambiar información entre las partes.

**Tipos de aserciones (afirmaciones):**

1. **La aserción de autenticación:** Indica cómo se autenticó la entidad e incluye fecha y hora.
    
2. **La aserción de atributos:** Proporciona información adicional sobre la identidad.
    
3. **La aserción de autorización:** Identifica lo que la identidad está autorizada a hacer.
    

---

## fortiauthenticator

- Actúa como IdP (Proveedor de Identidad).
    
- Verifica las credenciales con el servidor de autenticación

---
# marco,protocolo_y_herramientas_de_auntenticación

**Definición:** Es el esquema o plan básico sobre cómo las entidades demostrarán sus identidades dentro de un sistema.

---

## radius-servicio-de-autenticación-remota

**Definición (RADIUS):** Servicio de autenticación remota de usuarios de marcación.

- Es un protocolo remoto de **Autenticación, Autorización y Registro (AAA)**.
    
- Funciona bajo arquitectura **Cliente-Servidor**.
    
- Actúa como punto central para la autenticación del usuario del sistema.
    
- Puede habilitar el marco de 802.1x.
    

**Proceso de autenticación RADIUS:** Utiliza **paquetes de datos** para intercambiar información entre dispositivos en una red de conmutación.

- Son unidades de datos formateadas que contienen información de control y datos de usuario (conocidos como **carga útil**).
    

**Repositorio de credenciales de usuario RADIUS:** El servidor RADIUS puede verificar las credenciales contra:

1. **Base de datos RADIUS:** Local (interna).
    
2. **Servidores externos:**
    
    - Lenguaje de consulta estructurada (SQL).
        
    - Protocolo ligero de acceso a directorios (LDAP).
        

---

## ldap-protocolo-ligero-de-acceso-a-directorios

**Definición:** Protocolo abierto de aplicación estándar de la industria para acceder a servicios de directorio a través de una red IP. Es un protocolo de comunicación para servidores de directorio.

**Nota Importante:**

- **Microsoft Active Directory (AD)** es el ejemplo más común de un directorio compatible con LDAP.
    

---

## tacacs-y-comparativa-con-radius

### TACACS+

**Definición:** Similar a RADIUS, TACACS+ es un protocolo remoto de **Autenticación, Autorización y Registro (AAA)**.

**Diferencias Técnicas 

|**Característica**|**RADIUS**|**TACACS+**|
|---|---|---|
|**Cifrado**|Solo cifra las **contraseñas**.|Cifra **todos** los protocolos AAA (toda la carga útil).|
|**Protocolo de Transporte**|Usa **UDP**.|Usa **TCP** (más fiable).|

## métodos-de-autenticación-pap-y-chap

Definen la manera en que se hace la autenticación y establecen las reglas de interacción y verificación que los endpoints usan para comunicarse.

### Protocolo de autenticación de contraseña (PAP)

- **Funcionamiento:** Envía el Nombre de usuario y contraseña; el servidor responde simplemente con "Aceptar" o "Rechazar".
    
- **Características:**
    
    - Usa un proceso de establecimiento de comunicación de **dos vías**.
        
    - Usa información de autenticación **estática**.
        
    - Puede autenticar sesiones PPP.
        

### Protocolo de autenticación por desafío mutuo (CHAP)

- **Funcionamiento:** Implica la generación de una cadena aleatoria, autenticación hash cifrada y una respuesta.
    
- **Características:**
    
    - Usa un proceso de establecimiento de comunicación de **tres vías** (Desafío - Respuesta - Verificación).
        
    - La cadena aleatoria y el resultado hash garantizan información de autenticación **dinámica**.
        
    - Puede autenticar sesiones PPP.
        
    - **Nota:** La versión de Microsoft se llama **MS-CHAP**.
        

---

## marco-de-autenticación-802-1x

**Definición:** Es un estándar IEEE para el **Control de acceso a la red basado en puertos (PNAC)**.

**Componentes del Marco (Los 3 Roles):**

1. **Solicitante (Supplicant):**
    
    - Es el dispositivo **cliente** (laptop, teléfono).
        
    - Envía los formularios de autenticación (Nombre de usuario/Contraseña o Certificado digital).
        
2. **Intermediario (Authenticator):**
    
    - También conocido como **Autenticador**.
        
    - Es el dispositivo de red que proporciona el enlace físico entre el cliente y la red.
        
    - **Ejemplos:** Switch de Ethernet o Punto de Acceso Inalámbrico (AP).
        
3. **Servidor de autenticación:**
    
    - Es el servidor de confianza que adjudica y decide el proceso.
        
    - Normalmente admite los protocolos **RADIUS** y **EAP**.


![[autenticacion_802.1x.png]]


---

# control_de_acceso_y_metodos

Control de acceso: restringe el acceso a lugar o recusos / autorizacion
- lista
- identificacion


Control de acceso obligatorio (MAC): no permite que ningun actor cambie los requisitos de seguridad.

Control de acceso discrecional (DAC): permite que un factor externo modifique las restricciones de control de acceso.  el sujeto o mecanismo