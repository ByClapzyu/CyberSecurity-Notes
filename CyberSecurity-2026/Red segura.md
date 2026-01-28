## Conceptos Fundamentales

**Comparativa Rápida:**

- **Perímetro Seguro:** "Confiar, pero verificar". Se enfoca en defender la frontera.
    
- **Confianza Cero (Zero Trust):** "Nunca confiar, siempre verificar". Se enfoca en proteger el recurso individual.
    
- **SD-WAN:** Red lógica sobre física. Desacopla el software del hardware.
    
- **SASE:** Convergencia de red y seguridad en la nube (implementación como servicio).
    

---

## 2. Modelo de Perímetro Seguro (Tradicional)

Se basa en la idea de una "Zona Confiable" (Red Interna) y una "Zona No Confiable" (Internet).

**Funcionamiento:**

- Verifica el acceso inicial.
    
- Si logras entrar, se te considera un usuario "confiable" interno.
    
- Se basa en reglas predefinidas y políticas comunes para todos.
    

**Capas de Filtrado (Modelo OSI):**

1. **Enlace de Datos:** Control de acceso mediante direcciones MAC y ACL (Listas de Control de Acceso que definen dispositivos de confianza).
    
2. **Transporte:**
    
    - **Filtrado de paquetes Sin Estado (Stateless):** Solo mira IP, puertos y protocolos.
        
    - **Filtrado de paquetes Con Estado (Stateful):** Rastrea la conexión completa (la 5-tupla TCP/IP).
        
    - **NAT:** Traduce IPs públicas a privadas y viceversa (oculta la red interna).
        
3. **Aplicación:** Filtrado de Proxy para protocolos específicos (FTP, SIP, Web).
    

**Limitaciones (Por qué falla hoy):**

- **Analogía del Caballo de Troya:** El modelo perimetral es como una ciudad amurallada. Es dura por fuera, pero blanda por dentro. Si un atacante logra cruzar el muro (como el Caballo de Troya), tiene vía libre para moverse lateralmente porque la red interna es "confiable".
    
- **Nuevas Tecnologías:** La desaparición del perímetro físico debido a:
    
    - **BYOD:** Dispositivos personales entrando a la red.
        
    - **IoT:** Dispositivos "sin cabeza" difíciles de asegurar.
        
    - **Nube:** Los datos ya no están en el centro de datos local.
        

---

## 3. Modelo de Confianza Cero (Zero Trust)

**Principios Clave:**

1. **Nunca confíe, verifique siempre:** La confianza no es implícita, se debe ganar en cada solicitud.
    
2. **Implemente el Privilegio Mínimo:** Dar solo el acceso justo y necesario.
    
3. **Suponga una violación de datos (Assume Breach):** Diseñar la red asumiendo que el atacante ya está dentro.
    

**La Ecuación de la Confianza:** La confianza se deriva explícitamente de: **Identidad + Contexto**.

### A. El Proceso de Identificación

Se requiere **Autenticación de Múltiples Factores (MFA)**.

- **Definición:** Método que exige presentar con éxito dos o más pruebas (factores) para acceder.
    
- **Ejemplo:** Nombre de usuario/contraseña (algo que sabes) + Código de un solo uso u OTP (algo que tienes).
    

### B. Aspectos Basados en el Contexto

No basta con saber la contraseña, el entorno debe ser seguro:

- **Hora y Fecha:** Distinguir horario laboral del no laboral. (Ejemplo: Si alguien entra a las 3 AM, pedir un OTP extra o bloquear).
    
- **Geolocalización:** Restricciones basadas en la ubicación física (Ejemplo: Bloquear accesos desde países donde la empresa no opera).
    
- **Postura de Seguridad:** Estado de salud del dispositivo. (Ejemplo: Si el dispositivo no tiene el antivirus actualizado o le faltan parches, se deniega el acceso).
    

---

## 4. Estrategia de Implementación

Pasos para construir una arquitectura Zero Trust:

**1. Definir la Superficie de Protección**

- A diferencia del "perímetro" (que es toda la red), aquí identificamos los **recursos críticos** (Datos, Aplicaciones, Activos, Servicios).
    
- Se evalúa la confidencialidad y quién necesita acceder a ellos.
    

**2. Administración de Acceso Privilegiado (PAM)**

- Mecanismo para proteger las "Llaves del Reino".
    
- Salvaguarda las identidades con permisos especiales (administradores) que van más allá de los usuarios normales.
    

**3. Aplicar el Método de Kipling**

- Se usa para crear políticas granulares haciéndose las preguntas universales durante la resolución de problemas o creación de reglas:
    
    - ¿Quién? (Usuario)
        
    - ¿Qué? (Aplicación)
        
    - ¿Cuándo? (Hora)
        
    - ¿Dónde? (Ubicación)
        
    - ¿Por qué? (Clasificación de datos)
        
    - ¿Cómo? (Dispositivo/Postura)
        

**4. Microsegmentación (Respuesta a "Suposición de Violación")**

- Divide la red en zonas muy pequeñas y seguras.
    
- Si un atacante entra en un segmento, no puede saltar a los demás. Prepara la red para "lo peor".
    

---

## 5. Componentes Técnicos de Zero Trust

**Agente de Endpoint:** Proporciona visibilidad profunda y control sobre:

- Sistema Operativo.
    
- Nivel de parches.
    
- Software instalado.
    
- Evaluación de riesgo.
    

**Control de Acceso Basado en Funciones (RBAC):** Las políticas se definen según el rol: Empleado, Invitado, Contratista, Gerente, TI, etc.

---

## 6. Comparativa Crítica: NAC vs. ZTNA

Es vital distinguir cuándo usar cada uno en una estrategia moderna.

|**Característica**|**Control de Acceso a la Red (NAC)**|**Acceso de Confianza Cero (ZTNA)**|
|---|---|---|
|**Uso Principal**|Ideal para dispositivos **IoT** o "sin cabeza" (impresoras, cámaras) que están en la red local.|Ideal para **Usuarios** y acceso a aplicaciones (especialmente remotos).|
|**Función**|Identifica dispositivos y ofrece visibilidad en la LAN.|Establece automáticamente una **sesión segura** y cifrada hacia la aplicación.|


## Resumen de Beneficios Zero Trust

- **No hay confianza implícita:** Se exige MFA y Contexto constante.
    
- **Privilegio Mínimo:** Reduce el daño potencial.
    
- **Reducción de Superficie de Ataque:** Mediante microsegmentación y revisión de acceso a los activos.


# Administración de la red de seguridad centralizada.

La administracion de la red de seguridad centralizada, consiste en recopilar datos relacionados con seguridad de diversos dispositivos en una solo ubicacion central.

a traves de una SNMP (protocolo recolecta y organiza info sobre dispsotivos administrados) y API (interfaz de software que permite a  dos dispositivos comunicarse entre si).
administracion de red: confi, control, operacion y diagnostico de seguridad

## Arquitectua Data Fabric.

monitorear y administrar los datos y las apps donde quiera que esten, sin dejar dobernanse de manera centralizada.
