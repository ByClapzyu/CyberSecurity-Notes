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
- **Swap** (intercambio): Si la mesa se llena y un Chef necesita poner una olla nueva, el jefe de cocina agarra algo que no este usando, la quita de la mesa y la lleva a la despensa. Esto libera espacio en la mesa (RAM).
- **Thrashing** (muerte por lentitud): Si tenemos poca RAM, el jefe de cocina pasa mas tiempo corriendo a la bodega y volviendo (moviendo datos entre RAM y Disco) que cocinando. Esto pone la PC lentisima.

Angulo de Seguridad
- Segmentation Fault (Violacion de Segmento):  SI el Chef A intenta agarrar un tomate que esta en el cuadro del Chef B, el jefe de cocina lo ve inmediatamente, le da un golpe y lo expulsa de la cocina. El programa se cierra de golpe (**segfault**). Esto protege los datos de un programa contra otro.
- **Buffer Oberflow*** (Desbordamiento de Búfer):  Imagina que el chef tiene un tazón pequeño (un espacio de memoria reservado) para echar agua. Un atacante malicioso vierte 5 lt de agua cuando el tazón solo soporta 1 lt. El agua desborda y moja la receta del chef de al lado (sobrescribe intrucciones de momoria adyacente). Si el atacante es listo, no derrama agua sino **instrucciones maliciosas**. Asi cuando el Chef (CPU) vaya a leer la receta mojada, leera las instrucciones del hacker. ( Muy usado)
- **Memory Leak** (Fuga de memoria): Un Chef usa un plato, termina de usarlo, pero no lo lava y lo devuelve. Saca otro, lo usa y no lo devuelve. Con el tiempo la cocina se queda sin platos (RAM llena) y el sistema colapsa, aunque no este haciendo nada pesado. Es un error de programacion común.
- 