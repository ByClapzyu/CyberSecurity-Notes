# Bandit 0

Para poder comenzar con bandit0, necesitamos acceder a traves de **SSH** usando el siguiente comando: 
- ssh bandit0@bandit.labs.overthewire.org -p 2220

Una vez adentro como se muestra en la pagina de OTW nos dice que "The password for the next level is stored in a file called readme located in the home directory."
Para resolver esto necesitamos llegar al home directory,  así que mi primer movimiento es realizar un **pwd** para saber en donde me encuentro, al visualizar que estoy dentro de  ***/home/bandit0***  realizo un **ls** para listar el contenido de home directory. Como se puede ver que esta el file readme antes de ver el contenido del archivo con **cat** procedo a saber que tipo de archivo es con **file** el resultado de esto es "readme: ASCII text" por lo cual este archivo contiene lenguaje humano. Antes del conseguir la contraseña checo cuantos bytes ocupa para darme idea que tanto puede venir con **du -b readme**, veo que pesa 438 bytes por lo cual se puede suponer que no tiene demasiado contenido.

Password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

# Bandit 1

Una vez que accedemos a bandit1, las intruccion nos dice lo mismo, pero ahora el file se llama - , pero si intentamos hacer un **cat -** cat pensara que debe esparar un input así que no va a suceder nada, para eso tenemos dos opciones usar la ruta relativa especificando en la carpeta que no encontramos con **.** y el file que queremos ver **./-** o tambien podemos usar doble **--** para indicar que lo que sigue despues son files y no comandos u opciones. **cat -- -** o **cat ./-**. SI hacemos otra vez lo de **du -b ./-** para saber cuanto pesa este nos marcara que pesa 44 y si lo abrimos podemo ver que solo esta la flag.

Password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
# Bandit 2

En este es similar a los anteriores, pero en este caso el file contiene espacios, por situaciones similares en windows, se que este tipo de files para acceder a ellos se necesita el uso de **""** comillas dobles. Este se resuelve usando el metodo de bandit 1, pero usando "".

Password:

