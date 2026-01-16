# RAM (Random Access Memory) vs Memoria Virtual

La **RAM física es el hardware real** (los módulos verdes que se conectana a la placa madre). Es ultra rápida pero volátil (se borra al apagar). Hay que recordar  que el **kernel no deja que los programas toquen la RAM física directamente** (por el user space). En su lugar, el kernel usa **Memoria Virtual**.

- El kenel hace una ilusión: Donde el kenel le dice a chrome 
