## Definición y Funciones Principales

**Propósito:** Analiza las alertas de seguridad en tiempo real. Actúa como el cerebro centralizado de los registros (logs) de la organización.

**Funciones Clave:**

- **Recopilación y Normalización:** Recolecta, estandariza (pone en el mismo formato) y almacena eventos y alertas provenientes de toda la red y dispositivos.
    
- **Cobertura Híbrida:** Recopila datos tanto de dispositivos locales (on-premise) como de la nube.
    
- **Análisis Avanzado:** Ejecuta análisis sobre los datos para identificar posibles incidentes de seguridad que pasarían desapercibidos si se miraran los registros por separado.
    
- **Priorización:** Clasifica los incidentes por riesgo, gravedad e impacto para que los analistas sepan qué atender primero.
    

##  Razones para implementar SIEM

Las organizaciones invierten en SIEM por tres motivos principales:

1. **Seguridad Mejorada:** Detección más rápida y precisa.
    
2. **Inversión:** Maximiza el valor de las herramientas de seguridad existentes al correlacionar sus datos.
    
3. **Cumplimiento Normativo:** Es esencial para auditorías. Demuestra que los controles de seguridad están implementados y son eficaces.
    

##  Cumplimiento y Normativas (Compliance)

El SIEM automatiza los informes necesarios para cumplir con leyes estrictas. El incumplimiento puede llevar a enfrentar **multas punitivas** severas.

**Normativas Comunes:**

- **PCI-DSS:** Estándar de seguridad de la industria de tarjetas de pago.
    
- **SOX (Ley Sarbanes-Oxley):** Regulaciones financieras y contables.
    
- **HIPAA:** Ley de portabilidad y responsabilidad de seguros de salud (Protección de datos médicos).
    
- **GDPR:** Reglamento general de protección de datos (Privacidad de datos en Europa).
    

##  Características y Tecnologías de Detección

Con el tiempo, el SIEM evolucionó de un simple almacenamiento de logs a un sistema de monitoreo inteligente.

- **Funcionalidades de detección de amenazas:** Escaneo constante de la red.
    
- **Inteligencia de amenazas integrada:** Se alimenta de bases de datos globales para reconocer ataques nuevos.
    
- **UEBA (Análisis del Comportamiento del Usuario y de la Entidad):**
    
    - Monitorea anomalías en el comportamiento (ej. un usuario de Finanzas accediendo a servidores de Ingeniería a las 3 AM).
        
    - Vigila Indicadores de Compromiso (IoC) conocidos.
        
- **Aprendizaje Automático (Machine Learning):** Aplica modelos sofisticados para detectar amenazas desconocidas sin necesidad de reglas manuales.
    

##  El Problema y la Solución (Automatización)

**Desafíos:**

- **Complejidad:** La configuración e integración de un SIEM tradicional puede ser compleja.
    
- **Escasez de Personal:** No hay suficientes analistas para revisar miles de alertas.
    

**Solución:** La escasez de personal impulsó que el SIEM se **automatizara más**.

- **Beneficio:** Se gana tiempo y precisión, reduciendo la carga manual.
    

##  Convergencia NOC y SOC

El SIEM moderno une el Centro de Operaciones de Red (NOC) y el Centro de Operaciones de Seguridad (SOC).

**Visibilidad de Panel Único:** Desde una sola pantalla se tiene visibilidad de toda la red, permitiendo:

- Generar un inventario de usuarios y dispositivos.
    
- Mapear la topología (cómo está conectado cada objeto).
    
- Determinar el comportamiento normal y advertir sobre posibles ataques.
    

---

##  Evolución del SIEM (Basado en el Diagrama)

El SIEM no nació como lo conocemos hoy, pasó por tres etapas evolutivas claras:

**Etapa 1: Una plataforma de información**

- Su función era básica: recolectar y almacenar logs para consultas históricas.
    

**Etapa 2: Centro de inteligencia frente a amenazas**

- Se le agregó la capacidad de correlacionar datos y detectar amenazas conocidas.
    

**Etapa 3: Centro de seguridad y operaciones de red totalmente integrado y automatizado**

- (Estado Actual) Es un sistema que integra NOC y SOC, con automatización, IA y capacidad de respuesta, conectado a todos los dispositivos y usuarios.
    

---

**Producto Fortinet: FortiSIEM**

Para el examen, asocia **FortiSIEM** con:

- La capacidad de ver el **NOC y SOC** en un solo panel.
    
- Soporte para múltiples proveedores (Multivendor).
    
- CMDB (Base de datos de gestión de configuración) integrada que descubre dispositivos automáticamente.