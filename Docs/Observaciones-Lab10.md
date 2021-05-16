# Laboratorio No. 10

## Autores :writing_hand:
* Hernán Buitrago
    * hf.buitrago10@uniandes.edu.co
    * 201512807

## Preguntas :page_facing_up:

**1. ¿Qué instrucción se usa para cambiar el límite de recursión de Python?**

La función ```setrecursionlimit()``` de la librería ```sys``` se utiliza para cambiar el límite de recursión de Python.

**2. ¿Por qué considera que se debe hacer este cambio?**

Dado que el algoritmo dijkstra es un algoritmo recursivo, es 

**3. ¿Cuál es el valor inicial que tiene Python como límite de recursión?**

El valor inicial del límite de recursión de Python por defecto es 1000.

**4. ¿Qué relación cree que existe entre el número de vértices, arcos y el tiempo que toma la operación 4?**

|  | Opción 4 |
| --- | --- |
| ```bus_routes_50.csv``` | 37.20612 [ms] |
| ```bus_routes_150.csv``` | 55.58470 [ms] |
| ```bus_routes_300.csv``` | 84.90818 [ms] |
| ```bus_routes_1000.csv``` | 363.12968 [ms] |
| ```bus_routes_2000.csv``` | 1170.00451 [ms] |
| ```bus_routes_3000.csv``` | 2441.46861 [ms] |
| ```bus_routes_7000.csv``` | 8348.04481 [ms] |
| ```bus_routes_10000.csv``` | 22003.47461 [ms] |
| ```bus_routes_14000.csv``` | 39771.19583 [ms] |

Se observa que el tiempo de ejecución de la operación 4 aumenta conforme aumenta el número de vertices y de arcos del grafo.

**5. ¿Qué características tiene el grafo definido?**

**6. ¿Cuál es el tamaño inicial del grafo?**

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

Se observa que la función de comparación utilizada para la implementación del grado es ```compareStopIds```.
