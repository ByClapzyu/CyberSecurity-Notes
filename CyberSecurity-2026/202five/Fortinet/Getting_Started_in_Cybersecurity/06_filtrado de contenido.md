## Definición y Propósito

**Definición:** Es un proceso de control de seguridad que filtra o restringe el acceso a correos electrónicos, páginas web, archivos ejecutables y otros elementos sospechosos en la red.

**Objetivo del Bloqueo:** El filtro analiza el tráfico para bloquear tres categorías principales de contenido:

1. **Nocivo:** Sitios con malware, phishing o kits de explotación.
    
2. **Ilegal:** Contenido prohibido por las leyes locales (ej. piratería, drogas).
    
3. **Inapropiado:** Material que viola las políticas de la organización o normas sociales (ej. violencia gráfica, contenido para adultos).
    

**Caso de Uso Común:**

- **Control Parental:** Los padres y escuelas utilizan el filtrado web para proteger a los menores de material gráfico o dañino (cumplimiento de leyes como CIPA).
    

##  Tipos de Filtro de Contenido

Existen diferentes métodos técnicos para aplicar estas restricciones:

### A. Filtro de Motores de Búsqueda

- **Funcionamiento:** Se aplica directamente en los resultados de búsqueda (Google, Bing).
    
- **Clasificación:** Permite niveles de restricción como Estricto, Moderado o Seguro.
    
- **Ventaja:** Ayuda a filtrar imágenes y textos explícitos desde la fuente, reduciendo los falsos positivos.
    

### B. Filtro de Correo Electrónico

- **Funcionamiento:** Analiza los encabezados, el cuerpo del mensaje y los archivos adjuntos.
    
- **Método:** Utiliza listas negras en tiempo real (RBL) e identifica palabras clave prohibidas o extensiones de archivos no autorizados (ej. bloquear archivos .exe) para detener correos maliciosos.
    

### C. Filtrado de Contenido Basado en DNS

- **Funcionamiento:** Ocurre en la etapa de resolución de nombres. Cuando el usuario escribe "https://www.google.com/search?q=sitio-malo.com", el servidor DNS verifica una lista de bloqueo.
    
- **Acción:** Si el sitio está en la lista negra, el DNS niega la resolución (no entrega la dirección IP), impidiendo la conexión desde el inicio. Las empresas pueden definir también listas blancas (sitios permitidos).
    

### D. Filtro Web (Basado en Categorías)

- **Funcionamiento:** Clasifica millones de sitios web en categorías predefinidas (Juegos, Apuestas, Noticias, Redes Sociales).
    
- **Machine Learning:** Utiliza aprendizaje automático para categorizar sitios nuevos automáticamente.
    
- **Perfiles:** Se aplican reglas según el perfil del usuario (ej. Marketing puede entrar a Facebook, pero Finanzas no).
    
- **Cumplimiento:** Ayuda a cumplir normativas legales como CIPA (Children's Internet Protection Act).
    

##  Beneficios y Funciones Adicionales

Implementar el filtrado web ofrece ventajas que van más allá de la simple censura:

1. **Seguridad (Protección contra Amenazas):**
    
    - Bloquea el acceso a sitios conocidos por alojar malware.
        
    - Identifica y detiene intentos de suplantación de identidad (Phishing).
        
    - Detecta kits de vulnerabilidad, bloqueando la conexión antes de que se descargue la carga maliciosa.
        
2. **Rendimiento (Eficiencia de Red):**
    
    - Aumenta la eficiencia del ancho de banda al bloquear sitios de alto consumo (como streaming de video no laboral), permitiendo conexiones más rápidas para las tareas críticas.
        
3. **Productividad (Recursos Humanos):**
    
    - Evita distracciones en el lugar de trabajo, manteniendo a los empleados enfocados en sus tareas laborales.
        

---

**Servicio Fortinet: FortiGuard Web Filtering**

**FortiGuard Web Filtering**.

- Este servicio alimenta a los dispositivos **FortiGate** (Firewall) y **FortiProxy**.
    
- Proporciona una base de datos masiva de URLs categorizadas y puntuaciones de reputación en tiempo real.
    
- Permite aplicar políticas granulares basadas en usuarios, grupos y horarios.