# Módulo: Monitoreo y Endurecimiento de Endpoints

##  Estrategias de Protección (Los 4 Pilares)

Para proteger los dispositivos conectados a la red, se deben aplicar controles en cuatro áreas clave:

**A. Controles Administrativos (Políticas Humanas)**

- **Contraseñas:** Gestión de claves robustas.
    
- **Restricciones de usuario:** Limitar lo que el usuario puede hacer.
    
- **Principio de Privilegio Mínimo (PoLP):** Otorgar solo los permisos estrictamente necesarios para la función laboral.
    

**B. Mantenimiento del Endpoint (Higiene Digital)**

- **Actualizaciones y Parches:** Automatizar la instalación de correcciones de seguridad.
    
- **Revisiones de política:** Auditorías periódicas.
    
- **Copias de seguridad:** Respaldos para recuperación ante desastres.
    

**C. Protección Local (Endurecimiento Técnico)**

- **Endurecimiento del OS y arranque:** Asegurar la configuración del sistema operativo.
    
- **Administración de arranque:** Proteger BIOS/UEFI (Secure Boot).
    
- **Seguridad y cifrado de disco:** Proteger los datos en reposo (ej. BitLocker).
    
- **Prevención de Pérdida de Datos (DLP):** Evitar la extracción de información sensible.
    

**D. Monitoreo (Vigilancia Activa)**

- Plataforma de Protección de Endpoints (**EPP**).
    
- Sistemas de Detección de Intrusiones (**IDS**).
    
- Detección y Respuesta de Endpoints (**EDR**).
    

---

##  Soluciones de Software de Endpoint (EPP vs. EDR)

Estas herramientas ayudan a administrar y proteger diversos tipos de endpoints frente a ciberamenazas.

###  Plataforma de Protección de Endpoints (EPP)

Es la primera línea de defensa. Se enfoca en la **prevención** y el mantenimiento.

**Funciones Principales:**

- **Verificación de Salud:** Revisa versiones de software y firmware para asegurar que estén actualizados.
    
- **Escaneo de Malware:** Busca virus y amenazas en el sistema local (Antivirus tradicional).
    
- **Cumplimiento:** Aplica políticas de seguridad corporativas (como DLP).
    

**Beneficios:**

- Actúa como medida defensiva básica contra ataques conocidos.
    
- Ayuda a mantener actualizaciones uniformes en toda la empresa.
    
- Proporciona visibilidad básica de los sistemas.
    

###  Detección y Respuesta de Endpoints (EDR)

Es la capa avanzada. Se enfoca en el **comportamiento** y la **respuesta** ante amenazas complejas que evadieron al EPP.

**Conceptos Clave:**

- **Indicador de Compromiso (IOC):** Es cualquier evidencia digital (conexión extraña, archivo modificado, comportamiento anómalo) que sugiere que el sistema ha sido vulnerado.
    
- **Objetivo:** Identificar y detener amenazas avanzadas como **Ransomware** y ataques de **Día Cero** (Zero-Day).
    

**Capacidades del EDR:**

- **Predicción:** Reconoce archivos y programas sospechosos antes de que actúen.
    
- **Alerta y Bloqueo:** Envía alertas a otros endpoints y bloquea comportamientos sospechosos en la red.
    
- **Cuarentena y Análisis:** Aíslan los sistemas comprometidos para evitar la propagación.
    
- **Respuesta Inmediata:** Actúa automáticamente contra ataques no identificados previamente.
    

### Resumen: Sinergia EPP + EDR

- **Visibilidad Descendente:** Los administradores pueden ver la condición de seguridad de todos los dispositivos.
    
- **Automatización:** El EDR permite la **contención de amenazas** automatizada (ej. si el firewall detecta algo, le dice al EDR que desconecte la PC infectada).
    

---

##  Protección de Endpoints Desconocidos y BYOD

La red debe distinguir entre dispositivos corporativos y externos.

**Clasificación de Redes:**

- Red Establecida (Corporativa).
    
- Red Aislada (Invitados/Cuarentena).
    
- Dispositivos BYOD (Trae tu propio dispositivo).
    

### Gestión de Endpoints Conocidos

Son los dispositivos propiedad de la empresa.

- **Registro:** Se identifican mediante:
    
    - Nombre de host.
        
    - Número de serie.
        
    - Dirección MAC o IP estática.
        
- **Acción:** Se les instala software de seguridad obligatorio (Agente EPP/EDR) y se les aplica el Principio de Privilegio Mínimo.
    

### Gestión de Dispositivos Desconocidos

Cualquier dispositivo que intente conectarse y no esté en la lista de aprobados.

- **Política de Aislamiento:** Deben ser aislados en una red separada hasta que se verifiquen, autoricen y etiqueten.
    
- **Registro Obligatorio:** Se obliga al usuario a registrar el dispositivo antes de darle acceso.
    
- **Ejecución (Enforcement):** Los dispositivos de red (Puntos de Acceso, Switches, Routers, Firewalls) se configuran para **deshabilitar el acceso** a cualquier dispositivo desconocido, evitando que los atacantes introduzcan hardware no autorizado en la red interna.