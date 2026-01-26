## Contexto y Definición

**La Necesidad Actual:** Las organizaciones requieren que sus usuarios tengan acceso inmediato, continuo y seguro a los recursos (en la red o la nube) desde cualquier ubicación, dispositivo y momento. El modelo tradicional de "todo pasa por la oficina central" ya no funciona.

**La Fórmula de SASE:** Es la convergencia de dos mundos: **Red como Servicio (SD-WAN) + Seguridad como Servicio (SSE)**

**Definición:** SASE se suministra a través de la nube como un modelo de consumo "como servicio". Su objetivo es apoyar el acceso seguro a las redes empresariales distribuidas e híbridas actuales.

##  Arquitectura y Componentes

El flujo de SASE conecta fuentes de tráfico con destinos de tráfico a través de un núcleo seguro en la nube.

**A. Fuentes de Tráfico (Origen):**

- Usuarios en Casa.
    
- Usuarios en Sucursales.
    
- Dispositivos móviles/roaming.
    

**B. Núcleo SASE (El Cerebro):** Se compone de dos pilares:

1. **SD-WAN:** Maneja la conectividad y el enrutamiento inteligente.
    
2. **SSE (Borde de Servicio de Seguridad):** Maneja la seguridad. Incluye:
    
    - FWaaS (Firewall como servicio).
        
    - SWG (Secure Web Gateway).
        
    - CASB (Cloud Access Security Broker).
        
    - ZTNA (Zero Trust Network Access).
        

**C. Destinos del Tráfico:**

- Sede Central / Centro de Datos (On-premise).
    
- Aplicaciones SaaS (Office 365, Salesforce).
    
- Nube Pública (AWS, Azure).
    

##  Ventajas de Implementar SASE

1. **Seguridad Flexible y Coherente:**
    
    - Reduce la superficie de ataque y el riesgo de movimiento lateral utilizando ZTNA y DLP (Prevención de Pérdida de Datos).
        
    - Asegura el acceso sin importar la ubicación del usuario.
        
2. **Menores Costos y Complejidad de TI:**
    
    - **Consolidación:** Combina múltiples soluciones puntuales en un solo servicio.
        
    - Reduce la necesidad de gestionar varios proveedores, ahorrando dinero y recursos de integración.
        
3. **Experiencia del Usuario sin Interrupciones:**
    
    - Reduce la latencia al procesar el tráfico en una "Red de Borde Global" (PoPs) lo más cerca posible del usuario, en lugar de enviar todo el tráfico de vuelta al centro de datos central.
        

##  Componentes de la Solución Unificada (Definiciones Clave)

Para el examen, es vital distinguir qué hace cada componente dentro del stack de SASE.

**1. SD-WAN (La Conectividad)**

- Emplea una estructura superpuesta para dirigir inteligentemente el tráfico por las rutas más eficientes.
    
- Mejora la satisfacción del usuario y facilita la implementación rápida de nuevos servicios.
    

**2. Secure Web Gateway - SWG (Navegación Segura)**

- Protege a los usuarios de amenazas en línea durante la navegación general en Internet.
    
- **Funciones:** Filtra malware, evita pérdida de datos e impone políticas de uso de Internet.
    

**3. Firewall como Servicio - FWaaS (Seguridad de Red en la Nube)**

- Sustituye a los firewalls físicos ("cajas") por un firewall basado en la nube.
    
- **Capacidades:** Ofrece funciones de NGFW como IPS (Prevención de Intrusiones), inspección SSL, antimalware y Sandboxing.
    

**4. Cloud Access Security Broker - CASB (Seguridad para SaaS)**

- Es el "policía" entre el usuario y las aplicaciones en la nube (SaaS, IaaS, Nube Privada).
    
- **Funciones:** Evita fugas de datos, infecciones de malware y falta de visibilidad en aplicaciones como Office 365 o Salesforce.
    

**5. Zero Trust Network Access - ZTNA (Acceso a Apps Internas)**

- Proporciona acceso seguro específicamente a las **aplicaciones internas** (privadas) de la empresa.
    
- **Filosofía:** "Nunca confiar, siempre verificar". Cada intento de acceso es cuestionado.
    
- **Tecnologías:** Usa Autenticación Multifactor (MFA) y verificación de postura del dispositivo.
    

**6. Administración Centralizada (Panel Único)**

- Permite gestionar todas las funciones anteriores desde una sola consola.
    
- **Beneficio:** Garantiza políticas coherentes en toda la organización y agiliza el control de cambios y parches.
    

---

# Producto Fortinet: FortiSASE

**Definición:** Es la solución de Borde de Servicio de Acceso Seguro de Fortinet. Permite el acceso seguro a la web, la nube y las aplicaciones para una fuerza de trabajo híbrida.

**Puntos Clave para el Examen:**

- **Integral:** Fortinet presume ser el primer proveedor en ofrecer una solución SASE verdaderamente integral (Single-Vendor SASE).
    
- **Integración:** Une la conectividad SD-WAN (desde el FortiGate) con el borde de seguridad en la nube (SSE).
    
- **Componentes:** Incluye SWG, ZTNA, CASB de modo dual y FWaaS.