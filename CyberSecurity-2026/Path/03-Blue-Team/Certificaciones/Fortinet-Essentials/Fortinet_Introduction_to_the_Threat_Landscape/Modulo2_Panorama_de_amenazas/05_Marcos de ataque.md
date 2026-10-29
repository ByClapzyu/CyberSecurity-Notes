- identificar situacion
- analisis de impacto
- clasificacion problema
- desarollo estrategias 

### APT (Amenaza Persistente Avanzada)

- **Definición:** Generalmente son **Naciones-Estado** (o grupos criminales muy financiados).
    
- **Clave:** Tienen **Paciencia y Dinero**. No atacan y se van; entran, se esconden y se quedan meses o años (dwell time) robando datos sin ser detectados.
    
- **Ejemplo:** Grupo Lazarus (Corea del Norte), APT28 (Rusia).

# Cyber Kill Chain (La Cadena de la Muerte)

Fue desarrollada por **Lockheed Martin**

Es un modelo **LINEAL**. La teoría dice que si rompes _cualquier_ eslabón de la cadena, detienes el ataque.

### Los 7 Pasos (Corrección de Terminología)

Tus definiciones están bien, pero los **nombres técnicos** deben ser exactos:

1. **Reconocimiento (Reconnaissance):** Correcto. Investigar a la víctima (OSINT, LinkedIn, Shodan).
    
2. **Armamento (Weaponization):** (Corregí tu typo "aramento"). Es crear la bala. Unir el **Exploit** (lo que rompe la seguridad) con el **Payload** (el virus/malware). Ejemplo: Meter un script malicioso dentro de un PDF.
    
3. **Entrega (Delivery):** Correcto. ¿Cómo llega el PDF a la víctima? (Email, USB, Link).
    
4. **Explotación (Exploitation):** **¡OJO AQUÍ!** En tus notas pusiste "vulnerabilidad". El paso se llama **Explotación**. Es el momento exacto en que el código malicioso se ejecuta en la CPU de la víctima.
    
5. **Instalación (Installation):** Correcto. El malware se instala y busca persistencia (para no borrarse al reiniciar).
    
6. **Comando y Control (C2):** Correcto. El malware "llama a casa" (al servidor del hacker) para pedir instrucciones.
    
7. **Acciones sobre Objetivos (Actions on Objectives):** En tus notas pusiste "exfiltración". La exfiltración es lo más común, pero el objetivo podría ser también **Destrucción** (Ransomware) o **Espionaje**. El nombre oficial engloba todo.
    

**Desventaja Clave (Añade esto):** La Kill Chain se centra mucho en el **Perímetro** y en evitar que entren. Una vez que el hacker está adentro (paso 5-6), este modelo se queda corto. Además, no sirve bien para amenazas internas.

# MITRE ATT&CK (La Matriz del Comportamiento)

Si la Kill Chain es un "Mapa de Carreteras", MITRE ATT&CK es la "Tabla Periódica de los Hackers". Es el estándar de oro actual.

**¿Qué significa ATT&CK?**

- **A**dversarial **T**actics, **T**echniques, **&** **C**ommon **K**nowledge.
    

### Tactica vs  Tecnica

- **Táctica (El QUÉ / El Objetivo):** ¿Qué quiere lograr el hacker?
    
    - _Ejemplo:_ "Quiero robar contraseñas" (Credential Access).
        
- **Técnica (El CÓMO):** ¿Cómo lo hace específicamente?
    
    - _Ejemplo:_ "Usando Keylogging" o "Haciendo Brute Force".
        
- **Procedimiento (El DETALLE):** La herramienta exacta.
    
    - _Ejemplo:_ "Usando el script `mimikatz.exe` con el flag `-dump`".
        

**Ventaja sobre Kill Chain:** MITRE es una **Matriz**, no una línea. Asume que el atacante **YA ESTÁ DENTRO** y describe cómo se mueve lateralmente, cómo escala privilegios y cómo evade defensas. Es mucho más detallado para el Blue Team.