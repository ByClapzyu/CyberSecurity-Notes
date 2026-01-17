# "Everything is a file"

 **Filosofia** En UNIX/Linux "Todo es un archivo"

Para el Kernel todo son flujos de byte que se pueden leer o escribir.
- **Documentos**: /home/user/notas.txt (archivo normal)
- **Disco duro**: /dev/sda (archivo represanta hardware fisico)
- **Mouse**: /dev/input/mouse0 (archivo que esucupe info cada vez que se mueve la mano)
- **papelera**: /dev/null (archivo magico donde lo que se escibe desaparece).

Lo bueno de esto que es podemos usar las mismas herramientas para todo. Podemos usar un cp (copiar) para duplicar texto, o para hacer un backup de nuestro disco con (cp /dev/sda /dev/sdb)

**Los Permisos**
Al ejecutar un ***ls -l*** 