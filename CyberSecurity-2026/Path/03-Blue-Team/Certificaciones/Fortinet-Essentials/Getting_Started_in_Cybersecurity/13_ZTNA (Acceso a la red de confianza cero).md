## Definición y Filosofía

**Concepto ZTNA:** Es un modelo de seguridad que establece una sesión segura entre una entidad final (usuario/dispositivo) y la red corporativa.

- **Independencia:** Funciona igual sin importar si el usuario está en la oficina o en una cafetería, y sin importar dónde esté alojada la red (On-premise o Nube).
    
- **Recursos Ocultos:** A diferencia de una VPN tradicional donde se ve toda la red, en ZTNA los recursos no publicados son invisibles para el usuario.
    

**Filosofía de Confianza Cero (Zero Trust):**

- **Principio:** "Nunca confiar, siempre verificar".
    
- **Acceso con Mínimos Privilegios:** Se otorga acceso solo a lo estrictamente necesario.
    
- **Túneles Cifrados Automáticos:** Se crea un túnel seguro desde la entidad final hasta el proxy de acceso (ej. Firewall FortiGate).
    

##  Componentes de la Arquitectura

1. **Cliente de ZTNA:** Software instalado en el endpoint (Agente) o uso a través de navegador web (Clientless).
    
2. **Proxy de Acceso de ZTNA:** Es la puerta de entrada que intercepta la conexión, verifica y permite el paso. (En soluciones Fortinet, este rol lo cumple el **FortiGate**).
    
3. **Servidor de Autenticación:** Verifica quién es el usuario (AD, LDAP, IDaaS).
    
4. **Motor de Políticas (Policy Server):** Define quién entra y quién no.
    

##  Control de Acceso Dinámico

ZTNA no revisa al usuario una sola vez; lo hace constantemente.

**Acceso por Sesión (Granularidad):** Cada vez que un usuario intenta acceder a un recurso, se realiza una nueva evaluación.

- Se autentica al usuario.
    
- Se evalúa el riesgo del dispositivo en tiempo real.
    

**Factores de Decisión (Contexto):** Para dar acceso, el sistema analiza:

- **Identidad del Usuario:** ¿Quién es? (Rol, departamento).
    
- **Identidad del Dispositivo:** ¿Es una laptop corporativa o personal?
    
- **Postura de Seguridad (Perfil de Riesgo):** ¿Tiene antivirus? ¿Está actualizado?
    

---

##  Flujo de Trabajo e Implementación (Fortinet)

En el ecosistema de Fortinet, los roles se definen así:

**Componentes:**

- **Cliente:** FortiClient (Local o Remoto).
    
- **Servidor de Políticas:** FortiClient EMS (Enterprise Management Server).
    
- **Proxy de Acceso:** FortiGate.
    
- **Destino:** Servidores protegidos.
    

**Intercambio de Información (Telemetría):**

1. **FortiClient (Endpoint)** envía a **FortiClient EMS**:
    
    - Atributos del dispositivo (Sistema Operativo, versión).
        
    - Información del usuario (ID).
        
    - **Postura de Seguridad:** Estado actual de salud del dispositivo (si tiene parches, antivirus activo, vulnerabilidades).
        
2. **FortiClient EMS** procesa esto y genera:
    
    - **Certificado Digital:** Para identificar al dispositivo.
        
    - **Etiquetas (Tags):** Aquí es donde entra tu nota clave.
        
        - _Nota:_ **La información u objeto que incluye la etiqueta representa la postura de seguridad del dispositivo.** (Ejemplo: Etiqueta "Seguro", Etiqueta "Vulnerable", Etiqueta "Finanzas").
            

---

##  El Proceso de Conexión (Paso a Paso)

Cuando un usuario intenta entrar, ocurren estos tres pasos secuenciales:

### Paso 1: Validación de la Identidad del Dispositivo

- **A.** El endpoint intenta conectar al Proxy (FortiGate).
    
- **B.** FortiGate solicita la identificación del dispositivo.
    
- **C.** El endpoint presenta su **Certificado de Dispositivo** (el que le dio el EMS).
    
- **D.** FortiGate verifica el certificado y revisa las **Etiquetas** de postura de seguridad asociadas. (Si la etiqueta dice "Vulnerable", bloquea el acceso aquí).
    

### Paso 2: Autenticación del Usuario

- **A.** Si el dispositivo pasa, FortiGate pide identificación del usuario.
    
- **B.** El usuario ingresa credenciales (o usa SSO).
    
- **C.** FortiGate valida contra el servidor de identidad (AD, LDAP, IDaaS).
    
- **D.** Se recuperan las funciones/roles del usuario.
    
- **E.** FortiGate cruza la información: ¿Este Usuario + Este Dispositivo tienen permiso para Esta Aplicación?
    

### Paso 3: Establecimiento de Sesión

- Una vez validadas ambas identidades (Usuario y Dispositivo) y verificada la postura de seguridad, se establece la **sesión cifrada** hacia el recurso específico.