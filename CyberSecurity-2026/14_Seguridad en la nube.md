## Evolución: Del On-Premise a la Nube

**El Pasado (On-Premise)** Antes, cada organización mantenía sus propios centros de datos y equipos físicos.

- **Problema:** Era costoso de mantener (mano de obra, electricidad, refrigeración). Aunque ofrecía ventajas competitivas en su momento, resultaba ineficiente porque muchos servidores permanecían inactivos o subutilizados, desperdiciando recursos.
    

**La Solución: Virtualización** Tecnología que permite que un único servidor físico ejecute simultáneamente múltiples sistemas operativos y aplicaciones de varios servidores lógicos.

- **Beneficios:**
    
    - Aumenta el uso de los recursos (maximiza el hardware).
        
    - Ahorra dinero en infraestructura física.
        
- **Resultado:** Esta tecnología fue la base para el nacimiento de la **Computación en la Nube**.
    

---

##  Modelos de Servicio en la Nube

Se definen por quién gestiona qué capas de la tecnología (Modelo de Responsabilidad Compartida).

### A. Infraestructura como Servicio (IaaS)

Es el modelo más flexible y parecido a tener tu propio centro de datos, pero virtual. Una organización recurre a este servicio cuando la demanda varía (ej. picos de tráfico estacionales o vacaciones), permitiendo escalar recursos rápidamente.

**Responsabilidad Compartida:**

- **El Proveedor proporciona (Hardware y Virtualización):**
    
    - Redes físicas.
        
    - Almacenamiento físico.
        
    - Servidores físicos.
        
    - Capa de Virtualización (Hypervisor).
        
- **La Organización proporciona (Software y Configuración):**
    
    - Sistema Operativo (Windows, Linux).
        
    - **Middleware:** Software que conecta aplicaciones (ej. bases de datos, servidores web). _Nota: Aquí tú instalas y gestionas este software sobre la máquina virtual._
        
    - Datos.
        
    - Aplicaciones.
        

### B. Plataforma como Servicio (PaaS)

Este servicio alquila plataformas basadas en la nube ideales para que los **desarrolladores de software** creen, prueben y distribuyan aplicaciones sin preocuparse por el sistema operativo.

**Responsabilidad Compartida:**

- **El Proveedor gestiona:**
    
    - Todo lo de IaaS (Redes, Servidores, Virtualización).
        
    - **Sistema Operativo** (Ya viene instalado y parcheado).
        
    - **Middleware** (Entornos de ejecución como .NET, Java, Python ya listos).
        
- **La Organización gestiona:**
    
    - Datos.
        
    - Aplicaciones (El código que desarrollan).
        

**Beneficios y Ciclo de Vida:** Hace que el ciclo de desarrollo sea más fácil, eficiente y barato. Cubre las etapas de:

1. Desarrollar.
    
2. Probar.
    
3. Implementar.
    

### C. Software como Servicio (SaaS)

Es el modelo de consumo final. El software está alojado y gestionado al 100% por el proveedor.

**Responsabilidad:**

- **El Proveedor gestiona:** TODO (Desde las redes físicas hasta la aplicación y sus datos base).
    
- **La Organización/Usuario:** Solo consume el servicio y configura accesos.
    

**Ejemplos:**

- **Netflix:** Tú no gestionas los servidores ni el código de la app, solo ves las películas.
    
- **Salesforce:** CRM gestionado en la nube.
    
- **Office 365 / Google Workspace:** Correo y ofimática listos para usar.
    
- **Dropbox:** Almacenamiento listo para usar.
    

---

##  Seguridad en la Nube

La seguridad en la nube se basa estrictamente en el **Modelo de Responsabilidad Compartida**. La seguridad no es solo tarea del proveedor (AWS/Azure/Google), el cliente también tiene obligaciones.

**Componentes:**

- **Físicos:** Responsabilidad del proveedor (Cámaras, guardias en el datacenter).
    
- **Lógicos:** Responsabilidad compartida o del cliente (Contraseñas, cifrado).
    

### Responsabilidades Específicas en IaaS

En una infraestructura IaaS, el proveedor asegura la "Nube" (el hardware), pero el **Cliente** es responsable de asegurar lo que pone "en" la nube:

1. **Acceso:** Gestión de usuarios y contraseñas (IAM).
    
2. **Tráfico de red:** Configuración de Firewalls virtuales y reglas de entrada/salida.
    
3. **Datos de las aplicaciones:** Cifrado y protección de la información.
    

### Desafíos y Herramientas de Seguridad

**Herramientas Nativas del Proveedor:**

- La mayoría de los proveedores (como AWS o Azure) ofrecen herramientas de seguridad básicas.
    
- **Limitación:** Suelen ofrecer funciones básicas y protegen solo su propia plataforma, no la de otros proveedores.
    

**Entorno de Nubes Múltiples (Multi-Cloud) e Híbrido:**

- Muchas organizaciones no usan una sola nube, sino un entorno híbrido (Nube + On-Premise) o Multi-Nube (usan AWS y Azure al mismo tiempo).
    
- **Problema de Escala:** La complejidad de la seguridad aumenta geométricamente con cada nuevo proveedor que se añade (Proveedor A + Proveedor B + SaaS).
    

**Desafíos Operativos:**

1. **Escasez de Talento:** Es difícil encontrar personal de seguridad altamente capacitado que sepa manejar todas las nubes.
    
2. **Falta de Integración:** Es complicado operar múltiples entornos de seguridad desconectados (tener que mirar 3 consolas diferentes para ver una alerta).