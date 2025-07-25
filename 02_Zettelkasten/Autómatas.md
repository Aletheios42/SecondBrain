**MetaTags:** #_Investigar
**Tags:** #Gramatica #Automatas #Programación #ToLink  
- - -
### simbolos de derivación

- Simbolos terminales
- simbolos no terminales
- Simbolo Inicial

### clasidficacion de gramaticas de chomsky

| Tipo | Lenguaje | Autómata               | Reglas prod. gramatical   |
| ---- | -------- | ---------------------- | ------------------------- |
| 0    | LRE      | Máquina de Turing      | α → β (sin restricciones) |
| 1    | LSC      | A. linealmente acotado | αAβ → αγβ                 |
| 2    | LLC      | A. con pila            | A → γ                     |
| 3    | LR       | A. finito              | A → aB o A → a            |

las gramaticas se utilizan para definir lenguajes.
los automatas para reconocer lenguajes formales.
explicar el operador perpendicular(pasar de un estado a otro)
### Automata
Los automatas son verificadores de lenguaje, no son actores como la gramatica.
Un automata es una quíntupla que reconoce un lenguaje:

$$
\text{DFA: } A = (Q, \Sigma, \delta, s, F)
$$
Donde:

- $Q$: Conjunto finito de estados.
- $\Sigma$: Alfabeto finito (símbolos de entrada).
- $\delta$: Función de transición, $\delta : Q \times \Sigma \to Q$. el producto cartesiano tambien se representa como tabla de trasiciones.
- $s$: Estado inicial, $s \in Q$.
- $F$: Conjunto de estados finales (o de aceptación), $F \subseteq Q$.

epsilon es la cadena vacia, explicar transiciones epsilon
estado sumidero: estado no final del que no lleva a ningun estado final

### DFA
Para que un automata sea Determinista DFA es necesario que la relacion $\delta$ sea aplicacion es decir, que sea una relacion total y univoca.
se define total como una relacion cuyo conjunto inicial es igual al dominio
se define univoca como que cada elemento del dominio solo tiene una corespondencia en la imagen


### NFA
Un automata no determinista, NFA es un automata cuya $\delta$ es una relación que no tiene que ser ni total ni univoca, 
==investigar los problemas np desde esta pespectiva==


### conversion de NFA a DFA.
Dado un Nfa  A= (Q, E, delta, s, F) , la clausura-e de un estado q € Q es el conjunto de estados q(prima) accesibles desde q sin consumir nigun simbolo de entrada.
es decir:
ponerlo en latex

- - - 
#### ***Sources:***