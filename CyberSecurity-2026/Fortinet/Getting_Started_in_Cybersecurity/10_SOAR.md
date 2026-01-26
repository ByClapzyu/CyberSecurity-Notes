## El Problema: La Fatiga de Alertas

El panorama de amenazas evoluciona constantemente, lo que obliga a las empresas a adquirir múltiples herramientas de seguridad. Esto genera un ciclo problemático:

- **Más herramientas:** Generan más alertas.
    
- **Mismo tiempo:** Los analistas tienen menos tiempo para investigar cada alerta individual.
    
- **Consecuencia:** Aumenta la probabilidad de cometer errores humanos. A esto se le llama **Fatiga de Alertas**.
    

**Soluciones posibles:**

1. Contratar más analistas (costoso y difícil).
    
2. Implementar **SOAR**.
    

##  ¿Qué es SOAR?

Es una solución que une las distintas herramientas de seguridad ("pilas de herramientas") extrayendo datos de todas ellas para centralizarlos.

**Beneficio Principal:** Reduce el cambio de contexto. Los analistas pueden realizar toda la investigación y respuesta desde una única interfaz (la de SOAR) sin tener que abrir 10 consolas diferentes.

##  Funcionalidades Clave

### A. Manuales de Estrategia (Playbooks)

Son el corazón de SOAR. Se definen como flujos de trabajo (similares a un diagrama de flujo) que pueden ejecutarse de forma automática o manual.

- **Estandarización:** Garantizan que siempre se sigan los pasos del Procedimiento Operativo Estándar (SOP).
    
- **Registro:** Guardan datos exactos sobre qué se hizo y quién lo hizo (auditoría).
    
- **Automatización:** Realizan tareas repetitivas como recopilar datos para un reporte o enviar correos de notificación.
    
- **Intervención Humana:** Pueden configurarse para hacer una **pausa** cuando se necesita supervisión (ejemplo: SOAR investiga todo, pero espera a que un humano presione "Aprobar" para bloquear un puerto en el firewall).
    

### B. Investigación Unificada

SOAR actúa como un banco de trabajo centralizado.

- **Inteligencia de Amenazas:** Comprueba automáticamente la reputación de IPs, archivos o dominios.
    
- **Consulta a SIEM:** Se conecta al Sistema de Gestión de Eventos e Información de Seguridad (SIEM) para buscar eventos relacionados con la alerta actual.
    

### C. Mitigación y Respuesta

Permite tomar acciones correctivas directamente en otros dispositivos sin salir de la consola SOAR.

- **Ejemplo 1:** Bloquear una dirección IP maliciosa en el Firewall.
    
- **Ejemplo 2:** Aislar un equipo infectado moviéndolo a una VLAN de cuarentena en el Switch.
    
- **Ejemplo 3:** Deshabilitar una cuenta de usuario comprometida en el Directorio Activo.
    

##  Comparativa: Proceso Manual vs. SOAR (Caso Phishing)

**Escenario:** Un usuario reporta un correo sospechoso de suplantación de identidad.

### Enfoque Manual (Lento y propenso a errores)

1. El analista dedica tiempo a investigar quién es el remitente.
    
2. Analiza el cuerpo del correo y los enlaces.
    
3. Si determina que es nocivo, debe investigar manualmente los registros (logs) del servidor de correo.
    
4. Busca quién más recibió el correo.
    
5. Investiga quién hizo clic en el enlace.
    
6. Elimina los correos uno por uno o mediante scripts manuales.
    

### Enfoque con Manual de Estrategia SOAR (Velocidad de máquina)

1. **Detección:** El proceso inicia automáticamente tan pronto como el correo es reportado.
    
2. **Filtrado:** SOAR analiza el correo. Si no es una amenaza, cierra el caso (evita falsos positivos).
    
3. **Investigación:** Si es sospechoso, consulta automáticamente al SIEM y bases de datos de inteligencia.
    
4. **Contención:** Elimina el correo malicioso de **todas** las bandejas de entrada de la organización instantáneamente.
    
5. **Comunicación:** Envía un correo automático a los destinatarios afectados avisando de la acción tomada y proporcionando consejos de seguridad.
    
6. **Resultado:** El analista solo recibe una notificación final o interviene solo si es estrictamente necesario, permitiéndole enfocarse en amenazas más críticas.
    

##  Beneficios Resumidos

- **Optimización:** Respuestas a velocidad de máquina.
    
- **Colaboración:** Permite asignar alertas a diferentes analistas o equipos según la fase del proceso.
    
- **Reducción de Errores:** Al automatizar lo repetitivo, se elimina el error humano por cansancio.
    
- **Autoridad Humana:** Mantiene el control humano en decisiones críticas mediante puntos de pausa.

