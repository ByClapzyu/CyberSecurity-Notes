# bases_ad

 - **Forest:** Es la frontera de seguridad (security boundary) definitiva. Define el **esquema** único y la configuración de configuración para todos los dominios contenidos.
- **Dominio:** Unidad lógica de particionamiento del directorio que facilita la replicación de objetos y la aplicación de Directivas de Grupo (GPO). 
	- "laboratorio.local"
- **Controlador de Dominio (DC):** Servidor crítico encargado de centralizar la gestión de identidades y la seguridad del entorno.
- **DSRM:** Protocolo de acceso de seguridad diseñado para la recuperación del Directorio Activo en escenarios de fallo crítico o corrupción de la base de datos.{}
- **Nombre NetBIOS:** Identificador simplificado del dominio utilizado para asegurar la compatibilidad con sistemas legados y facilitar el inicio de sesión en entornos de red específicos.
	- "pruebas o laboratorio o sucursal"

	NetBIOS es un protocolo antiguo de Windows que permite que las computadoras en una misma red local se encuentren por su 'nombre corto' en lugar de usar direcciones IP o el DNS del dominio.

- **OU** (Unidad Organizativa): es un objeto contenedor dentro de un dominio que permite agrupar cuentas de usuarios, equipos y grupos en una estructura jerárquica. Su función es servir como unidad minima para la vinculación de Objetos de Directiva de Gruppo/GPO y la delegación de autoridad administrativa.

# configuracion_de_red_vm

- La arquitectura de red de la maquina virutal se basa en una configuración de doble interfaz. En la primera se habilita un adaptador en modo NAT (**Network Addreess Translation**) con el proposito de facilitar el accesso a servicios externos y la gestión de actualiazciones criticas del sistema sujeto a los requisitos de conectividad del despliegue. Se configura la segunda interfaz en modo **Red Interna** para garantizar el aislamiento del tráfico de los servicios de dominio, asegurando que la comunicación entre nodos  se mantenga dentro de un entorno controlado y seguro. Para esta interfaz, se requiere la configuración de un direccionamineto estático. Esto asegura la persistencia de los registros SRV en el DNS.


# configuracion_implementacion_ad

### dns

Tras la implementación de AD, se inicia la fase de validación de servicios. Se verificará que la resolución de nombres DNS sea consistente mediante la utilidad **`nslookup "laboratorio.local"`**. El éxito de esta prueba confirma la integridad de la zona de búsqueda directa y la disponibilidad del controlador de dominio.
# nueva-ou

Se inicia la creacion de unidad organizativa (OU) con el fin de optimizar la estructura jerárquica del dominio. 

1) inicie la consola **Active Directory Users and Computers**.
2) Identifique el nodo raíz del dominio, despliegue el **menú contextual** y seleccione **New** > **Organizational Unit**.

 Dentro de la OU se hace la creación de sub-unidades organizativas con los siguiente nombres:
- **New** > **Organizational Unit**
	- Users
	- Groups
	- Computers
	objetivo: *Preparar el entorno para una aplicación eficiente de GPOs.*
## new-user
Dentro de la sub-unidad organizativa "Users" se hace lo siguiente:

1) Identifique el nodo de Users, despliegue el **menú contextual** y seleccione **New** > **User**
2) registre datos del usuario  e implementa una contraseña que cumpla con la politicas.

# new-group

Dentro de la sub-unidad organizativa "Groups" se hace lo siguiente:

1) Identifique el nodo de Group, despliegue el **menú contextual** y seleccione **New** > **Group**
2) registre el nombre del grupo.
3) despliegue el **menú contextual** y seleccione **properties** > **members** > **add**

gruopo-permisos-especiales

1) Identifique el grupo
2)  Identifique el nodo raiz de dominio, despliegue el **menú contextual** y seleccione **Delegate Control
3) Agregue el grupo, **custom task** > **only the following objects in the folder** >**computer object** > marcar 2 casillas "created y delete" (para borrar rastro viejo, para volver a unir) >next
4) **general, property-specific** > **reset password** > **read and write account restrictions** > **validate wr to DNS h name** > **validate w to service...**
- objetivo: dar permisos para unir dominio-host.
# union-host-dominio

1) tener ip estatica, DNS preferido ip del server.
2) about pc >**cambiar nombre (avanzado)** > **dominio**
3) ingresar credenciales.
4) Reinicio, acceder con usuario creado en AD normal

VK7JG-NPHTM-C97JM-9MPGT-3V66T

# gpos-grl

Se implementan GPO **Group Policy Managemenet**:
1) Inicie la consola  **Group Policy Managemenet** 
2) identifique el nodo del forest de raiz del dominio, despliegue domains, dominio
3) ubicado en nuestro dominio despliegue el **menú contextual** y seleccione **Create a GPO in this domain, and Link it here**, *asigne nombre*.
4) despliegue el **menú contextual** y seleccione edit
5) seleccione de acuerdo a la politica requerida.


# gpos-control-panel

 Inicie la consola  **Group Policy Managemenet** 
1) identifique el nodo del forest de raiz del dominio, despliegue domains, dominio
2) ubicado en nuestro dominio despliegue el **menú contextual** y seleccione la que se creo.
3) despliegue el **menú contextual** y seleccione edit
4) **User configuration** > **Polices** > **Administrative Templates** >**Control Panel** > **Prohibit acces to Control Panel and PC settings**

# event-viewer

#### codes 
- 4624 **inicio sesión exitoso**
- 4625 **nicio sesión fallido**
- 4634 **logoff** (evento finalizado)
- 5379 **lecura credenciales**