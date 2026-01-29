[Métodos de autenticación](#métodos_de_autenticación)

[Inicio de Sesión Único (SSO)](#sso_(inicio_de_sesión_único))
- [Protocolos de SSO](#protocolos_de_sso)


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

Es el esquema o plan basico sobre como las entidades demostraran sus idnetidades dentro de un sistema.

**Servicio de autenticacion remota de usuarios de marcacion (RADIUS)
- protocolo remoto de autenticacion, autroizacion y registro (AAA)
- cliente- servidor
- punto central para la autenticacion del usuario del sistema
- pueede habilitar el marco de 802.1x

proceso:
