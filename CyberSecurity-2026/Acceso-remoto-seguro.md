
### **¿Qué es el acceso remoto seguro?**

- **Definición:** El acceso remoto seguro es una combinación de métodos y tecnologías de seguridad que permiten a entidades finales externas conectarse a las redes sin comprometer los activos digitales ni exponer las redes a partes no autorizadas.
    
- **Lugares de teletrabajo:** Casa, hotel, cafetería, sucursal, campus, aeropuerto, estación de tren, etc.
    
- **Contexto:**
    
    - Aumento del teletrabajo.
        
    - Los actores maliciosos aprovechan el acceso remoto no seguro.
        
    - Los métodos para salvaguardar las conexiones remotas se han vuelto más seguros a través del tiempo.
        

---

### **Protección del acceso remoto: Funciones Clave**

1. **Privacidad de datos:** Un estado en el que la información se oculta al público y solo está disponible para personas selectas.
    
2. **Integridad de datos:** La exactitud y coherencia de los datos a lo largo de su ciclo de vida.
    
3. **Autenticación:** Proceso de verificación de la identidad de una persona o cosa.
    
4. **Autorización:** La función de especificar los derechos de acceso a los recursos.
    
5. **Registro (Accounting):** El registro y seguimiento de las actividades de los agentes en una red informática.
    

- **Nota:** Las tres últimas funciones se expresan comúnmente como **AAA** (Authentication, Authorization, Accounting).
    

---

### **Métodos comunes de acceso seguro**

- **VPN IPsec:** Red privada virtual de seguridad del protocolo de Internet.
    
- **VPN SSL:** Red privada virtual de capa de conexión segura.
    
- **ZTNA:** Acceso a la red de confianza cero (que incorpora el principio de confianza cero).
    

---

### **Comparación: ZTNA vs VPN**

**VPN de acceso remoto seguro:**

- **Casos de uso:** Acceso remoto seguro, Sitio a sitio.
    
- **Componentes principales:** Cliente, Servidor, Protocolos.
    

**Acceso a la red de confianza cero (ZTNA):**

- **Características:** Principio de confianza cero, Seguridad mejorada.
    

---

### **Tabla Comparativa Detallada: IPsec VPN vs SSL VPN vs ZTNA**

|**Característica**|**IPsec VPN**|**SSL VPN**|**ZTNA**|
|---|---|---|---|
|**Nivel del modelo OSI que protege**|Red|Transporte a la aplicación|Transporte a la aplicación|
|**Implementación en el cliente**|Aplicación de cliente de VPN|Navegador web o una aplicación de cliente de la SSL VPN|Cliente de ZTNA|
|**Control de acceso tras la sesión**|No hay ningún control de acceso después de que el usuario establece una sesión de VPN|Cierto control de acceso granular (conecta a usuarios a aplicaciones/servicios específicos)|Control de acceso granular a aplicaciones específicas. Se basa en funciones de usuario, políticas y verificaciones continuas|
|**Autenticación**|Entre la aplicación de cliente de la VPN y la red privada|Mediante solicitud de inicio de sesión del navegador tras establecer sesión SSL|Usuario y dispositivo se autentican y verifican cada vez que se solicita acceso a una aplicación|
|**Tipo de túnel**|Solo túnel IPsec|Se basa en la sesión o túnel|Se basa únicamente en la sesión|
|**Categoría**|Estándar de la industria|Específica del proveedor|Específica del proveedor|
|**Configuración**|Requiere instalación. Flexible (malla/estrella). Para clientes o puertas de enlace pares.|No requiere instalación (si es tipo web). Configuración más simple (solo cliente a FortiGate, sin ajustes de usuario).|Requiere instalación de cliente ZTNA. Configuración más simple (solo cliente a FortiGate, sin ajustes de usuario).|


---

# VPN SSL

Definición:  Tecnologia que admite una sesion cifrada entre dos dispositivos informaticos, **proporciona seguridad desde la capa de transporte** del modelo OSI al mismo tiempo **comunica datos en la capa de app**. Mientras que la **info se intercabia en la capa de app** entre el cliente y el servidor, la **info se encapsula en la capa de transporte** 

Requiere un cliente y un servidor, donde el clinete suele ser un servidor web, esta provve **privacidad, integridad, autenticacion y antirepeticion(evita manipulacion)**.

