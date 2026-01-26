
Establece una sesion segura entre una entidad final y una red, al mismo tiempo gaarantiza un control granular sobre el acceso a los recursos y ejerce confianza cero, independientemente de la ubivacion de la entidad final o de la red.

**confinazza cero**: acceso con minimo privilegios (no confia en nadie)
Automatica tuneles cifrados:
	Entidad final al proxy de acceso de ztna (ejemplo da ejemplo, por ejemplo firewall)
	recursos ocultos 
**Componentes:**

- Cliente de ZTNA (se puede utilizar con un navegador web)
    
- Proxy de acceso de ZTNA
    
- Servidor de directorio de autenticación local o identidad como servicio (IDaaS)
    
- Servidor y firewall de política de seguridad de ZTNA

- **Control de acceso dinámico**
    
    - Acceso granular por sesión
	    - acceso por sesión: significa cada vez que el usuario se conecta a la red, se autentica y se hace una avaluacion de riesgo sobre el dispostivo que se coencta.
        
    - **Basado en:**
        
        - Identidad del usuario
            
        - Identidad del dispositivo y perfil de riesgo.
	        - dispostivi: puede ser una compu, o un portatil
            
        - Política: puede definir parametros de acceso a los recursos segun su función del usuario, el tipo de dispositvo y otros factores.

### **Flujo de trabajo de ZTNA**

**Componentes del Diagrama:**

- **Clientes:** Cliente local con FortiClient y Cliente remoto con FortiClient (conectado vía Internet).
    
- **FortiClient EMS:** Servidor de políticas de ZTNA.
    
- **FortiGate:** Firewall y Proxy de acceso de ZTNA.
    
- **Destino:** Servidores protegidos y recursos.
    

**Intercambio de información:**

- **FortiClient envía la siguiente información a FortiClient EMS:**
    
    - Atributos del dispositivo, como el tipo de sistema operativo.
        
    - Información del usuario, como ID de usuario.
        
    - Postura de seguridad del dispositivo.
        
- **FortiClient EMS genera:**
    
    - Etiquetas.
        
    - Un certificado digital de cliente.
        

---

### **¿Cómo funciona el ZTNA de Fortinet?**

#### **Paso 1: Validación de la identidad del dispositivo**

- **A.** El endpoint se conecta al proxy de acceso de ZTNA.
    
- **B.** FortiGate desafía al endpoint para la identificación del dispositivo.
    
- **C.** El endpoint envía el certificado del dispositivo a FortiGate, que emite FortiClient EMS.
    
- **D.** FortiGate aplica las etiquetas y reglas asociadas al dispositivo.
    

#### **Paso 2: Autenticación del usuario**

- **A.** FortiGate desafía al endpoint para la autenticación del usuario.
    
- **B.** El usuario introduce sus credenciales en el endpoint.
    
- **C.** FortiGate reenvía las credenciales al servidor de autenticación, que puede ser un AD, un directorio LDAP, una base de datos o una Identidad como servicio (IDaaS).
    
- **D.** La identidad del usuario se valida y se recuperan sus funciones en el servidor de autenticación.
    
- **E.** FortiGate usa las funciones del usuario para determinar el acceso a la aplicación de la red.
    

#### **Paso 3: Establecimiento de sesión**

1. Validación de la identidad del dispositivo.
    
2. Autenticación del usuario.
    
3. **Sesión cifrada establecida.**

no se donde poner pero: info u objeto que incluye la etiqueta es la postura segurdad del dispostivo