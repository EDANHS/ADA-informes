Se realiza foro de la semana 13, el cual no se hizo ni publicación ni comentarios, tema: "El problema del camino más corto con Dijkstra"
Se adjunta lo expuesto en el foro:

El problema del camino más corto

Este es un problema para encontrar la ruta más corta para ir desde un nodo fuente s y todos los nodos del grafo. Para ello existen distintos algoritmos que solucionan el problema, en un grafo G = (V,E) y un nodo fuente s, se puede resolver el problema con Dijkstra, Bellman-Ford y Floyd-Warshall, en este foro se hablará del algoritmo de Dijkstra.
El algoritmo de Dijkstra: Este problema tiene como restricción que todos los arcos pertenecientes a E sean positivos, ¿esto por qué?, para responder está pregunta imaginemos que tenemos un costo negativo en un arco arbitrario, y luego en los siguientes nodos arcos con peso muy grande, si elegimos este camino podemos toparnos que el costo aumenta mucho, ya que el algoritmo se basa en escoger el arco con peso menor, es por ello que se debe trabajar solo en grafos con arcos de peso positivo.

Como funciona el algoritmo:
1.	Inicializar cada distancia con valor infinito con excepción de nuestro nodo fuente s que es 0 en una lista auxiliar.
2.	Recorrer los nodos adyacentes a s, con excepción de los que ya fueron visitados
3.	Se calcula la distancia menor viendo si la distancia actual más una nueva es la menor entre todas.
4.	Se marca el nodo como visitado y sigue los mismos pasos para los siguientes nodos. 
Para su complejidad temporal tenemos que:
Primero que nada, hacemos una iteración de la cola $Q$, esta se ejecuta en a lo más $E$ veces, ya que almacena como máximo n-1 nodos. En el segundo caso, cuando revisamos las conexiones, se hace por un recorrido por la lista, como se revisan las conexiones, esto opera en tiempo E, finalmente, si lo implementamos con min-heap que es la mejor forma de reducir su tiempo de ejecución de O(V^2) a O(E*Log V), tenemos que el min-heap opera en O(log V) para sus operaciones, finalmente tenemos que en total Dijkstra funciona en tiempo O(E) + O(E * log V), siendo E*log V por revisar las conexiones y extraer nodos. Tomando el mayor valor de ambos tenemos que el tiempo de ejecución del algoritmo de Dijkstra es O(E * log V).
