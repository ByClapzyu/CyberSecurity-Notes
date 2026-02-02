- [[#introducción-al-acceso-remoto-seguro]]
    
- [[#comparativa-ipsec-ssl-ztna]]
    
- [[#vpn-ssl-definición-y-tipos]]
    
- [[#vpn-ipsec-definición-y-funcionamiento]]
    
- [[#preguntas-clave-de-examen]]
## introducción-al-acceso-remoto-seguro

**Definición:** Es una combinación de métodos y tecnologías que permiten a entidades externas conectarse a las redes sin comprometer los activos digitales ni exponer la red.

- **Contexto:** Aumento del teletrabajo (Casa, hoteles, aeropuertos) y la necesidad de protegerse contra actores maliciosos que atacan conexiones inseguras.
    

### Funciones Clave (AAA + Integridad/Privacidad)

1. **Privacidad de datos:** Ocultar la información al público (Cifrado).
    
2. **Integridad de datos:** Garantizar exactitud y coherencia (que no fue modificada).
    
3. **Autenticación:** Verificar la identidad (¿Quién eres?).
    
4. **Autorización:** Especificar derechos de acceso (¿Qué puedes hacer?).
    
5. **Registro (Accounting):** Seguimiento de actividades.
    

### Métodos Comunes

- **VPN IPsec:** Capa de Red.
    
- **VPN SSL:** Capa de Transporte (pero comunica en capa de Aplicación).
    
- **ZTNA:** Confianza Cero.
    

---

## comparativa-ipsec-ssl-ztna

Esta tabla es fundamental para el examen, ya que compara las diferencias técnicas y de implementación.

|**Característica**|**IPsec VPN**|**SSL VPN**|**ZTNA**|
|---|---|---|---|
|**Nivel OSI que protege**|**Capa de Red** (Capa 3)|**Capa de Transporte** (Capa 4)|Capa de Transporte a la Aplicación|
|**Implementación en Cliente**|Requiere Software de Cliente VPN especializado.|**Navegador Web** (Clientless) o Software Cliente.|Requiere Cliente ZTNA (Agente).|
|**Control de Acceso (Post-Sesión)**|**Ninguno.** Una vez dentro, el usuario tiene acceso amplio a la red (a menos que haya firewall interno).|**Granular.** Conecta a aplicaciones específicas.|**Muy Granular.** Basado en verificación continua por sesión.|
|**Autenticación**|Entre Cliente y Red.|Mediante solicitud web o cliente.|Usuario y Dispositivo se verifican **cada vez** que se pide acceso a una app.|
|**Filosofía**|Conexión de sitios o usuarios a la red.|Acceso remoto a recursos.|**Principio de Confianza Cero:** "No confiar en nada, verificar todo".|

## vpn-ssl-definición-y-tipos

**Definición:** Tecnología que admite una sesión cifrada desde la capa de transporte, encapsulando datos de la capa de aplicación.

**Autenticación del Servidor (Dato clave para examen):** En una SSL VPN, ¿qué se usa para autenticar el servidor web ante el navegador del usuario?

- **El Certificado Digital del servidor web.** (El candado en el navegador indica que el servidor presentó un certificado válido).
    

### Tipos de VPN SSL

**1. Portal SSL o VPN Web (Clientless - Sin Cliente)**

- **Definición:** Sesión segura establecida directamente entre un **navegador web** y el servidor.
    
- **Diferencia Clave:** **No requiere software de cliente especializado** (esta es la gran diferencia con IPsec y ZTNA).
    
- **Limitaciones:** Solo funciona para protocolos web (HTTP/HTTPS/FTP). Apps externas al navegador no funcionan.
    

**2. VPN de Túnel SSL (Tunnel Mode)**

- Requiere el cliente **FortiClient**.
    
- Permite enviar **todo el tráfico** (no solo web) por el túnel.
    

### Arquitectura (FortiGate)

Actúa como **Proxy Inverso**: Recibe las solicitudes de los usuarios remotos y las reenvía a los servidores internos, protegiendo la identidad de la red interna.

---

## vpn-ipsec-definición-y-funcionamiento

**Definición:** Seguridad en la **Capa de Red**. Protege paquetes IP completos.

**Características de Seguridad Implementables (Examen):**

1. **Cifrado de Paquetes** (Privacidad vía ESP).
    
2. **Autenticación de Paquetes** (Integridad/Origen vía AH).
    

### Funcionamiento Paso a Paso

**Paso 1: Intercambio de Clave (IKE)** Se acuerda la Asociación de Seguridad (SA): Algoritmos (AES, SHA) y el Modo (Túnel vs Transporte).

**Paso 2: Enlace de Datos (Estructura)**

- **Carga Útil (Payload):** Son los **datos legibles** (la información real que se quiere transmitir).
    
- **Encabezados:** Datos para el transporte (IPs, Puertos).
    

**Paso 3 y 4: Autenticación y Cifrado**

- **Modo Transporte:** Cifra solo la carga útil.
    
- **Modo Túnel:** Cifra la **carga útil Y el encabezado IP original**. (Es más seguro para VPNs entre sitios).
    

**Paso 5: Transmisión** Usa protocolo **UDP** para mover los datos encapsulados.

---

## preguntas-clave-de-examen

Aquí están las preguntas integradas con la teoría de arriba para tu repaso final:

**1. En la SSL VPN, ¿qué se usa para autenticar el servidor web ante el navegador?**

- **Respuesta:** El certificado digital del servidor web.
    

**2. ¿Qué dos características diferencian la SSL VPN de la IPsec VPN? (Elija dos)**

- **Respuesta A:** Permite un acceso más granular a aplicaciones y recursos (SSL VPN puede restringir acceso a apps web específicas, IPsec suele dar acceso a la red).
    
- **Respuesta B:** Proporciona seguridad desde la capa de transporte del modelo OSI (IPsec es capa de red).
    

**3. ¿Qué dos características de seguridad se pueden implementar mediante IPsec VPN? (Elija dos)**

- **Respuesta A:** Cifrado de paquete (Confidencialidad).
    
- **Respuesta B:** Autenticación de paquetes (Integridad y Origen).
    

**4. Concepto de Carga de datos útil (Payload):**

- **Respuesta:** Es la parte donde la **información es legible** (los datos reales del usuario), a diferencia de los encabezados que son para direccionamiento.
    

**5. ¿Qué característica diferencia la SSL VPN de la IPsec VPN y ZTNA?**

- **Respuesta:** SSL VPN (en modo web) **no requiere software de cliente especializado** (usa el navegador). Tanto IPsec como ZTNA requieren instalar un agente o software.
    

**6. ¿Qué característica diferencia la ZTNA de la VPN?**

- **Respuesta:** El **concepto de confianza**. (VPN confía una vez conectado; ZTNA nunca confía).
    

**7. ¿Qué enunciado describe mejor el enfoque de confianza cero en el que se basa el diseño de la ZTNA?**

- **Respuesta:** **No se puede confiar en nada, ni dentro, ni fuera de la red.** (Verificación continua).