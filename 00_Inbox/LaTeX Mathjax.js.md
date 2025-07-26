**Tags:** #_Todo
**MetaTags:** #LenguajesDeMarcado #Productividad
- - -
LaTeX es un potente lenguaje de marcado, constituye un estándar universal para la producción de documentación científica. 

MathJax es una librería de JavaScript de código abierto diseñada para renderizar ecuaciones matemáticas en páginas web, especialmente aquellas escritas en LaTeX, MathML o Asciimath. Esta herramienta permite a los navegadores visualizar de manera correcta y consistente notación matemática, independientemente del navegador o dispositivo. Además, es compatible con Obsidian a través de plugins.

El objetivo es producir este tipo de apuntes:  
![[LaTeX_Potential.jpg]]

"La notación `{}` en LaTeX sirve como introducción al sintagma, lo que la hace ideal para expandir los argumentos complejos de una función. Ejemplo:  
\[
\frac{a + b}{c + d}
\]

## Operaciones Matemáticas  

| Descripción               | LaTeX                            | Renderizado                          |
| ------------------------- | -------------------------------- | ------------------------------------ |
| Suma                      | `a + b`                          | \( a + b \)                          |
| Resta                     | `a - b`                          | \( a - b \)                          |
| Multiplicación            | `a \times b`                     | \( a \times b \)                     |
| Producto escalar          | `a \cdot b`                      | \( a \cdot b \)                      |
| División                  | `a \div b`                       | \( a \div b \)                       |
| Fracción                  | `\frac{a}{b}`                    | \( \frac{a}{b} \)                    |
| Raíz cuadrada             | `\sqrt{a}`                       | \( \sqrt{a} \)                       |
| Raíz n-ésima              | `\sqrt[n]{a}`                    | \( \sqrt[n]{a} \)                    |
| Potencia (exponente)      | `x^n`                            | \( x^n \)                            |
| Logaritmo Natural         | `\ln(x)`                         | \( \ln(x) \)                         |
| Funciones trigonométricas | `\sin(x), \cos(x), \tan(x)`      | \( \sin(x), \cos(x), \tan(x) \)      |
| Coordenadas polares       | `r \cos(\theta), r \sin(\theta)` | \( r \cos(\theta), r \sin(\theta) \) |
| Binomio                   | `\binom{n}{k}`                   | \( \binom{n}{k} \)                   |
| Factorial                 | `n!`                             | \( n! \)                             |
| Sumatoria                 | `\sum_{i=1}^{n} a_i`             | \( \sum_{i=1}^{n} a_i \)             |
| Producto                  | `\prod_{i=1}^{n} a_i`            | \( \prod_{i=1}^{n} a_i \)            |
| Límites                   | `\lim_{x \to \infty} f(x)`       | \( \lim_{x \to \infty} f(x) \)       |
| Derivada ordinaria        | `\frac{d f}{d x}`                | \( \frac{d f}{d x} \)                |
| Derivada parcial          | `\frac{\partial f}{\partial x}`  | \( \frac{\partial f}{\partial x} \)  |
| Integral definida         | `\int_{a}^{b} f(x)\, dx`         | \( \int_{a}^{b} f(x)\, dx \)         |
| Integral indefinida       | `\int f(x)\, dx`                 | \( \int f(x)\, dx \)                 |


## Texto  
| Descripción                 | LaTeX                                                          | Renderizado                                                        |
| --------------------------- | -------------------------------------------------------------- | ------------------------------------------------------------------ |
| Texto en negrita            | `\textbf{lore ipsum}`                                          | **lore ipsum**                                                     |
| Texto en cursiva            | `\textit{lore ipsum}`                                          | *lore ipsum*                                                       |
| Texto normal                | `\text{lore ipsum}`                                            | \( \text{lore ipsum} \)                                            |
| Texto en negrita y cursiva  | `\textbf{\textit{lore ipsum}}`                                 | ***lore ipsum***                                                   |
| Texto en modo matemático    | `\text{lore ipsum}`                                            | \( \text{lore ipsum} \)                                            |
| Vector (con flecha)         | `\vec{a}`                                                      | \( \vec{a} \)                                                      |
| Ángulo entre dos vectores   | `\angle ABC`                                                   | \( \angle ABC \)                                                   |
| Ángulo medido               | `\measuredangle ABC`                                           | \( \measuredangle ABC \)                                           |
| Matrices                    | `\begin{bmatrix} a & b \\ c & d \end{bmatrix}`                 | \( \begin{bmatrix} a & b \\ c & d \end{bmatrix} \)                 |
| Función generalizada        | `f(x), g(x), h(x)`                                             | \( f(x), g(x), h(x) \)                                             |
| Función compuesta           | `f(g(x))`                                                      | \( f(g(x)) \)                                                      |
| Función definida por tramos | `f(x) = \begin{cases} a, & x < 0 \\ b, & x \geq 0 \end{cases}` | \( f(x) = \begin{cases} a, & x < 0 \\ b, & x \geq 0 \end{cases} \) |
| Color                       | `\textcolor{red}{lore ipsum}`                                  | <span style="color:red">lore ipsum</span>                          |

## Espacios  
| Descripción                 | LaTeX       | Renderizado     |
| --------------------------- | ----------- | --------------- |
| Espacio implícito           | `a\,b`      | \( ab \)        |
| Fusión                      | `a\!b`      | \( a\!b \)      |
| Espacio delgado             | `a\,b`      | \( a\,b \)      |
| Espacio normal              | `a\:b`      | \( a\:b \)      |
| Espacio grande              | `a\;b`      | \( a\;b \)      |
| Espacio cuádruple           | `a\quad b`  | \( a\quad b \)  |
| Espacio de cuádruple grande | `a\qquad b` | \( a\qquad b \) |

Además, para web tiene integración de CSS:
```css
.MJX-TEX {
	font-size: 180%;
}
```

- - - 
## ***Sources:***
- [Comprehensive Overview | LaTeX Mathjax Equation In Obsidian](https://www.youtube.com/watch?v=FA0z7oR7OWc)
- [MathJax Crash course](https://www.youtube.com/watch?v=Wdc-MA2M8Xg)