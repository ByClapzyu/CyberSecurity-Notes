[Métodos de autenticación](#métodos_de_autenticación)

[Inicio de Sesión Único (SSO)](#sso_(inicio_de_sesión_único))

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

Logra el quilibrio entre productividad y seguridad.

unico inicios de sesion, pasando token de autenticación (como cookie )para inicar en otros sitios. LDAP combatible 

comun en empresas y nubes. (confianza entre empresas , idp sp acuerdo)

Ventajas:
- reduce carga de recordar credenciales
- reduce redudncia de credenciales y costos operativos de la organizacion
- facilida el cumplimineto y la organizacion de informe de usuario

nota : (usar mfa para reforzar)
Desventaja

- credenciales comprometidas dan al actor accreso a todo


como funciona?

necestia:
- usuario
- proveedor de srvicio sp
- prodeveedor de identidad 
- idp
usaurio --> sp --> idp  ---> token autenticacion , token inscurtado prueba de su autenticacion--> sp


Protocolo de SSO

- QAuth
- SAML:  basado en xml . Usa afirmaciones de seguridad para intecambiar info entre las partes 
	- la sercion de uatenticacion: indica como se autentico la entidad e incluye fcha y hora
	- la asersion de atributos proporciona infromacion adicional sobre la identidad
- asercion de autorizacion identifica lo que la identidad esta autorizada a hacer
- Los protocolos de sso son estandares abiertos de delegacion de acceso que se us para que losusuarios concedan a sitios o paps acceso a su info en otros sitios, pero sin darlas contraseñas.

ForitAuthenticator:
- idp verifica con servidor de autenticacion
- 