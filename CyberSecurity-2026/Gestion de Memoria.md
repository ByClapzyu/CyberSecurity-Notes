# RAM (Random Access Memory) vs Memoria Virtual

La **RAM física es el hardware real** (los módulos verdes que se conectana a la placa madre). Es ultra rápida pero volátil (se borra al apagar). Hay que recordar  que el **kernel no deja que los programas toquen la RAM física directamente** (por el user space). En su lugar, el kernel usa **Memoria Virtual**.

- El **kenel hace una ilusión**: Donde el kenel le dice a chrome "toma, aqui esta estos 4 GB de memoria continuos para que ocupes tú"
- La **realidad**:  En la física, esos 4GB están fragmentados: un pedazo está en la RAM, otro pedazo está en el **Disco Duro (**Swap**), y otro pedazo ni siquiera existe todavía.
- **Paginación** (Paging): El kernel divide la memoria en pequeños bloques llamados paginas (usualmente de 4KB).
- **MMU (Memory Managment Unit)**: Es un chip en la CPU que traduce en tiempo real las direcciones virtuales (lo que ve el programa) a direcciones fisicas (donde esta realmente el dato en el chip de RAM).

Analogía (Mesa de Trabajo del Chef)

- **Chef**: CPU. Es quien trabaja y procesa.
- **Despensa**: Disco duro. Enorme cabe todo, pero está lejos y es lento ir a buscar cosas
- **Mesa de trabajo**: Es la RAM. Es pequeña, pero esta justo frente al Chef, tiene lo necesario a la mano.
- **Jefe de Cocina** : Es el Kenel
Hay 3 chefs (3 programas) compartiendo la misma mesa, el jefe de cocina dibuja lineas con cinta para dividir la mesa y asignar un cuadro a cada chef.