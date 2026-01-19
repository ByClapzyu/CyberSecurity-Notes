
# Dirección de retorno

Es una dirección de memoria hexadecimal almacenada en el Stack. Su función es decirle a la CPU exactamente a que línea de código debe regresar una vez que termine de ejecutar una función.

**Flujo de ejecución**

Los programas se ejecutan línea por línea y la CPU usa un registro especial llamado **Instruction Pointer** (**EIP / RIP**) que siempre apunta la intrucción que se está ejecutando en el momento.

- 1 La llamada: Cuando un programa principal llama a una función la CPU deb
# Stack vs Heap

# Stack (Pila)

**Que es**: El Stack es la memoria rápida y ordenada **LIFO** (Last in, First Out), usado para funciones temporales. 

**Contenido**: Esta suele contener las **variable locales** y la **dirección de retorno** (a dónde ir cuando acabe la función) . 

**Riesgo**:Si un atacante llega a llenar una variable con más datos de los que caben (Overflow), se puede desbordar hacia abajo y sobrescribir la dirección de retorno,. Esto puede permitir tener el control de donde salta la CPU.

# Heap (Montón)

**Que es**:  Es la memoria dinamica y desordenada para datos grandes o de larga duración. Esta es gestionada de manera manual ya que el programador debe reservar y liberar espacio.

**Riesgo**: Fuga de memoria (Memory Leaks) si no se limpia.
