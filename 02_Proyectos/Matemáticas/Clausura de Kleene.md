**Tags:** #_Done
**MetaTags:** #Matemáticas #Gramatica #ToLink 
- - -
La **clausura de Kleene** se define formalmente en teoría de lenguajes formales como:

$$
A^* = \bigcup_{n=0}^{\infty} A^n
$$

donde:

* $A$ es un **alfabeto** o un **lenguaje** (un conjunto de cadenas sobre un alfabeto).
* $A^n$ denota el conjunto de todas las **concatenaciones de $n$** elementos de $A$, con $A^0 = \{\varepsilon\}$ (la cadena vacía).
* La operación $A^*$ incluye todas las cadenas que pueden formarse concatenando cero o más cadenas de $A$.

La definición en términos de cadenas:

> La clausura de Kleene de un lenguaje $A$ es el conjunto de todas las cadenas finitas (incluyendo la cadena vacía) que pueden obtenerse concatenando **cero o más** cadenas de $A$.


También se define la **clausura positiva**:

$$
A^+ = \bigcup_{n=1}^{\infty} A^n = A^* \setminus \{\varepsilon\}
$$

- - - 
#### ***Sources:***
