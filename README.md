# Búsqueda Binaria Explicada: Un Algoritmo para Encontrar lo que Necesitas

## Introducción

La búsqueda binaria es uno de los algoritmos más eficientes para encontrar un elemento en una lista ordenada. En este video, te explico cómo funciona paso a paso y cómo puedes implementarla en tu propio código.

## Tabla de contenidos

- [¿Qué es la búsqueda binaria?](#¿que-es-la-busqueda-binaria?)
- [Cómo funciona paso a paso](#como-funciona-paso-a-paso)
- [Implementación en código](#implementacion-en-codigo)
- [Análisis de la eficiencia](#analisis-de-la-eficiencia)
- [Conclusión ](#conclusión)
- [License](#license)
- [Contact](#contact)

## ¿Qué es la búsqueda binaria?

La búsqueda binaria es un algoritmo eficiente para encontrar la posición de un elemento en una lista ordenada. En lugar de buscar secuencialmente cada elemento, la búsqueda binaria divide el conjunto en mitades repetidamente hasta encontrar el objetivo o determinar que no existe.

## Cómo funciona paso a paso

1. Lista ordenada: El algoritmo requiere que la lista esté ordenada previamente.

2. Inicio, fin y medio: Se establecen dos índices, inicio y fin, que representan los extremos de la lista. Luego, se calcula el índice del medio:

```
medio = (inicio + fin) / 2
```

3. Comparación: 
- Si el valor en el índice medio es igual al valor buscado, entonces has encontrado el elemento.
- Si el valor buscado es menor que el valor en el índice medio, se reduce el rango de búsqueda descartando la mitad superior (es decir, fin = medio - 1).
- Si el valor buscado es mayor, se descarta la mitad inferior (inicio = medio + 1).

4. Repetición: Este proceso se repite, recalculando el índice medio y reduciendo el rango de búsqueda en cada iteración, hasta que se encuentra el elemento o el rango de búsqueda se vuelva inválido (inicio > fin).

## Implementación en código

```python
def busqueda_binaria(lista, objetivo):
    inicio = 0
    fin = len(lista) - 1

    while inicio <= fin:
        medio = (inicio + fin) // 2 # División hacia abajo
        if lista[medio] == objetivo:
            return medio  # Elemento encontrado
        elif lista[medio] < objetivo:
            inicio = medio + 1  # Buscar en la mitad derecha
        else:
            fin = medio - 1  # Buscar en la mitad izquierda

    return -1  # Elemento no encontrado
```

### Ejemplo de uso
```python
lista = [1, 3, 5, 7, 9, 11, 13, 15, 17]
objetivo = 7
resultado = busqueda_binaria(lista, objetivo)
print(f'El elemento {objetivo} está en el índice {resultado}')  # Salida: El elemento 7 está en el índice 3
```


## Análisis de la eficiencia

- Tiempo de ejecución: En cada iteración, el algoritmo reduce el espacio de búsqueda a la mitad. Por lo tanto, si el tamaño de la lista es 𝑛, esto da como resultado un tiempo de ejecución de 𝑂(log 𝑛), lo que hace que sea mucho más eficiente que una búsqueda secuencial, que es 𝑂(𝑛).

- Condiciones: Sin embargo, la búsqueda binaria solo funciona en listas ordenadas. Si la lista no está ordenada, el tiempo de ordenar la lista previamente es 𝑂(𝑛 log 𝑛), lo que impacta la eficiencia total si este paso es necesario.

## Conclusión 

La búsqueda binaria es un algoritmo esencial para la búsqueda eficiente en listas ordenadas. Su capacidad para reducir drásticamente el número de comparaciones lo convierte en una técnica ideal para grandes volúmenes de datos, siempre que se cumpla el requisito de que la lista esté previamente ordenada. Es especialmente útil en aplicaciones donde las búsquedas repetitivas son comunes y la lista rara vez cambia.

## License

This project is licensed under the MIT License. For more details, see [LICENSE](https://github.com/CompilandoYT/20240914-Busqueda-Binaria/blob/main/LICENSE)

## Contact