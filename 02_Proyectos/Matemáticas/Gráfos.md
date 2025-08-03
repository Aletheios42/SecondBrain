**MetaTags:** #_Done
**Tags:** #Matemáticas #ToLink 
- - -

Un grafo es un sistema para representar relaciones.
$$
G = (V, E) \quad \text{donde } V \text{ es el conjunto de vértices y } E \text{ el conjunto de aristas}
$$
### Tipos de grafos

* **Dirigido**:
  $E \subseteq V \times V$
* **No dirigido**:
  $E \subseteq \left\{ \{u, v\} \mid u, v \in V \right\}$
* **Ponderado**: cada arista tiene un peso
  $w : E \to \mathbb{R}$
* **Multigrafo**: se permiten múltiples aristas entre los mismos vértices
* **Grafo simple**: sin lazos ni múltiples aristas
### Representaciones comunes

* **Matriz de adyacencia**:
  $A \in \{0, 1\}^{|V| \times |V|}$
* **Lista de adyacencia**: diccionario o lista de listas (eficiente en espacio para grafos dispersos)
### Conceptos clave

* **Grado**: número de aristas incidentes a un vértice
* **Camino**: secuencia de vértices
  $$
  (v_0, v_1, \dots, v_k) \quad \text{tal que} \quad (v_i, v_{i+1}) \in E
  $$
* **Ciclo**: camino cerrado (inicio = fin)
* **Conexo**: existe un camino entre todo par de vértices
* **Árbol**: grafo acíclico conexo

- - - 
#### ***Sources:***