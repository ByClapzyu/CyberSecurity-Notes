**Criptografía** : Estudio de la escritura o la rsolución de códigos.

PKI: Implementación de la criptología en una red informatica,, compuesta de hardware, software y politica y procedimientos.

La criptografía permite el cifrado de datos y firma digital.

**cifrado**: proceso de conversión de texto plano a texto criptográfico

**firma digital**: vincula al firmante con la información firmada.

uso del cifrado:
- privacidad y confidencialidad
uso de firma:
- integridad 
- autenticidad
- no repudio
resultado: comercio electroniyo y comunicación segura.

# cifrados

**cifrado**:forma secrete o disimulada de escribir un código.

**algoritmos**: los algortimos y las claves digitales prmiten cifras y decifrar información.
	Los algoritmos son información pública y las claves son, generalmente secretas

## Tipo de cifrado

**por sustitución** :  este usand antes informatica (**julius caesar**)
se desplaza x cantidad de letrar (secreto/clave)  y el metodo algoritmo de cifrado,. 

**transposicional**: re ordenar las letrar como (rail fence)  se necesita sbaer cuantas filas hay (secreto/clave)

**libreta de un solo uso**: introduce alatoriedad en el metodo de sustitucion., 26 posibles combinaciones para cada letra. casi 12 millones de combinaciones para un mensaje de 5 letras , sin computadora es imposible de decifrar mediante fuerza bruta.

![[Libreta de un solo uso.png]]

## Cifrado de computadoras

# Cifrado de flujo

Cifra un flujo de datos de texto plano bit a bit o byte a byte.
Ejemplo: FISH, RC4 (Cifrado rives)

mas rapidos
# Cifrado de bloque
Cifra datos de texto plano en bloques
el tamaño del bloque depende del tamaño de la clave,
Ejemplo: DES, 3DES, AES y BlowFish 

# calve digital
En criptografía es un valor que se puede expresar alfanumericamente y que se usa para hacer operaciones criptograficas.
- firma digital
- codigo de autenticacion de mencaje (MAC: es una funcion hash que usa una clave digital para garantizarla integridad y auntenticidad del mensaje)
- cifrado
	- flujo de info tren dos dispostivos
	- datos estacionarios masivos
	- fragmente pequeño de datos ,como una clave digital.
- pueden ser:
	- privada o secretas
	- publica
## longitudes y fortalezas de clave

Publicas :
- clave grande 1024 bits y superior , cifrar fragmentos pequeños de datos
	- transferencia de claves y firmas digitales
- clave pequeña entre 128 y 256 bits, cifriar datos masivos.
	- flujo de datos o datos masivos donde el rendimiento es cfitico
- longitu + cmplejidad

ejemplo de ocntraseña (10 caracteres solo numero )(10 millones) vs contraseña de 8 caracteres nuero,letra y signos (218 trillones)

Estiraminetos de clave
metood para hacer mas seguras las claves o contraseñas.
- funcion dos de derivacion de clave basda en contraseña (PBKDF2)
- BCRYPYT
el proceso de salting: la es es un valor aleatorio añadido a otro valor para aumentar la entropia.

## Algoritmo simetrico

Algoritmo simetrico: cifrado que se usa para cifrar y decifrar datos con la misma clave/llave
- des
- 3des
- idea
- aes
- rc4 (flujo),rc5,rc6
- blowfish/twofish
- (pon descripcion breve de cada uno)

ventajas y desventajas.

cifrado y decifrado mas rapido que la criptografia asimetrica.
eficiente para cifrar y decifrar cantidades grandes de datos.

- se basa en una calve secreta que debe ser compartida entre partes involucrades, debe mantenerse se