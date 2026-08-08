## El Panorama de Amenazas

El correo electrónico es el vector de ataque más común utilizado por los actores maliciosos para distribuir desinformación, estafas y fraudes.

**Conceptos Básicos:**

- **Correo no deseado (Spam):** Correo electrónico no solicitado e irrelevante enviado masivamente a muchos destinatarios.
    
- **Suplantación de identidad (Phishing):** Ataque de ingeniería social que utiliza el correo electrónico redirigido a un grupo amplio e indiscriminado de personas para engañarlas.
    

## . Puerta de Enlace de Correo Segura (SEG)

**Definición:** Una Puerta de Enlace de Correo Segura (SEG - Secure Email Gateway) es un dispositivo o software que monitoriza los correos electrónicos que entran y salen. Actúa como un filtro avanzado (MTA - Mail Transfer Agent) para bloquear amenazas antes de que lleguen al usuario.

**Funciones Principales:**

1. **Filtro de Contenido:**
    
    - Controla y maneja los tipos de contenido que se pueden acceder o compartir.
        
    - **Tecnologías:** Coincidencia de palabras clave, expresiones regulares, inspección profunda de paquetes y análisis contextual.
        
2. **Prevención de Pérdida de Datos (DLP):**
    
    - Evita la fuga no autorizada o accidental de información confidencial (tarjetas de crédito, datos personales) hacia el exterior de la organización.
        
3. **Filtro de Malware:**
    
    - Escanea archivos adjuntos y enlaces dentro del correo para detectar virus o software malicioso.
        
4. **Cifrado (IBE - Identity Based Encryption):**
    
    - Cifra el correo electrónico para asegurar que solo el destinatario legítimo pueda leerlo, protegiendo la confidencialidad en tránsito.
        
5. **Autenticación y Verificación de Identidad:**
    
    - Admite varios métodos para verificar quién envía el correo y evitar el Spoofing (falsificación).
        

## . Profundizando en el Filtro de Spam (Antispam)

Su objetivo es administrar el correo y eliminar el contenido nocivo, reduciendo la basura en la bandeja de entrada.

**Características que analiza el filtro (Indicadores):**

- Direcciones de remitentes sospechosas.
    
- Uso excesivo de ciertas palabras clave (ej: "Gratis", "Urgente", "Lotería").
    
- Patrones conocidos de spam.
    
- Direcciones IP con mala reputación (IP Reputation).
    

**Tecnologías de Filtrado:**

- **Listas de denegación (Blacklists):** Bloquea remitentes conocidos por ser maliciosos.
    
- **Listas de aprobación (Whitelists):** Permite siempre el paso a remitentes confiables.
    
- **Filtros Bayesianos:** Análisis estadístico que "aprende" a calcular la probabilidad de que un mensaje sea spam basándose en palabras y patrones previos.
    
- **Algoritmos de aprendizaje automático:** IA que detecta nuevas tendencias de spam sin necesidad de firmas manuales.
    

## . Protocolos de Autenticación de Correo (Crítico para Examen)

Para evitar que los atacantes se hagan pasar por tu dominio (Spoofing), se utilizan tres estándares clave que trabajan juntos.

**1. SPF (Sender Policy Framework):**

- **Función:** Verifica la dirección IP del servidor de envío.
    
- **Cómo funciona:** El dueño del dominio publica una lista en sus DNS diciendo: "Solo estas IPs tienen permiso para enviar correos a nombre de mi empresa". Si el correo viene de otra IP, falla.
    

**2. DKIM (DomainKeys Identified Mail):**

- **Función:** Asegura la integridad y autenticidad mediante criptografía.
    
- **Cómo funciona:** Añade una firma digital al correo electrónico usando una clave privada. El receptor verifica la firma con la clave pública del dominio. Confirma que el correo no fue modificado en el camino.
    

**3. DMARC (Domain-based Message Authentication, Reporting, and Conformance):**

- **Función:** Es el "Jefe" o el manual de instrucciones. Se basa en SPF y DKIM.
    
- **Cómo funciona:** Permite al remitente especificar una política que le dice al receptor qué hacer si un correo falla las pruebas de SPF o DKIM (ej: "Si falla, mándalo a cuarentena" o "recházalo"). También envía informes al dueño del dominio sobre quién está enviando correos a su nombre.
    

## . Evolución: SEG de Nueva Generación

Las soluciones SEG modernas ya no trabajan solas.

- **Integración con Sandbox:** Si un adjunto es desconocido, el SEG lo envía al Sandbox para detonarlo y ver si es un Zero-Day.
    
- **Integración con Firewall:** Comparten inteligencia de amenazas.
    
- **Aprendizaje Automático (ML):** Mejora la detección de ataques sofisticados como el BEC (Business Email Compromise).
    

---

### Producto Fortinet

 **Secure Email Gateway (SEG)** con **FortiMail**.

- Protege el correo electrónico contra spam, phishing, malware, ataques de compromiso de correo empresarial (BEC) y pérdida de datos (DLP).
    
- Ofrece tres modos de implementación flexibles: **Pasarela (Gateway)**, **Transparente** y **Servidor**.
    
- Utiliza **Cifrado Basado en Identidad (IBE)** para enviar mensajes seguros utilizando la dirección de correo como clave pública, sin gestión compleja de certificados.