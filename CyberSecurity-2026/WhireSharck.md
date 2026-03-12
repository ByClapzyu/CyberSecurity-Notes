![[escenario_MITM_Chuck.png]]

# MITM

### ¿Como funciona? 

La base de Man In The Middle es el ARP spoofing donde uno debe mentir sobre la Mac, si lo vemos desde un escenario donde hay 3 dispostivos:

- router -->ip: 10.0.0.1  MAC: AA:AA
- phone -->ip 10.0.0.3 MAC: BB:BB
- hacker´s pc --> 10.0.0.4 MAC: CC:CC

El objetivo de ARP spoofing es hacer que el **router crea que nuestra MAC CC:CC es la del celular phone MAC: BB:BB** Y que el telefono piense que la MAC CC:CC es del router. Esto hace que quedemos como un puente en la conversación.

Esto para una persona normal no es evidente pero para alguien que sabe se puede traducir como un retraso ya que el paquete hace una parada que no deberia hacer.

