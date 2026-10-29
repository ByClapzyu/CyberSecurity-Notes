## Network Access Control (NAC)

## Definición y Concepto

**Definición Simple:** Sistema o máquina virtual que controla el acceso a una red. Categoriza automáticamente los dispositivos, evalúa su cumplimiento de políticas (si tienen antivirus, si están actualizados) y decide si pueden entrar y hasta dónde pueden llegar.

**Analogía del Mundo Real:** Imagina el **Control de Pasaportes/Aduana de un Aeropuerto**.

- No importa quién seas, debes mostrar tu identificación (Autenticación).
    
- El agente revisa si tienes visa válida y si no traes contrabando (Postura de seguridad/Cumplimiento).
    
- Si todo está bien, te deja pasar, pero solo a la zona de turistas, no a la pista de aterrizaje (Segmentación).

## Los Inicios: El Estándar IEEE 802.1X

Antes del NAC moderno, usábamos el protocolo **802.1X** para autenticar cables y Wi-Fi.

**Los 3 Jugadores del 802.1X (Pregunta de Examen):**

1. **Suplicante (Cliente):** El dispositivo que quiere entrar (Laptop, Celular). Debe proporcionar credenciales.
    
2. **Autenticador:** El "portero" que bloquea o abre la puerta. Generalmente es un **Switch** o un **Access Point (AP)**.
    
3. **Servidor de Autenticación:** El "cerebro" que tiene la base de datos de usuarios (generalmente un servidor **RADIUS**). Dice "Sí, pasa" o "No, bloquéalo".

## Retos Emergentes: ¿Por qué evolucionó el NAC?

El 802.1X funcionaba bien para PCs corporativas, pero falló con las nuevas tendencias:

### A. BYOD (Bring Your Own Device)

- Los empleados traen sus propios celulares/laptops. El departamento de TI (MIS) no controla esos equipos, pero debe darles acceso seguro.
    

### B. IoT (Internet of Things) - El Gran Dolor de Cabeza

- Cámaras, impresoras, sensores, termostatos.
    
- **El Problema:** Son dispositivos "sin cabeza" (Headless). No tienen pantalla ni teclado para poner usuario/contraseña, y a menudo tienen poca CPU/RAM, por lo que **no se les puede instalar software de seguridad (agentes)**.
    
- **Superficie de Ataque:** Si hackean una cámara (que suele tener seguridad débil o contraseñas por defecto imposibles de cambiar), pueden usarla para saltar al servidor de la empresa.

## ¿Cómo funciona el NAC Moderno? (El Proceso)

Cuando conectas FortiNAC, el proceso sigue estos pasos lógicos:

### Paso 1: Visibilidad y Perfilado (Profiling)

- **Regla de Oro:** "No puedes proteger lo que no puedes ver".
    
- NAC escanea la red y crea un **inventario** en tiempo real.
    
- **Identificación:** Como los IoT no te dicen quiénes son, NAC analiza su comportamiento o huella digital para decir: _"Esto es una Cámara IP Axis modelo X"_.
    

### Paso 2: Segmentación Dinámica (Micro-segmentación)

- Una vez identificado el dispositivo, NAC le asigna un perfil y lo manda a su lugar correcto.
    
- **Caso de Uso (Cámara vs. Finanzas):**
    
    - NAC detecta una **Cámara IP**.
        
    - Automáticamente la mueve a la **VLAN de Video**.
        
    - Configura el Firewall para que esa cámara hable con el **NVR (Grabador)**, pero **BLOQUEA** su acceso al **Servidor de Finanzas**.
        
    - _Resultado:_ Si hackean la cámara, el malware se queda atrapado en la VLAN de video y no roba los datos bancarios.
        

### Paso 3: Respuesta Automatizada

- NAC se integra con el SOC (Security Operations Center).
    
- Si un dispositivo aprobado empieza a comportarse raro (ej. la impresora intenta descargar archivos de Rusia), NAC lo aísla o desconecta automáticamente.

## Funcionalidades Clave

- **Acceso de Invitados (Guest Management):**
    
    - Portal Cautivo (página web donde aceptas términos o pones un código) para visitas.
        
    - Permite autoservicio sin molestar al equipo de TI.
        
- **Verificación de Postura:**
    
    - Antes de dejar entrar a una Laptop, revisa: ¿Tiene el antivirus activo? ¿Tiene los parches de Windows? Si no, la manda a una "VLAN de Cuarentena" para que se actualice.

### Importancia y Beneficios

| **Beneficio**                | **Descripción**                                                                   |
| ---------------------------- | --------------------------------------------------------------------------------- |
| **Visibilidad (Inventario)** | Sirve como un inventario permanente y vivo de todos los endpoints conectados.     |
| **Seguridad Zero Trust**     | "Nunca confiar, siempre verificar". Autentica todo antes de conectar.             |
| **Ahorro de Datos y TI**     | Automatiza procesos que antes eran manuales (mover puertos de VLAN).              |
| **Experiencia de Usuario**   | Conexión sin fricción para usuarios autorizados; portales fáciles para invitados. |

## FortiNac

- **Características:** Arquitectura centralizada (ideal para redes grandes y múltiples sitios), visibilidad total de IoT, y respuesta automatizada ante incidentes.
