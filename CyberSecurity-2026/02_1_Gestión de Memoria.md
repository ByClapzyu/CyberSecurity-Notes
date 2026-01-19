
# Stack vs Heap

# Stack (Pila)

**Que es**: El Stack es la memoria rápida y ordenada **LIFO** (Last in, First Out), usado para funciones temporales. 

**Contenido**: Esta suele contener las **variable locales** y la **dirección de retorno** (a dónde ir cuando acabe la función) . 

**Riesgo**:Si un atacante llega a llenar una variable con más datos de los que caben (Overflow), se puede desbordar hacia abajo y sobrescribir la dirección de retorno,. Esto puede permitir tener el control de donde salta la CPU.

# Heap (Montón)

**
