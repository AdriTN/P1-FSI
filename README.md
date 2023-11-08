README - Práctica 1 FSI

Estudiantes: Santiago Ramirez Olivares y Adrián Talavera Naranjo


Tareas incluidas:

1. Programar la "Búsqueda de Ramificación y Acotación".
2. Programar la "Búsqueda de Ramificación y Acotación con Subestimación" usando la distancia en línea recta como heurística. 
3. Comparar la cantidad de nodos expandidos en ambas estrategias.

La primera estrategia es la "Búsqueda de Ramificación y Acotación," una técnica no informada que prioriza los nodos de menor costo. La segunda es la "Búsqueda de Ramificación y Acotación con Subestimación," una estrategia informada que combina el costo acumulado con una estimación heurística. Se utiliza el grafo de las ciudades de Rumanía como ejemplo.


Cambios en 'run.py':

Se ha agregado la funcion measure_time que devuelve el recorrido de cada algortimo de búsqueda y el tiempo de ejecución de cada uno.


Cambios en 'search.py':

Se han implementado los nuevos algoritmos de búsqueda (branch_and_bound y branch_and_bound_subestimation), que son útiles para problemas de búsqueda con costos.

Se han añadido nuevas métricas (nodos generados, nodos visitados y coste).


Cambios en 'utils.py':

Se ha mejorado el método 'pop' de la clase 'FIFOQueue' para simplificar la eliminación de elementos.

Se han implementado dos nuevas colas de prioridad, 'BranchAndBoundQueue' e 'InformedPriorityQueue', que se utilizan en los algoritmos 'branch_and_bound' y 'branch_and_bound_subestimation' respectivamente.


Funcionamiento 'BranchAndBoundQueue':

- Método '__init__': Inicializa la cola y el nodo inicial.

- Método 'append': Agrega un elemento al final de la cola, pero haciendo una llamada al método 'extend'.

- Método '__len__': Devuelve la longitud de la cola.

- Método 'extend': Añade los nodos vecinos del actual a la cola y reordena dicha cola según el coste.

- Método 'pop': Extrae el primer elemento de la cola.

Funcionamiento 'InformedPriorityQueue':

Comparte los métodos de la clase anterior. 

La única diferencia reside en el método 'extend', el cual ahora tiene en cuenta la heurística del problema (nuevo atributo de la clase)

La heurística proporcionada emplea el Teorema de Pitágoras para calcular la distancia que hay entre el nodo actual y el nodo destino.
