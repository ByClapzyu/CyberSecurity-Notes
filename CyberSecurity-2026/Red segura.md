
Perimetro seguro: confiar pero verificar
- verificar acceso inciarl, confiable interno/ no externo
- reglas predefinidas y politicas comunes.

confianza cero: no confiar simere verificar


SD-WAN
Red logica sobre fisica, 

SASE: nube, implementacion como servicio ocn seguridad itegrada.


# Perimetro seguro

Zona confiable / red adminsitrada (confiable)
- autenticacion
- autorizacion
filtra trafico capa osi:
- enlace de datos: (control de acceso: MAC, ACL (lista define dispostivos de onfianza y acciones especificar para una red))
- **transporte**: filtrado de paquetes (sin estado: basandose en direccion ip, puertos  protocolo ) con estado (5 tupla, conexion tcp/ip), filtrado de NAT (traducir una ip publica a privada y viceveversa) red privada, ip puerto. 
- **app**: filtrado de proxy () ftp sip, puerto tcp/udp

Limitaciones
- BYOD (dispostivo persoanl)
- IoT
- Nube

# Confianza zero

Identidad y contexto 
- nunca confie, verifique siempre
	- autenticacion y autorizacion
- implemente el privilegio minimo
- suponga que su red tuvo una violacion de datos
	- reducción de la superficie de ataque.
red perimetral
definicion
y algo de un ataque que dieron ejemplo del caballo de troya.


El principio de nunca confie:
- **Definición:** La confianza se deriva explícitamente de una combinación de aspectos basados en la identidad y el contexto.
    
- **Proceso de identificación:** Autenticación de múltiples factores.
    
- **Aspectos basados en el contexto:**
    
    - Hora y fecha
        
    - Geolocalización
        
    - Postura de seguridad
        

---

### **Autenticación de múltiples factores (MFA)**

- **Definición:** La Autenticación de múltiples factores (MFA) es un método de autenticación en el que solo se permite el acceso a un usuario o dispositivo informático después de presentar con éxito dos o más pruebas, o factores, a un mecanismo de autenticación.
    
- **Ejemplo típico:** Una forma típica de conseguir la MFA es exigir un nombre de usuario y una contraseña más un código de acceso de un solo uso.
    

---

### **Ejemplos de Contexto de Seguridad**

**Contexto de Hora y fecha**

- Un ejemplo de contexto de hora y fecha es cuando se distingue el horario laboral del no laboral comercial para restringir el acceso a los recursos o para exigir un método adicional de autenticación, como la contraseña de un solo uso (OTP).
    

**Contexto de Geolocalización**

- Un ejemplo de contexto basado en la geolocalización es cuando las alertas pueden activar restricciones para los recursos basándose en la ubicación geográfica del solicitante.
    

**Contexto de Postura de seguridad**

- Un ejemplo de contexto basado en la postura de seguridad es cuando se imponen restricciones a un dispositivo que no cumple los requisitos de seguridad, como parches actualizados y software antivirus.

### **Estrategia de Seguridad y Pasos**

1. **Administración de acceso privilegiado (PAM)**
    
2. **Definir la superficie de protección**
    
3. **Aplicar el método de Kipling**
    

---

### **Detalles de los Componentes**

**1. Administración de acceso privilegiado (PAM)**

- PAM es un mecanismo de seguridad de la información que salvaguarda las identidades con acceso o funcionalidades especiales más allá de los usuarios normales.
    

**2. Superficie de protección**

- Definir la superficie de protección es un proceso que consiste en identificar los recursos de la red, evaluar el grado de confidencialidad y determinar qué funciones necesitan acceder a estos.
    

**3. Método de Kipling**

- El método de Kipling consiste en hacerse una serie de preguntas, como ¿quién?, ¿qué?, ¿cuándo?, ¿dónde?, ¿por qué? y ¿cómo?, durante la preparación de la resolución de un problema.

principio de suposicion de una violacion de datos
preparacion para lo peor
microsegmentacion


Otros metodos de confianza cero