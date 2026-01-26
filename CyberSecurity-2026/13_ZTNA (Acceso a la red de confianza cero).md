
Establece una sesion segura entre una entidad final y una red, al mismo tiempo gaarantiza un control granular sobre el acceso a los recursos y ejerce confianza cero, independientemente de la ubivacion de la entidad final o de la red.

**confinazza cero**: acceso con minimo privilegios (no confia en nadie)
Automatica tuneles cifrados:
	Entidad final al proxy de acceso de ztna (ejemplo de uno creo que switch o rutter)
	recursos ocultos 
**Componentes:**

- Cliente de ZTNA (se puede utilizar con un navegador web)
    
- Proxy de acceso de ZTNA
    
- Servidor de directorio de autenticación local o identidad como servicio (IDaaS)
    
- Servidor y firewall de política de seguridad de ZTNA

- **Control de acceso dinámico**
    
    - Acceso granular por sesión
	    - acceso por sesión: significa cada vez que el usuario se conecta a la red, se autentica y se hace una avaluacion de riesgo sobre el dispostivo que se coencta.
        
    - **Basado en:**
        
        - Identidad del usuario
            
        - Identidad del dispositivo y perfil de riesgo.
	        - dispostivi: puede ser una compu, o un portatil
            
        - Política: puede definir parametros de acceso a los recursos segun su función del usuario, el tipo de dispositvo y otros factores.
    - 