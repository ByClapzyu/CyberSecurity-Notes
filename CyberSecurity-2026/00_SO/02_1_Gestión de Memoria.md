
# Dirección de retorno

Es una dirección de memoria hexadecimal almacenada en el Stack. Su función es decirle a la CPU exactamente a que línea de código debe regresar una vez que termine de ejecutar una función.

**Flujo de ejecución**

Los programas se ejecutan línea por línea y la CPU usa un registro especial llamado **Instruction Pointer** (**EIP / RIP**) que siempre apunta la intrucción que se está ejecutando en el momento.

- 1 **llamada**: Cuando un programa principal llama a una función la CPU debe detener el flujo principal para ir a ejecutar el código de esa función.

- 2 **Guardado**: Antes de saltar a la función, la CPU guarda la dirección de la intrucción siguiente en el Stack. Esto es lo que llamamos dirección de retorno. Se puede ver como el punto de guardado.

- 3 **Ejecución**: La función se ejecuta. Las variables locales se guardan en el Stack, justo encima o antes de la dirección de retorno.

- 4 **Retorno**: Cuando la función termina, la CPU va al Stack, lee esa dirección guardada, la carga en el intruction pointer y salta de vuelta a esa linea para continual con el programa principal.

Como en la memoria RAM (Stack), las variables locales y la direccion de retorno están pegadas fisicamente, una al lado de la otra.

El programa serva 8 bytes de variable local (buffer) y justo despues de esas 8, está guardada la dirección de retorno. Entonces si el usuario intruce 12 bytes de datos en la variable las primeras 8 se llenan de forma correcta y las otra 4 invaden el espacio se desborda y sobrescriben los datos de forma adyacente.
# Stack vs Heap

# Stack (Pila)

**Que es**: El Stack es la memoria rápida y ordenada **LIFO** (Last in, First Out), usado para funciones temporales. 

**Contenido**: Esta suele contener las **variable locales** y la **dirección de retorno** (a dónde ir cuando acabe la función) . 

**Riesgo**:Si un atacante llega a llenar una variable con más datos de los que caben (Overflow), se puede desbordar hacia abajo y sobrescribir la dirección de retorno,. Esto puede permitir tener el control de donde salta la CPU.

# Heap (Montón)

**Que es**:  Es la memoria dinamica y desordenada para datos grandes o de larga duración. Esta es gestionada de manera manual ya que el programador debe reservar y liberar espacio.

**Riesgo**: Fuga de memoria (Memory Leaks) si no se limpia.
