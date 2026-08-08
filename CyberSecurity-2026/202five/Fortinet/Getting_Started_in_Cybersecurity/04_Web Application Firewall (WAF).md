
## Definición y Diferencia Clave

**Definición:** Dispositivo o software diseñado específicamente para monitorear, filtrar y bloquear el tráfico **HTTP/HTTPS** hacia y desde una aplicación web.

**WAF vs. Firewall de Borde (Network Firewall):**

- **Firewall de Borde (FortiGate):** Actúa como puerta de enlace entre la LAN e Internet. Se centra en la red (IPs, Puertos).
    
- **WAF (FortiWeb):** Se centra en el **contenido** de la aplicación web. "Lee" el lenguaje de la web (HTML, SQL, JSON) para entender si una petición es válida o un ataque.
    

**¿Por qué es vital?** Porque pasamos todo el tiempo interactuando con apps web. El WAF detiene ataques específicos que el firewall normal no ve, como:

- Inyección SQL.
    
- Scripting entre sitios (XSS).
    
- Inclusión de archivos.
    
- Configuraciones de seguridad incorrectas.
    

---

## 2. El Antecesor: Firewall de Aplicaciones (Años 90)

Antes del WAF moderno, existían los "Application Firewalls". Aunque eran basados en red, podían controlar aplicaciones específicas.

**Glosario de Protocolos Antiguos (Lo que pediste explicar):**

1. **FTP (File Transfer Protocol):**
    
    - Es el protocolo estándar para enviar archivos de una computadora a un servidor.
        
    - _El problema:_ En los 90s, el FTP básico enviaba todo (incluyendo contraseñas) en texto plano, sin cifrar.
        
2. **Shell Remoto (RSH - Remote Shell):**
    
    - Es una herramienta de línea de comandos antigua que permitía a un usuario ejecutar comandos en otra computadora a través de la red.
        
    - _El problema:_ Al igual que FTP, era muy inseguro y fácil de interceptar. Fue el "abuelo" inseguro del actual SSH.
        

---

## 3. Evolución del WAF (Historia)

El WAF tuvo que evolucionar porque los hackers cambiaron de estrategia.

###  Primera Generación: Firmas y Listas (El inicio)

- **Enfoque:** Diseñado para HTTP (puertos 80/443).
    
- **Método:** Usaba **Listas de Bloqueo** y atributos basados en **Firmas** (buscaba patrones de texto exactos conocidos como "ataque").
    
- **Limitación:**
    
    - No podía confiar en métodos tradicionales de IPs/Puertos.
        
    - **El Gran Fallo:** Generaba demasiados **Falsos Positivos** (alertas de ataque que en realidad eran tráfico legítimo), saturando al equipo de TI.
        

### Segunda Generación: Aprendizaje y Heurística

- **Mejora:** Se volvieron más inteligentes. Incluían un elemento de aprendizaje.
    
- **Método:**
    
    - **Línea Base (Baselining):** Estudiaban el comportamiento normal de la app para saber qué era "raro".
        
    - **Heurística:** Podían detectar variantes de firmas conocidas (ataques que cambiaban ligeramente).
        
    - **Monitoreo de Sesiones:** Seguían al usuario durante toda su visita.
        
- **Desventaja Crítica:** No podían seguir el ritmo de las vulnerabilidades nuevas. **Fallaban contra ataques de Día Cero (Zero-Day)**.
    

###  Tercera Generación (Actual): Machine Learning (ML)

- **La Solución Lógica:** Integración de **Aprendizaje Automático (ML)**.
    
- **Capacidades:**
    
    - Defensa contra DDoS.
        
    - Reputación IP.
        
    - Antivirus y DLP (Prevención de Pérdida de Datos).
        
    - Supervisión continua de tráfico HTTP para detener acciones sospechosas sin firmas previas.
        

---

## 4. Capacidades Modernas y Evolucionadas

El WAF moderno (como FortiWeb) no trabaja solo; se integra en la red.

1. **Identificación de Usuario:** No solo ve una IP, ve "quién" es, correlaciona sus acciones con sus permisos y bloquea si intenta hacer algo fuera de su función (ej. un usuario de ventas intentando acceder a la base de datos de admin).
    
2. **Colaboración (Security Fabric):** Comparte info con otros firewalls y sandboxes.
    
3. **Defensa Zero-Day:** Si encuentra un archivo sospechoso, lo manda a cuarentena en el **Sandbox**, obtiene la firma y la comparte con el resto de la red.
    
4. **Inteligencia de Amenazas:** Carga los nuevos descubrimientos a la nube (FortiGuard) para proteger a otras empresas globalmente.
    

---

## Producto Fortinet: FortiWeb

Para el examen, asocia **WAF** con **FortiWeb**.

- **FortiWeb** protege aplicaciones web, APIs y bases de datos contra ataques OWASP Top-10 (como SQL Injection).
    
- Utiliza **Machine Learning** de dos capas para eliminar falsos positivos.