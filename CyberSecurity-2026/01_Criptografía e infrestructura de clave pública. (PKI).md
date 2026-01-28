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

- se basa en una calve secreta que debe ser compartida entre partes involucrades, debe mantenerse secreta,(problema seguridad)

## Algoritmo asimetrico
 se usa para operaciones cirptografics que usan un par de claves relaconadas matematicamente,.
 puede hacer todoa o algunas de las operaciones.
 - cifrado
 - intercambio de clave 
 - firma digital.
Estos son conocidos como algoritmos y criptografia de clave publica.

- Diffie Helman
- RSA
- Curva eliptica ECC
- PGP Y GPG
- DSA
Ventaja
- mayor seguridad (no comparten claves privadas)
- publica cifra, privdada decifra.
- 
desventaja
- lentas
- no es eficinete para cntidades grande de datos

Combinacion de ambas : se elimina las desventajas.

![[combinasion asimetrico y simetrico.png]]
## Hashing y firmas digitales

Es el proceso de convertir datos  de tamaño arbitrario en un valor unico de tamaño fijo.

funciones importantes:
- valor de salida tiene una longitud fija
	- lo determina el algoritmo de hashing
	- niega al actor malicioso maliciosos informacion sobre la naturaleza de los datos de entrada.
- El valor de salida es unico para cada valor de entrada
	- detecta cambios en los datos de entrada cuando el valor de salida es diferente.
	- impide que el actor maliciosos tenga la posibilidad de alterar los datos y cumplir su onjetivo
	- evita coliisones
- El hashing no es reversible y es unidireccional
	- no se puede reporducir el valor de entrada usando el valor de salida.
	- impide que el actor malicioso use el valor de salida pra determinar el valor de entrada.

Crear una  firma digital:
- se necesita el hashing y la criptografia asimetrica.
- estas garantizan:
	- integridad 
	- autenticacion de firmante
	- no repudio (no puede negar validez)
	
proceso:
valor de entrada --> funcion hash --> valor de salida hash --> algoritmo asimetrico --> firma digital --> dato firmado digitalmente.

Proceso de verificacion:
se checa el hash y debe coincidir con el original.

## Funciones Hash

- Resumen de mensajes cinco (MD5) y MD6
- Algoritmo hash seguro (SHA-1, SHA-2, SHA-3)
	- -SHA-2 inclye SHA-224, 256, 384, 512
	- varias longitudes de salida SHA-3
- Algoritmo LANMAN y NT LAN Manager (NTLM) de Microsoft
- HAVEL y RIPEMD

## Ataques comunes contra el hashing

- Ataque de fuerza bruta, eficaz si el actor tiene pista sobre la naturaleza de los datos de entrada.
- ataque de cumpleaños (explica breve y claro)
	- es mas facil encontrar dos concidencias si no importa que son
	- colision: dos entradas dan 2 salids iguales.
	- calculo matematicos al problema del dia de cumpleaños en la teoria de la probabilidad.
-**defensa**
aumenta el tamaño de la longitud hash
estiramientos de clave.

- 