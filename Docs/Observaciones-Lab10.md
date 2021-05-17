# Laboratorio No. 10

## Autores :writing_hand:
* Hernán Buitrago
    * hf.buitrago10@uniandes.edu.co
    * 201512807

## Preguntas :page_facing_up:

**1. ¿Qué instrucción se usa para cambiar el límite de recursión de Python?**

La función ```setrecursionlimit()``` de la librería ```sys``` se utiliza para cambiar el límite de recursión de Python.

**2. ¿Por qué considera que se debe hacer este cambio?**

Dado que el algoritmo dijkstra es un algoritmo recursivo, si se quiere determinar la ruta más corta desde un vértice a los demás vertices del grafo es posible que se supere el límite de recursión por defecto de Python cuando el número de vértices y arcos del grafo sea lo suficientemente grande, de modo que se produciría un ```Runtime error``` al exceder el límite de recursión. Por esta razón, es importante cambiar el límite de recursión establecido por defecto.

**3. ¿Cuál es el valor inicial que tiene Python como límite de recursión?**

El valor inicial del límite de recursión de Python por defecto es 1000.

**4. ¿Qué relación cree que existe entre el número de vértices, arcos y el tiempo que toma la operación 4?**

|  | Vértices | Arcos | Tiempo |
| --- | --- | --- | --- |
| ```bus_routes_50.csv``` | 74 | 73 | 37.20612 [ms] |
| ```bus_routes_150.csv``` | 146 | 146 | 55.58470 [ms] |
| ```bus_routes_300.csv``` | 295 | 382 | 84.90818 [ms] |
| ```bus_routes_1000.csv``` | 984 | 1633 | 363.12968 [ms] |
| ```bus_routes_2000.csv``` | 1954 | 3560 | 1170.00451 [ms] |
| ```bus_routes_3000.csv``` | 2922 | 5773 | 2441.46861 [ms] |
| ```bus_routes_7000.csv``` | 6829 | 15334 | 8348.04481 [ms] |
| ```bus_routes_10000.csv``` | 9767 | 22758 | 22003.47461 [ms] |
| ```bus_routes_14000.csv``` | 13535 | 32270 | 39771.19583 [ms] |

Se observa que el tiempo de ejecución de la operación 4 aumenta conforme aumenta el número de vertices y arcos del grafo.

**5. ¿Qué características tiene el grafo definido?**

El grafo es un grafo dirigido, en el que cada arco tiene una dirección desde un vértice hacia otro. Cada vértice representa una parada y cada arco una ruta desde una parada a otra, donde el peso de cada arco es la distancia entre dos paradas.

**6. ¿Cuál es el tamaño inicial del grafo?**

```Python
def newAnalyzer():
    analyzer = {'stops': None,
                'connections': None,
                'components': None,
                'paths': None}

    analyzer['stops'] = m.newMap(numelements=14000,
                                 maptype='PROBING',
                                 comparefunction=compareStopIds)

    analyzer['connections'] = gr.newGraph(datastructure='ADJ_LIST',
                                          directed=True,
                                          size=14000,
                                          comparefunction=compareStopIds)
    return analyzer
```

Se observa que el tamaño inicial utilizado para la implementación del grafo es 14000.

**7. ¿Cuál es la estructura de datos utilizada?**

```Python
def newAnalyzer():
    analyzer = {'stops': None,
                'connections': None,
                'components': None,
                'paths': None}

    analyzer['stops'] = m.newMap(numelements=14000,
                                 maptype='PROBING',
                                 comparefunction=compareStopIds)

    analyzer['connections'] = gr.newGraph(datastructure='ADJ_LIST',
                                          directed=True,
                                          size=14000,
                                          comparefunction=compareStopIds)
    return analyzer
```

Se observa que la estructura de datos utilizada para la implmentación del grafo es una lista de adyacencia.

**8. ¿Cuál es la función de comparación utilizada?**

```Python
def compareStopIds(stop, keyvaluestop):
    """
    Compara dos estaciones
    """
    stopcode = keyvaluestop['key']
    if (stop == stopcode):
        return 0
    elif (stop > stopcode):
        return 1
    else:
        return -1
```

Se observa que la función de comparación utilizada para la implementación del grafo es ```compareStopIds```.
