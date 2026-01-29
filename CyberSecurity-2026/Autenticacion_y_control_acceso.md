[Métodos de autenticación](#métodos_de_autenticación)

[Inicio de Sesión Único (SSO)](#sso_(inicio_de_sesión_único))
- [Protocolos de SSO](#protocolos_de_sso)

[marco,protocolo_y_herramientas_de_auntenticación](#marco,protocolo_y_herramientas_de_auntenticación)

[Control de acceso y metodos](#control_de_acceso_y_metodos)

[Buenas prácticas de control de acceso](#buneas-practicas-de-control-de-acceso)

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

Restringe el acceso a un lugar o recursos (Autorización).

- **Mecanismos:** Se basa en una **lista** o en la **identificación**.
    
## mac-control-de-acceso-obligatorio

**Definición:** Es el modelo más estricto. **No permite que ningún actor cambie los requisitos de seguridad**. El sistema impone la política y el usuario no puede alterarla.

**Ejemplos:**

- Candado (Seguridad física estricta).
    
- Sistema operativo **SELinux** (Security-Enhanced Linux).
    
## dac-control-de-acceso-discrecional

**Definición:** Permite que un factor externo modifique las restricciones de control de acceso. El sujeto (dueño del recurso) o mecanismo puede ajustar los permisos e incluso conceder nuevos accesos a otros.

**Ejemplos:**

- Guardia de seguridad de un edificio (Decide quién pasa).
    
- Control de cuentas de usuario (**UAC**) de Microsoft.
    
- Permisos del sistema de archivos **Linux** (chmod/chown).
    

## abac-control-de-acceso-basado-en-atributos

**Definición:** Control de seguridad dinámico que involucra y evalúa **varios atributos** complejos para tomar una decisión (como la hora del día + la identificación + ubicación).

**Ejemplos:**

- Control de acceso dinámico (**DAC**) de Microsoft.
    
- Modelos de seguridad de base de datos.
    
- Políticas de **Next-Generation Firewall** (NGFW).
    
## rbac-control-de-acceso-basado-en-funciones

**Definición:** El acceso se otorga según el **rol** o puesto de trabajo del usuario dentro de la organización, no por su identidad individual.

**Ejemplos:**

- Seguridad de grupo de **Active Directory** de Microsoft.
    
- Funciones de **administrador** en muchos sistemas operativos y dispositivos de seguridad.
    
- Políticas de seguridad de la empresa basadas en la función o el cargo.
    
## rsbac-control-de-acceso-basado-en-reglas

**Definición:** El acceso se basa en una lista de reglas estrictas (Si cumple X regla, pasa).

**Ejemplos:**

- Conjuntos de reglas del enrutador (Router ACLs).
    
- **iptables** (Firewall de Linux).
    
- Puertas de hotel con cerradura de tiempo.
    
- Tarjetas de entrada a áreas restringidas.
    
## lbac-control-de-acceso-basado-en-etiquetas

**Definición:** Asigna etiquetas de seguridad a los usuarios y a los datos (Lattice-Based Access Control).

**Ejemplos:**

- Clasificación de documentos (Confidencial, Secreto, Top Secret).

---

# buneas-practicas-de-control-de-acceso

## ciclo-de-vida-administracion-identidad-acceso

**Fases del Ciclo:**

1. **Aprovisionamiento:**
    
    - Crear cuenta para usuario o dispositivo.
        
    - Asignar funciones o grupos.
        
2. **Autenticación:**
    
    - Validar la identidad del usuario o dispositivo.
        
3. **Autorización:**
    
    - Determinar si un usuario válido tiene permisos.
        
    - Hacer auditoría y registrar las conexiones.
        
4. **Autoservicio:**
    
    - Cambio de contraseña.
        
    - Actualizar la información de cuenta.
        
    - Solicitar acceso a información denegada.
        
    - Informar sobre actividades sospechosas.
        
5. **Dar de baja:**
    
    - Quitar permisos.
        
    - Eliminar reglas, funciones y grupos de control de acceso.
        

**Actividades Generales:**

- Crear reglas de política, funciones y grupos de control de acceso.
    
- Revisión periódica de todas las fases del ciclo de vida.
    

---

### **Desafíos del control de acceso**

1. **Configuración del control de acceso:**
    
    - Varias funciones, grupos y políticas en varios departamentos y dispositivos.
        
    - Complejidad de las reglas.
        
    - Comprensión incoherente de los dispositivos de control de acceso.
        
    - Reglas mal configuradas o que no se usan y dificultan la configuración correcta.
        
2. **Coherencia:**
    
    - Flexibilidad necesaria para crear políticas de control de acceso adecuadas.
        
    - Creación de varias políticas y reglas de control de acceso coherentes en varias plataformas.
        
3. **Experiencia del usuario:**
    
    - Cambio de contraseñas.
        
    - Manejo de contraseñas caducadas.
        
    - Otorgar acceso adicional a los recursos necesarios fácilmente.
        
4. **Auditoría:**
    
    - Creación de un registro unificado en papel para la autenticación y autorización.
        
    - Manejo de sitios geográficamente dispersos y ubicaciones de control de acceso.
        
    - Consolidación de varios tipos de dispositivos de control de acceso y tipos de registro.
        

---

### **Políticas de Usuarios**

- Política de reportes.
    
- Política de contraseña.
    
- Política de uso permitido.
    

---

### **Archivos y carpetas: Permisos y Jerarquía**

- **Concepto:** Conocer los permisos de archivos y carpetas de los distintos sistemas operativos al definir políticas de control de acceso.
    
- **Herencia y jerarquía de permisos para sistemas de archivos:**
    
    - Tenga siempre en cuenta cómo se asignan el control de acceso y los permisos a los sistemas de archivos.
        
    - Aplicar permisos a una carpeta y a todas las carpetas y archivos en esta para garantizar la máxima protección.
        
    - Evitar cambiar muchos permisos pequeños, específicos y separados de archivos y carpetas a un grupo o usuario específico.
        
    - Consolidar archivos y carpetas con los mismos conjuntos de permisos en una sola ubicación para facilitar la aplicación de la política de control de acceso y evitar el crecimiento descontrolado de privilegios y la complejidad.
        

---

### **Principio de privilegio mínimo y arquitectura de confianza cero**

**Principio de privilegio mínimo (PoLP):**

- **Objetivo:** Minimiza la superficie de ataque.
    
- **Definición:** Permite que un usuario o dispositivo acceda solo a los recursos que necesita para cumplir su propósito.
    

**Arquitectura de confianza cero (ZTA):**

- **Objetivo:** Verifica continuamente.
    
- **Definición:** Autentica y autoriza todas las conexiones a recursos independientemente de dónde provengan las conexiones.
    

**Diagrama de Flujo:**

- Las conexiones (Remoto, Campus, Sucursal) se tratan bajo el principio de "Nunca confíe".
    
- La ZTA aplica una política de "Siempre verifica" antes de dar acceso a los recursos.


## Administradores y permisos

### **dministradores y gobernanza: Descripción General**

- Controlar la postura de seguridad y crear políticas de control de acceso.
    
- Definir políticas importantes de escalada, desastres e incorporación/baja.
    
- Comunicar estas políticas a través de planes y políticas de seguridad.
    
- Hacer auditorías periódicas de las cuentas de usuario y de las políticas de control de acceso.
    

---

### **1. Separación de funciones**

- Mantener siempre la separación entre usuarios y administradores con cuentas y políticas de control de acceso.
    
- Control de acceso separado para los distintos departamentos que tienen requisitos diferentes para permitir un control de acceso más granular y seguro.
    
- Aplicar esto a nivel de sistema operativo usando funciones como el Control de acceso de usuarios (UAC) de Windows y los privilegios de superusuario de Linux.
    
- Separar el control de acceso mediante divisiones que tengan sentido, como el departamento, el nivel de trabajo o la ubicación geográfica.
    
- Minimizar la sobrecarga, el crecimiento descontrolado de reglas y la escalada de privilegios.
    

### **2. Creación y recertificación de políticas de control de acceso**

- Crear y documentar la creación de políticas de control de acceso para que un administrador pueda ver el panorama general.
    
- Revisar periódicamente (al menos una vez al año) todas las políticas de control de acceso para comprobar si son pertinentes o si es necesario actualizarlas o eliminarlas.
    
- Reevaluar las políticas de control de acceso cuando se produzcan cambios importantes en la red o en la infraestructura, y no suponga que las políticas existentes podrán manejar nuevos equipos o situaciones.
    

### **3. Instrucción de los usuarios**

- Conocimiento de las políticas de seguridad y control de acceso de la empresa.
    
- Capacidad para crear contraseñas seguras y usar formularios de cambio.
    
- Capacidad para identificar e informar actividades sospechosas o políticas de control de acceso mal configuradas.
    

### **4. Incorporación, recertificación y baja de usuarios**

- Métodos de incorporación claros y fáciles de usar para crear perfiles de control de acceso seguro.
    
- Recertificación periódica para garantizar que los usuarios tienen asignadas las políticas de control de acceso correctas.
    
- Políticas exhaustivas para la baja de usuarios para eliminar todos los accesos de los usuarios y las cuentas antiguas.
    

### **5. Planes de escalado y recuperación de desastres**

- Planes públicos de recuperación de desastres.
    
- Estrategias de escalado claras y fáciles de usar para que los usuarios puedan informar de actividades sospechosas y denunciar políticas de acceso mal configuradas.