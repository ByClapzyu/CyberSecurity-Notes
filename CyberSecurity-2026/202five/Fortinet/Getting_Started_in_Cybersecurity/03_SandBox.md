## Qué es un Sandbox?

**Definición Técnica:** Sistema que confina las acciones de una aplicación o archivo dentro de un **entorno virtual seguro y aislado**.

- **Objetivo:** Ejecutar ("detonar") el código sospechoso para observar **qué hace** realmente, sin arriesgar el sistema operativo real ni la red.
    
- **Uso:** Se aplica en redes, aplicaciones y operaciones de escritorio para reforzar la seguridad.
    

**Analogía del Mundo Real:** Imagina al **Escuadrón Antibombas**.

- Cuando encuentran una mochila sospechosa en el aeropuerto, no la abren ahí mismo. La meten en un contenedor blindado (Sandbox) y la hacen detonar ahí dentro. Si explota, nadie sale herido. Si no era nada, la devuelven.
    

---

## 2. El Problema: Amenazas de Día Cero (Zero-Day)

Las herramientas tradicionales tienen un límite:

- **Firewall y Antivirus:** Funcionan base a **Firmas** (buscan huellas digitales conocidas de virus pasados).
    
- **El Hueco de Seguridad:** Los actores de amenazas aprovechan vulnerabilidades nuevas (Zero-Day) para las cuales **aún no existen parches ni firmas**.
    
- **La Solución:** Como el Antivirus no reconoce la "cara" del virus nuevo, el Sandbox analiza su **comportamiento**. (Ej: _"No sé quién eres, pero estás intentando cifrar mis documentos, así que eres malo"_).
    

---

## 3. La Evolución del Sandbox (Pregunta de Examen)

Es vital entender por qué cambiamos de generación.

### Primera Generación: Soluciones Independientes (Silos)

- **Funcionamiento:** Eran cajas aisladas. Analizaban el archivo y daban un veredicto.
    
- **Desventaja Crítica:** **No podían compartir inteligencia.**
    
    - Si el Sandbox detectaba un virus nuevo, el Firewall y el Antivirus no se enteraban automáticamente.
        
    - _Consecuencia:_ El proceso de consolidación y análisis era manual, complicado y **tomaba mucho tiempo**. La respuesta era lenta.
        

### Segunda Generación: Integración Centralizada

- **Mejora:** Se integraban con otros dispositivos de seguridad del mismo fabricante.
    
- **Ventaja:** Permitía compartir información de forma centralizada. Si el Sandbox detectaba algo, le avisaba al Firewall para bloquearlo en toda la red.
    

### Tercera Generación: IA y Estándares (El actual)

- **Necesidad:** Los ataques modernos usan Inteligencia Artificial para evadir la detección.
    
- **Características:**
    
    - Utilizan **Machine Learning / IA** para detectar patrones complejos.
        
    - **Interoperabilidad:** Se basan en estándares universales como **MITRE ATT&CK**.
        

---

## 4. El Estándar MITRE ATT&CK

**¿Qué es?** Es una base de conocimientos global (un diccionario o enciclopedia) de tácticas y técnicas de adversarios.

**Función en el Sandbox de 3ra Generación:**

- Proporciona un **lenguaje común** para identificar, describir y categorizar las amenazas.
    
- **Beneficio:** Permite que dispositivos de **diferentes proveedores** (ej. Fortinet y Cisco) se entiendan entre sí.
    
    - En lugar de decir _"Alerta Código 504"_, el Sandbox dice _"Se detectó la técnica T1059 de MITRE"_. Todos entienden eso.
        

---

## FortiSandbox

Es la solución de Fortinet que cumple con la 3ra Generación.

- Se integra en el **Security Fabric**.
    
- Comparte inteligencia en tiempo real con FortiGate, FortiMail y FortiClient.
    
- Si FortiSandbox encuentra un Zero-Day, genera una firma y la envía a todos los dispositivos para inmunizar la red en minutos.