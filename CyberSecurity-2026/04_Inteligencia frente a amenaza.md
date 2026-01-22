# Cyber Threat Intelligence (CTI)

## 1. Definición Clave

No es solo "datos", es **Conocimiento procesado**. Es la diferencia entre saber que _"está lloviendo"_ (dato) y saber que _"viene una tormenta que inundará el sótano donde están los servidores"_ (inteligencia).

- **Propósito:** Fundamentar decisiones (desde bloquear una IP hasta cambiar la estrategia de seguridad anual).
    

## 2. Las 3 Características de la Calidad

Para que un dato sea Inteligencia, debe cumplir con esto:

1. **Relevante:** ¿Me afecta a mí? (Si soy una panadería, una amenaza a plantas nucleares no es relevante).
    
2. **Procesable (Actionable):** ¿Puedo hacer algo con esto? (Ej: "Bloquea la IP 1.2.3.4").
    
3. **Contextual:** ¿Entiendo la amenaza? (Quién, cómo, cuándo).
    

## 3. Fuentes de Inteligencia (De dónde sacamos la info)

- **Interna:** Lo que tus propios sistemas te gritan. Logs de firewall, SIEM, análisis de incidentes pasados.
    
- **Externa (OSINT):** Fuentes abiertas. Blogs de hackers, noticias, feeds del gobierno (CISA), Twitter (X) de investigadores.
    
- **Privada/Comercial:** Pagas por ella. Empresas como Fortinet, CrowdStrike o Mandiant te venden reportes exclusivos.
    
- **ISACs ("mercados verticales"):** _Information Sharing and Analysis Centers_. Son clubes de industrias (Ej: Bancos comparten info con otros Bancos) para protegerse mutuamente.
    

---

# Herramientas y Estándares (El Lenguaje Común)

### STIX vs TAXII

Imagina que envías una carta por correo.

- **STIX (Structured Threat Information eXpression):** Es **LA CARTA** (El contenido).
    
    - Es el formato (XML/JSON) para describir la amenaza.
        
    - Define: "¿Quién es el actor?", "¿Qué malware usó?", "¿A qué IP se conecta?".
        
- **TAXII (Trusted Automated eXchange of Indicator Information):** Es **EL CAMIÓN DE CORREO** (El transporte).
    
    - Es el protocolo (vía HTTPS/API Rest) que lleva la carta STIX de un punto A a un punto B.
        

### MITRE ATT&CK

Es la **Tabla Periódica de los Hackers**. No se centra en "qué herramienta usaron" (porque las cambian), sino en su **Comportamiento (TTPs)**:

- **Tácticas:** El objetivo del hacker (Ej: "Quiero entrar", "Quiero robar datos").
    
- **Técnicas:** Cómo lo logran (Ej: "Phishing", "Fuerza Bruta").
    

### CVSS (Common Vulnerability Scoring System)

El termómetro de gravedad. Del 0.0 al 10.0.

-  El CVSS mide **Severidad Técnica**, NO **Riesgo**.
    
    - _Ejemplo:_ Una vulnerabilidad 10.0 (Crítica) en un servidor que está apagado y desconectado tiene un **Riesgo bajo** para tu empresa.
        
    - El CVSS base considera: ¿Es fácil de explotar? (Aprovechamiento) ¿Qué tanto daña? (Impacto en Confidencialidad, Integridad, Disponibilidad).
        

---

# El Ciclo de Vida de la Inteligencia (Tu última sección)

Lo que describiste al final son las fases oficiales. Ordénalas así para que tengan lógica de proceso:

1. **Requisitos (Identificar):** ¿Qué queremos proteger y qué nos preocupa?
    
2. **Recolección (Reunir):** Sacar datos de fuentes internas/externas.
    
3. **Procesamiento (Separar el ruido):** Normalizar datos, traducir idiomas, quitar duplicados.
    
4. **Análisis (Buscar IoC):** Aquí entra el cerebro humano. Conectar puntos. "¿Esta IP rara se conecta con este malware conocido?".
    
5. **Difusión:** Avisar al equipo (Alerta al Blue Team o Reporte al CISO).
    
6. **Retroalimentación (Lecciones aprendidas):** ¿Nos sirvió esta info? ¿Qué mejoramos?
