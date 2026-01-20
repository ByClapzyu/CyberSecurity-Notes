# Bandit 0

Para poder comenzar con bandit0, necesitamos acceder a traves de **SSH** usando el siguiente comando: 
- ssh bandit0@bandit.labs.overthewire.org -p 2220

Una vez adentro como se muestra en la pagina de OTW nos dice que "The password for the next level is stored in a file called readme located in the home directory."
Para resolver esto necesitamos llegar al home directory,  así que mi primer movimiento es realizar un **pwd** para saber en donde me encuentro, al visualizar que estoy dentro de  ***/home/bandit0***  realizo un **ls** para listar el contenido de home directory. Como se puede ver que esta el file readme antes de ver el contenido del archivo con **cat** procedo a saber que tipo de archivo es con **file** el resultado de esto es "readme: ASCII text" por lo cual este archivo contiene lenguaje humano. Antes del conseguir la contraseña checo cuantos bytes ocupa para darme idea que tanto puede venir con **du -b readme**, veo que pesa 438 bytes por lo cual se puede suponer que no tiene demasiado contenido.


  

