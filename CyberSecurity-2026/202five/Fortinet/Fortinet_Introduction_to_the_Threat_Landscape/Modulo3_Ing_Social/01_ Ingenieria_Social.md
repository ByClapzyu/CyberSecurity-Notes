**Definición:** Manipulación psicológica para fines maliciosos. Es una amplia gama de ataques diseñados para incentivar al objetivo a realizar acciones que permitan al atacante tener éxito (como revelar claves o descargar malware).

**Canales/Métodos:**

- Interacción cara a cara.
    
- Correo electrónico.
    
- Teléfono / SMS.
    
- Redes Sociales.

## Técnicas de Ing social

|**Técnica**|**Descripción Clave**|**Ejemplo**|
|---|---|---|
|**Quid Pro Quo**|"Algo por algo". Intercambio de favores.|"Te ayudo a arreglar tu PC lenta si me das tu contraseña para entrar".|
|**Pretexting (Pretexto)**|Crear un escenario inventado para invocar una **respuesta emocional** o de confianza.|"Soy del banco, hay un cargo no reconocido, necesito confirmar tus datos ya".|
|**Baiting (Cebo)**|Ofrecer algo tentador (físico o digital) que despierte la **curiosidad o avaricia**.|Dejar una USB etiquetada "Sueldos Ejecutivos" en el estacionamiento.|
|**Scareware**|Software o pop-ups que infunden **miedo** mediante desinformación para que compres algo falso.|"¡SU PC ESTÁ INFECTADA! Pague $50 aquí para limpiar".|
|**Watering Hole (Abrevadero)**|Infectar un sitio web legítimo que el objetivo frecuenta.|Hackear el foro de cafetería que visitan los empleados de la empresa objetivo.|
|**Tailgating (Piggybacking)**|Aprovechar normas sociales (amabilidad) para acceder físicamente a un lugar restringido.|Pegarse a alguien que abrió la puerta con tarjeta o entrar cargando cajas pidiendo que "le sostengan la puerta".|
|**Honey Trap (Trampa de Miel)**|Atracción del objetivo mediante interacción romántica o sexual falsa.|Perfil falso en redes de citas para sacar secretos de estado.|

## Variante Suplantación de Identidad

| **Tipo**           | **Vector** | **Objetivo** | **Descripción**                                                                 |
| ------------------ | ---------- | ------------ | ------------------------------------------------------------------------------- |
| **Phishing**       | Correo     | Masivo       | "Pesca de arrastre". Correo genérico para ver quién cae.                        |
| **Spear Phishing** | Correo     | Específico   | Dirigido a una persona o departamento concreto (requiere investigación previa). |
| **Whaling**        | Correo     | Alto Perfil  | Dirigido a CEOs, Directivos ("Ballenas"). Buscan grandes sumas o secretos.      |
| **Smishing**       | SMS/Texto  | Cualquiera   | Phishing por mensaje de texto ("Tu paquete está retenido, clic aquí").          |
| **Vishing**        | Teléfono   | Cualquiera   | Phishing por voz/llamada ("Voice Phishing").                                    |
## Amenaza de Codigo web

**Applets de Java:**

- **Definición:** Son pequeñas aplicaciones escritas en lenguaje Java que se entregaban a través de navegadores web.
    
- **El Riesgo:** Aunque ya son tecnología antigua, históricamente fueron muy peligrosos porque si el usuario aceptaba los permisos, el Applet podía ejecutarse con privilegios locales en la computadora, sirviendo como puerta de entrada para malware. Hoy en día están bloqueados por defecto en casi todos lados.

## Amenazas internas (insider threats)

**Definición:** Personas que trabajan para una organización (empleados, ex-empleados, contratistas) y tienen acceso autorizado, pero que suponen un riesgo físico o cibernético.

### Clasificación de Insiders (Pregunta de Examen)

Se dividen en dos grandes grupos: **Negligentes** (sin querer) y **Maliciosos** (con intención).

#### A. Negligentes (Error Humano)

1. **Peón (Pawn):**
    
    - Es un empleado inocente que es **manipulado** por un actor malicioso externo. No sabe que está haciendo daño.
        
    - _Ejemplo:_ La recepcionista que descarga un archivo adjunto creyendo que es una factura real.
        
2. **Torpe (Goof):**
    
    - Usuario arrogante o ignorante que cree saber más que las políticas de seguridad. Se salta las reglas por comodidad, no por maldad.
        
    - _Ejemplo:_ El empleado que desactiva el antivirus porque "pone lenta la PC".
        

#### B. Maliciosos (Turncloaks / Traidores)

1. **Colaborador:**
    
    - Persona con acceso interno que trabaja en conjunto con un tercero externo (hacker o competidor) para robar datos.
        
2. **Lobo Solitario (Lone Wolf):**
    
    - Persona con acceso interno que actúa **completamente sola**. Suele ser por venganza, ideología o beneficio propio.
        
3. **Topo (Mole):**
    
    - **OJO:** Técnicamente es un **externo** que ha logrado infiltrarse (o ha sido contratado falsificando credenciales) para fingir ser un empleado interno. Ya está dentro, pero su origen es externo
## Indicadores y Protección

### Indicadores de Amenaza (¿Cómo detectarlos?)

- **Humanos (Comportamiento):**
    
    - Expresiones de rencor o descontento laboral.
        
    - Cambio repentino de estilo de vida (riqueza inexplicable).
        
    - Trabajar en horas inusuales sin razón.
        
- **Red (Digital):**
    
    - Tráfico de datos inusual (ej. subidas masivas de archivos a la nube).
        
    - Solicitudes de acceso a sistemas que no tienen que ver con su trabajo.
        
    - Uso de USBs o dispositivos no autorizados.
        
    - Envío de información sensible a correos personales (Gmail/Hotmail).
        

###  Acciones para Proteger Activos

**En el Endpoint / Usuario:**

- Conocer y respetar las políticas de seguridad.
    
- No usar "atajos" (no desactivar seguridad).
    
- No exponer credenciales ni compartir info privada.
    
- Proteger datos confidenciales (cifrado).
    
- Mantener parches/actualizaciones al día.
    
- No permitir Tailgating.
    

**En la Red / Administración:**

- **Identificar activos:** Saber qué hay que proteger.
    
- **UEBA (User and Entity Behavior Analytics):** Herramientas automáticas que aprenden el comportamiento normal del usuario y alertan cuando hace algo raro.
    
- Impartir **capacitación** continua (Awareness).
    

---

## 6. Fraude y Campañas de Influencia

###  Fraude vs. Estafa

- **Ciberfraude:** Delito grave. Uso de engaño, malware o ingeniería social para obtener beneficio económico sustancial.
    
- **Ciberestafa (Scam):** Tipo de fraude, generalmente de menor escala o impacto individual.
    
    - _Fraude de vacaciones / Citas:_ Engaños personales.
        
    - _BEC (Business Email Compromise):_ Comprometer el correo de un ejecutivo para ordenar pagos fraudulentos.
        
    - _Pharming:_ Redirigir a un usuario de un sitio web legítimo a uno falso (a nivel de DNS o archivo hosts) para robar datos.
        

### Campañas de Influencia (Fake News / Desinformación)

Iniciativas a gran escala para cambiar la opinión pública (política, social).

- **El Ciclo:**
    
    1. Creación de cuentas falsas (Bots).
        
    2. Creación del contenido (Narrativa falsa).
        
    3. Publicación masiva del contenido.
        
    4. Usuarios reales lo ven y comparten (Viralización).
        
    5. Medios de comunicación amplifican el mensaje.