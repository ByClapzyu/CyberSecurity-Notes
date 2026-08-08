
# Qué es la ciberseguridad?

Es la práctica de proteger dispositivos, redes, aplicaciones y datos contra ataques digitales.

- **Objetivo Principal:** Preservar la **Tríada CIA** (Confidencialidad, Integridad, Disponibilidad) en el ciberespacio.
    
- **Alcance:** Protege bases de datos, endpoints, servidores y redes detectando brechas y vulnerabilidades.

**Las 5 Categorías Clave:**

1. **Infraestructura Crítica:** (Energía, transporte).
    
2. **Seguridad de Aplicaciones:** (Software seguro desde el diseño).
    
3. **Seguridad de Red:** (Protección del tránsito de datos).
    
4. **Seguridad en la Nube:** (AWS, Azure, Private Clouds).
    
5. **Internet de las Cosas (IoT):** (Cámaras, sensores, dispositivos inteligentes).
# Seguridad de la infromación (infosec) vs Seguridad Sistema Información

**Seguridad de la Informacióm (InfoSec)**
    Se encarga de proteger la información **en cualquier formato** (físico o digital). Su meta es **prevenir, detectar, corregir** para que la informacion cumpla con la triada (CIA), asi tambien se encarga de los procesos, amenazas y sistemas que afecten la seguridad de la información
    
- **Alcance:** Archivos en papel, conversaciones verbales y datos en computadoras.
    
- **Clasificación de datos:**
    
- _Desprotegida:_ Información pública.
        
- _Protegida:_ Requiere control (Confidencial, Secreta, Top Secret).
    
  
**Seguridad Sistema Información**
    Es la protección de los sistemas (hardware/software) y la informacion que contienen, contra: 
    
   - Acceso no autorizado 
   - Modificación o Destrucción.
   - Denegación de servicio a usuarios autorizados.

- **. ¿Qué protege exactamente? (El Alcance)** :

	- **Dispositivos:** (Servidores, Laptops, Discos Duros).
    
	- **Redes Informáticas:** (Cables, Switches, Wi-Fi).
    
	- **Ubicación de los dispositivos:** (El site, el cuarto de servidores, el edificio).
**3. Naturaleza:**

- Combina protección **Digital** + protección **Física**.
------------------------
# Principios Opuestos CIA vs DAD

| ** Tríada CIA (Lo que queremos)** | ** Tríada DAD (El ataque)**  | **Definición del Ataque**                                                       |
| --------------------------------- | ---------------------------- | ------------------------------------------------------------------------------- |
| **C**onfidencialidad              | **D**ivulgación (Disclosure) | Los datos son expuestos a personas no autorizadas (Filtraciones).               |
| **I**ntegridad                    | **A**lteración               | Los datos son modificados sin permiso, perdiendo su autenticidad.               |
| **D**isponibilidad                | **D**enegación / Destrucción | Se impide el acceso a los datos o sistemas a los usuarios legítimos (Ej. DDoS). |

# Modelo AAA 

Es el marco de control de acceso. Imagínalo como entrar a un edificio seguro.

1. **Autenticación (Authentication):**
    
    - _Pregunta:_ "¿Quién eres?"
        
    - _Acción:_ Verificar la identidad (Usuario/Contraseña, Biometría, Token).
        
2. **Autorización (Authorization):**
    
    - _Pregunta:_ "¿Qué tienes permiso de hacer?"
        
    - _Acción:_ Controlar el acceso a recursos específicos (Ej. Puedes entrar al Lobby, pero no al centro de datos).
        
3. **Contabilidad / Registro (Accounting):**
    
    - _Pregunta:_ "¿Qué hiciste?"
        
    - _Acción:_ Rastreo y registro de actividades (Logs) para auditoría forense.

# Primera Linea de Defensa y Recomenaciones

- **El Eslabón Humano:** Las personas suelen ser el punto más débil. La capacitación y concientización son la primera línea de defensa.
    
- **Recuperación:** Prepararse para el desastre es obligatorio.
    
    - _Backup:_ Copias de seguridad periódicas.
        
    - _Disaster Recovery:_ Planes para restaurar la operación tras un incidente.
        
- **Identificación de Activos:** Antes de proteger, debes determinar **qué información es valiosa**. No puedes proteger lo que no sabes que tienes.
