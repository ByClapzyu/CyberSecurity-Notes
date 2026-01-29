
[Administración de red seguridad centralizada](#administración_de_red_seguridad_centralizada)

[Arquitectura Data Fabric](#arquitectura_data_fabric)

[Segmentación de Red](#segmentación_de_red)

[Switching y Puertos Seguros](#switching_y_puertos_seguros)


---
# administración_de_red_seguridad_centralizada

**Definición:** Consiste en recopilar datos relacionados con la seguridad de diversos dispositivos en una sola ubicación central para su gestión, control, operación y diagnóstico.

**Protocolos Clave:**

- **SNMP (Simple Network Management Protocol):** Recolecta y organiza información sobre dispositivos administrados.
    
- **API (Application Programming Interface):** Interfaz de software que permite a dos dispositivos comunicarse entre sí automáticamente.
    

# arquitectura_data_fabric

Su objetivo es monitorear y administrar los datos y aplicaciones donde quiera que estén (nube o local), sin perder la gobernanza centralizada.

- **Uso de IA:** Automatiza tareas repetitivas y ofrece recomendaciones inteligentes.
    

### fortinet security fabric

Es la implementación de este concepto por Fortinet.

- **Ecosistema Abierto:** Se integra con otros mediante API y Conectores Fabric.
    
- **Centro de Administración:** Visibilidad de extremo a extremo (NOC/SOC).
    
- **Componentes Clave:**
    
    - **Acceso de Confianza Cero:** Ajustes dinámicos de acceso.
        
    - **FortiGuard:** Velocidad, coordinación y detección de amenazas en tiempo real.
        

**Ventajas:**

- **Amplia Visibilidad:** Evita puntos ciegos, reduce el tiempo de respuesta a incidentes y minimiza interrupciones.
    
- **Integración:** Definición centralizada de configuraciones y orquestación de políticas.
    
- **Eficiencia:** Reducción de tareas repetitivas/manuales y mantenimiento más fácil.
    
- **Cumplimiento:** Auditorías más sencillas y previsión de capacidad/rendimiento clara.
    

---

# segmentación_de_red

**Concepto:** Divide la red en segmentos más pequeños y aislados (ej. por departamentos como Finanzas, RRHH).

- **DMZ (Zona Desmilitarizada):** Segmento especial expuesto a Internet solo para servidores necesarios (Web, Correo), protegiendo la red interna.
    
- **Tráfico Vertical (Norte-Sur):** Tráfico que entra o sale de la red (hacia Internet).
    
- **Tráfico Horizontal (Este-Oeste):** Tráfico interno entre servidores o dispositivos de la misma red.
    

### tipos de segmentación

**A. Segmentación Lógica (Pequeña y Manejable)**

- **Capa OSI:** Enlace de Datos (Capa 2).
    
- **VLAN (Redes de Área Local Virtuales):** Los dispositivos se comunican entre sí como si estuvieran en el mismo cable, aunque estén físicamente separados, gracias a los switches.
    

**B. Segmentación Física**

- **Capa OSI:** Red (Capa 3).
    
- **Herramientas:** ACLs (Listas de Control de Acceso), Enrutadores y Políticas de Firewall. Es una separación dura y física.
    

### cómo segmentar una red moderna

1. **Capa de Aplicación:** Segmentación basada en el servicio (Web, Base de Datos).
    
2. **SD-WAN:** Permite la comunicación a través de Internet mediante túneles superpuestos cifrados (Overlay).
    
    - _Nota:_ Una **Red Superpuesta (Overlay)** es una red virtual construida sobre la infraestructura física subyacente (Underlay).
        

**Administración de Segmento de Red Segura:**

- **Servidor Puente (Jump Server):** Un punto único y controlado para acceder a zonas seguras. Mejora el control de acceso y monitoreo.
    
- **Host Bastión:** Servidor endurecido diseñado para resistir ataques, que proporciona acceso seguro desde una red externa a una aplicación privada.
    

**Ventajas de Segmentar:**

- **Seguridad:** Limita los ataques a un segmento específico (evita movimiento lateral).
    
- **Rendimiento:** Minimiza la congestión y reduce el número de difusiones (broadcasts).
    
- **Protección:** Mayor seguridad para dispositivos vulnerables y cumplimiento normativo más fácil (reduce el alcance de la auditoría).
    

---

## switching_y_puertos_seguros

La seguridad en la Capa 2 (Enlace de Datos) es crítica porque es donde se conectan los usuarios.

**Conceptos Básicos:**

- **Función del Switch:** Asigna paquetes a las VLAN basándose en la dirección MAC de origen.
    
- **Tabla CAM (Content Addressable Memory):** Es la "memoria" del switch. Muestra la relación: `Puerto Nº -> Dirección MAC -> VLAN`.
    

### amenazas y ataques comunes en capa 2

**1. Inundación de MAC (MAC Flooding)**

- **Objetivo:** Llenar la tabla CAM del switch con direcciones falsas.
    
- **Efecto:** El switch entra en modo "Fail Open" (actúa como un Hub) y reenvía el tráfico por todos los puertos, permitiendo al atacante espiar datos (fuga de información) y causando Denegación de Servicio (DoS).
    
- **Síntoma:** Un mismo puerto asociado a miles de MACs distintas.
    

**2. Spoofing de MAC**

- **Definición:** El atacante suplanta (falsifica) su dirección MAC por la de un dispositivo autorizado para saltarse los filtros de seguridad.
    

### definiciones de tramas y control

- **Trama de Difusión (Broadcast):** Destino `FF:FF:FF:FF:FF:FF`. Se envía a todos.
    
- **Trama de Unidifusión Desconocida:** El switch no conoce la MAC destino, así que la envía a todos (inundación) para ver quién responde.
    
- **Control de Tormentas (Storm Control):** Configura un umbral límite para evitar que estas tramas inunden y colapsen la red.
    

### medidas de seguridad para switches

- **Seguridad de Puertos (Port Security):** Limitar el número de direcciones MAC permitidas por puerto.
    
- **Direcciones Sticky MAC:** El switch "aprende" la MAC del primer dispositivo que se conecta y la guarda en memoria. Si se conecta otro, bloquea el puerto.
    
- **MAC Estáticas:** Configurar manualmente qué MAC va en qué puerto (muy seguro, poco escalable).
    
- **Autenticación 802.1X:** Estándar de oro. Exige usuario/contraseña antes de activar el puerto del switch.
    
- **Reflejo de Puerto (Port Mirroring):** Copiar el tráfico de un puerto a otro para análisis (IDS/Sniffer).
    
- **Protección Física:** Encerrar los switches en armarios con llave.
    

---

##  protocolos de seguridad

Es la evolución de los protocolos de texto plano a protocolos cifrados para garantizar confidencialidad, integridad y autenticación.

|**Tipo de Comunicación**|**Protocolo Inseguro (Texto Plano)**|**Protocolo Seguro (Cifrado)**|**Características de Seguridad**|
|---|---|---|---|
|**Correo**|SMTP / MIME|**S/MIME**|Autenticación, No repudio, Integridad, Confidencialidad extremo a extremo.|
|**Web**|HTTP|**HTTPS (TLS)**|Cifrado de tráfico web.|
|**Control Remoto**|Telnet|**SSH**|Verificación extremo a extremo, Intercambio Diffie-Hellman (DH), Código de Autenticación de Mensajes (MAC).|
|**Acceso Remoto (VPN)**|L2TP (Solo túnel)|**IPsec**|Cifrado robusto, autenticación e integridad de paquetes.|

## amenazas comunes y ataques dos

**Motivaciones:** Políticas, financieras, represalias.

### ataques de inundación - volumétricos

El objetivo es saturar el ancho de banda o los recursos del dispositivo.

1. **Ataque Smurf:** Falsifica la IP de la víctima y envía un Ping (ICMP) a una dirección de difusión. Toda la red responde a la víctima, colapsándola.
    
2. **Ataque Fraggle:** Igual que Smurf, pero usa paquetes UDP (puerto 7 y 19) en lugar de ICMP.
    
3. **Inundación SYN:** Explota el "apretón de manos" TCP (3-way handshake). El atacante envía muchos `SYN` pero nunca responde con `ACK`. El servidor se queda esperando (conexiones medio abiertas) y agota su memoria.
    

### ataques por fragmentación y malformación

Envían paquetes "rotos" que el dispositivo no sabe cómo procesar.

1. **Ping de la Muerte:** Envía paquetes ICMP más grandes de lo permitido (fragmentados). Al reensamblarse, desbordan el búfer y tiran el sistema.
    
2. **Ataque de Goteo (Teardrop):** Envía fragmentos con cargas superpuestas (offset incorrecto). El sistema operativo no puede rearmarlos y colapsa (Crash).
    
3. **Christmas Tree (XMAS):** Envía un paquete TCP con todas las banderas encendidas (FIN, URG, PSH). Consume muchos recursos de procesamiento.
    

### ataques destructivos

- **PDoS (Phashing):** Daña el hardware permanentemente corrompiendo el firmware. Requiere reemplazo físico del equipo.
    
- **Bomba Fork:** Se replica a sí mismo en procesos secundarios hasta agotar la CPU/RAM del servidor.
    

---

##  medidas de prevención y endurecimiento

**Relación Ataque - Prevención:**

|**Tipo de Ataque**|**Método de Prevención**|
|---|---|
|**Paquetes Malformados** (Ping muerte, Teardrop)|**Detección de anomalía en paquete:** El firewall revisa que el paquete cumpla los estándares antes de dejarlo pasar.|
|**Agotamiento de Recursos** (Bombas Fork)|**Limitación de procesos:** Restringir cuántos procesos puede abrir un solo usuario.|
|**Amplificación/Reflexión** (Smurf, Fraggle)|**Configuración de Router:** Evitar el reenvío de paquetes de difusión dirigida.|
|**Volumétricos** (Inundaciones)|**Sensores DoS / Análisis de Comportamiento:** Detectar picos inusuales de tráfico.|
**Buenas Prácticas de Endurecimiento:**

1. **Cerrar puertos innecesarios:** Usar escáneres como Nmap para ver qué está abierto y cerrar lo que no se usa en el Firewall.
    
2. **Corregir Vulnerabilidades:** Realizar pruebas de penetración (Pentesting) y aplicar parches de seguridad al día.
    
3. **Segmentación:** Para que una infección no se propague.
    
4. **Zero Trust:** Nunca confiar, siempre verificar.