# ¿Qué es una amenaza a la ciberseguridad?

- **Amenaza (Threat):** Es la **acción** o el evento potencial. Aprovecha una vulnerabilidad para causar daño, robo o interrupción en el sistema.
    
- **Vector de Ataque:** Es el **método, camino o vehículo** que utiliza el actor malicioso para llegar a su objetivo (entrar en la red o inhibirla).
    
- **Ruta de Ataque (Attack Path):** Es la cadena completa de eventos o pasos que ocurren cuando se explota un vector.

### Componentes de un Vector de Ataque

Para que un ataque funcione, generalmente necesita estos 3 elementos:

1. **Vulnerabilidad:** El fallo o debilidad (ej. un usuario descuidado, un puerto abierto).
    
2. **Mecanismo:** La herramienta usada (ej. Malware, Phishing).
    
3. **Ruta:** El canal de entrega (ej. Correo electrónico, USB, Web).

## Tipos de Amenazas (Categorías)

1. **Ingeniería Social:** Manipulación psicológica para engañar a los usuarios (el "hackeo humano").
    
2. **Malware:** Software diseñado para causar daño informático.
    
3. **Acceso No Autorizado:** Entrar a sistemas donde no se tienen permisos.
    
4. **Falla del Diseño del Sistema:** Defectos en la lógica de seguridad de una aplicación o dispositivo (Bugs).

# Vectores de Ataque Comunes

**Suplantación de identidad (Phishing)**

Tenica usada para instalar malware o robar credenciales

|**Tipo**|**Descripción**|**Objetivo**|
|---|---|---|
|**Phishing (Normal)**|Ataque masivo, no discrimina. "Tirar la red a ver qué pez cae".|Cualquiera (Volumen).|
|**Spear Phishing (Dirigido)**|Ataque personalizado. Investigan a la víctima antes de atacar.|Individuo o Grupo específico.|
|**Whaling (Alto Perfil)**|Ataque dirigido a "peces gordos" con mucho poder o acceso.|CEOs, Directivos, Gerentes.|
**Ataque de Denegación de Servicio**

Su objetivo es que el servicio **deje de funcionar** (disponibilidad), no necesariamente robar datos.

- **DoS (Denial of Service):** Ataca desde **una sola fuente** (una computadora). Es fácil de bloquear.
    
- **DDoS (Distributed Denial of Service):** Ataca desde **múltiples fuentes** simultáneamente.
    
    - **Botnet:** Red de dispositivos infectados (zombies).
        
    - **C&C (Command & Control):** El servidor maestro que da la orden a la botnet para atacar todos a la vez.
        

**Ataques a Contraseñas y Cifrado**

- **Fuerza Bruta (Brute Force):** Probar todas las combinaciones posibles de contraseñas hasta acertar.
    
- **Ataque de Cumpleaños (Birthday Attack):** Ataca la integridad. Aprovecha vulnerabilidades en los algoritmos de **Hash** para encontrar dos mensajes distintos que generen la misma huella digital (colisión).

***Normalmente la etapa previa es sumplatacion de identidad ya que es necesario que el usuario abra la puerta***