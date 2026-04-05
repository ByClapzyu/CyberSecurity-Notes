
Virtualizacion:

De hardware fisico a crear instancias virutales
- host local: servidor o pc
	- mantener entorno adecuado y seguro
- host externo: navegador web, api
**ventajas**
- Disponibilidad, Escalabilidad y Elasticidad crea y elimina datos8
- reducir costos
**retos**
- tiempo de activididad del dispostivio
- almacenamiento
- seguridad de la maquina
**proteccion**
- parches                          - limitar la conectividad
- politica contraseña         - eliminar piezas inecesarias del hard visual
- firewall                            - evitar expansion (desconrolada)
- segmentacion                 - restringir acceso fisico y adm al hipervisor

**amenaza**
- escape vm:
- remanencia de datos: (destruccion segura de datos
- escalabilidad: (privilegio minimo)
- ataque de migracion

# Amenaza comunes

- error conf, implementacion
Autenticacion y autorizacion: metodos modernos
	**tipo**
	- OAuth
	- SAML: Permite autenticacion de recursos tanto locales como basado en la nube a traves de una unica DB
vm creep: auditoria frecuente
almacenamiento: reglas, autenticacion, lista de contrl acceso
	- politicas
	- IAM
	- ACL
perdida datos: dlp y administracion en cuanto derecho y propiedad
conectividad: cifrar protocolos seguros
registro monitore: SIEm centralizado.
	 - 
derecho propiedad: saber el propietario

# Servicios seguridad alojado en la nube

**escalabilidad**
**cinfiabilidad**

proporcionan:
- alta diponibilidad
- conformacion paquete
- optimiza latencia
- reduce costo, 

tipo: 
WAF,
- balance carga
- seguridad
- escalabilidad
CNF(firewall nube), 
puerta enlace correo
- escalar y verificar todo correo

Servicios:
Autneticacion: 
- LDAP: acceso directorios
- SAML
- OAuth
- proxy
CASB (seguridad acceso nube): autentica, controla acceso 
Navegador (RBI): 
Antivirus y sandox : 

SOC
- dispsitivos de red
- registro
CNP: Presta servicio que necestie : forti,aws,azure,go
- permitras: mas alla de local

# Asegurar

WAF, CNF: preveni perdida datos, intrusiones
- regla politica
- inspecin trafico
- autentica
DLp, monitoreo antivirus, sandbox:  
Proxy: GRANTIza no coenxio ndirecta      malo: dificl usar mucha ubicacio nremoto y poca proteccion
- permite granular trafico
Proxy inverso: 
- abilita equilibrio carga entre servidores             -malo: se debe implmentar delante cada app y dificil implementar en nube
- permite ejecucion especifica app

CASB: agente seguridad de acceso nube: (**protege autenticacion**)
## APIS

REST: Conf rapida monitoreo sencillo, solicita info serv
SOAP: esque xml empaquetar como una http post, mas apps heredadas