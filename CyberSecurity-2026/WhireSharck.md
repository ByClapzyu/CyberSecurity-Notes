![[escenario_MITM_Chuck.png]]

# MITM

### ¿Como funciona? 

La base de Man In The Middle es el ARP spoofing donde uno debe mentir sobre la Mac, si lo vemos desde un escenario donde hay 3 dispostivos:

- router $\rightarrow$$ip: 10.0.0.1  MAC: AA:AA
- phone -->ip 10.0.0.3 MAC: BB:BB
- hacker´s pc --> 10.0.0.4 MAC: CC:CC

El objetivo de ARP spoofing es hacer que el **router crea que nuestra MAC CC:CC es la del celular phone MAC: BB:BB** Y que el telefono piense que la MAC CC:CC es del router. Esto hace que quedemos como un puente en la conversación.

Esto para una persona normal no es evidente pero para alguien que sabe se puede traducir como un retraso ya que el paquete hace una parada que no deberia hacer.

El **TTL** es un valor en el encabezado IP que indica cuántos "saltos" (**hops**) puede dar un paquete antes de ser descartado. Es clave para detectar intermediarios no autorizados.

**Valores Iniciales Estándar:**

- **64:** Linux / Android / Mac / iOS.
    
- **128:** Windows.
    

**Comportamiento en la Red:**

- El valor se **resta en 1** cada vez que el paquete es procesado y reenviado por un dispositivo de Capa 3 (Router, Gateway o Atacante).
    
- **Escenario Normal:** Dispositivo (64) $\rightarrow$ Router lo recibe (64) $\rightarrow$ Router lo envía a Internet (**63**).
    
- **Escenario MITM:** Dispositivo (64) $\rightarrow$ Atacante (lo recibe 64 y resta 1) $\rightarrow$ Router (lo recibe **63**).


# Nmap

Escaneo y reconocimientos.
Reconocimiento de dispositivos  `nmap -sn 192.168.50.0/24`


# Wiresharck

Este se usa para ver el trafico. Para no volvernos loco con tantos datos, se pueden usar fitros.
- `ip.addr 192.168.50.20 ` : ver data solo una ip especifica.
- `ip.addr 192.168.50.20 && http` : Ver data de http de cierta ip.
- `http.content_type contains "image"`
# Ettercap

 **Ettercap:** Herramienta de intercepción activa. Se utiliza para realizar el **envenenamiento de tablas ARP** (ARP Poisoning) y **forzar que el tráfico de la red fluya a través de nuestra máquina**. A diferencia de Wireshark (que es pasivo), Ettercap es **activo**: puede capturar credenciales en tiempo real y manipular paquetes.

# A packets

Reporte o data estructurada para entender mejor, aqui se sube pcap files

