## Historia
Håkon Wium Lie, trabajando en el CERN junto a Tim Berners-Lee, propuso las **Hojas de Estilo en Cascada (CSS)** para separar la estructura del contenido de su presentación, resolviendo los problemas de desorden visual en la web.  
**Internet Explorer 3** fue el primer navegador en implementarlo, aunque con una especificación cerrada.

## Sintaxis básica
```css
selector {
    propiedad: valor;
}
```

## Especificidad y Cascada
La importancia de las reglas CSS se organiza de la siguiente manera (de mayor a menor prioridad):
- `!important`
- Estilos **inline**
- ID (`#`)
- Clases (`.`), atributos y pseudo-clases
- Elementos y pseudo-elementos
- Selector universal (`*`)

## Herencia
No todos los atributos se heredan. Para heredar un valor específico, usa la propiedad `inherit`.

## Selectores
- **Por etiquetas**: Puedes seleccionar un elemento directamente (ej. `h1` para todos los `<h1>`).
- **Por clases**: Se utiliza un punto (`.`) antes del nombre de la clase (ej. `.mi-clase`).
- **Por ID**: Se utiliza un `#` antes del nombre del ID (ej. `#mi-id`).
- **Por atributos**: Se seleccionan elementos con atributos específicos (ej. `[type="text"]`).

### Selectores principales CSS
### Básicos
- `* { }`: Selector universal. Afecta todos los elementos.
- `p { }`: Selector de elemento. Afecta todos los elementos `<p>`.
- `.clase { }`: Selector de clase. Afecta todos los elementos con la clase especificada.
- `#id { }`: Selector de ID. Afecta el elemento con el ID especificado.
- `[type="text"] { }`: Selector de atributo. Afecta los elementos con el atributo `type="text"`.

### Combinadores
- `div p { }`: Selector descendiente. Afecta todos los `<p>` dentro de un `<div>`.
- `div > p { }`: Selector de hijo directo. Afecta los `<p>` que son hijos directos de un `<div>`.
- `div + p { }`: Selector de hermano adyacente. Afecta el primer `<p>` inmediatamente después de un `<div>`.
- `div ~ p { }`: Selector de hermanos generales. Afecta todos los `<p>` que son hermanos de un `<div>`.

### Pseudo-clases
- `:hover`: Se activa cuando el elemento es hovered.
- `:focus`: Se activa cuando el elemento recibe enfoque.
- `:first-child`: Se aplica al primer hijo de un elemento.
- `:last-child`: Se aplica al último hijo de un elemento.
- `:nth-child(n)`: Se aplica al n-ésimo hijo de un elemento.

### Pseudo-elementos
- `::before`: Se utiliza para insertar contenido antes del contenido de un elemento.
- `::after`: Se utiliza para insertar contenido después del contenido de un elemento.
- `::first-letter`: Se aplica a la primera letra de un elemento.
- `::selection`: Se aplica al texto seleccionado de un elemento.


- - - 
 **Píxeles**: `50px`, `100px`  
   Una unidad común de medición en el mundo digital.  
   Ejemplo: Una pantalla 4K es de 3840px por 2160px.
 
 **Porcentaje**: `50%`, `100%`  
   Una medición relativa.  
   Ejemplo: `width: 50%` significa el 50% del ancho de la página (o del contenedor si está dentro de uno).
 
 **em / rem**: `1em`, `1rem`  
   Mediciones relativas útiles para la accesibilidad.  
   - `em`: relativo al tamaño de fuente del elemento (por ejemplo, `2em` significa 2 veces el tamaño de fuente).
   - `rem`: relativo al tamaño de fuente de la página (16px por defecto; `2rem` significa 2 * 16px = 32px).
### Box Model CSS
```css
.selector {
    /* Content */
    width: 200px; /* Establece el ancho del elemento */
    height: 100px; /* Establece la altura del elemento */
    
    /* Padding */
    padding: 10px; /* Padding en todos los lados (arriba, derecha, abajo, izquierda) */
    padding: 10px 20px; /* Padding vertical 10px, horizontal 20px */
    padding: 10px 20px 15px 25px; /* Padding: arriba 10px, derecha 20px, abajo 15px, izquierda 25px */
    
    /* Border */
    border: 1px solid black; /* Establece un borde de 1px, color negro y estilo sólido */
    border-radius: 5px; /* Bordes redondeados con un radio de 5px */
    
    /* Margin */
    margin: 10px; /* Espacio fuera del borde, 10px en todos los lados */
    
    /* Box sizing */
    box-sizing: border-box; /* Incluye padding y border en el cálculo del width/height */
    
    /* Background */
    background-color: lightblue; /* Establece un color de fondo */
    background-image: url('image.jpg'); /* Imagen de fondo */
    background-size: cover; /* La imagen de fondo cubre todo el área del elemento */
    
    /* Font */
    font-family: Arial, sans-serif; /* Define la fuente del texto */
    font-size: 16px; /* Tamaño de la fuente */
    color: #333; /* Color del texto */
    
    /* Display */
    display: flex; /* Utiliza el modelo de diseño Flexbox */
    justify-content: center; /* Centra el contenido horizontalmente */
    align-items: center; /* Centra el contenido verticalmente */
}
```
### Flexbox CSS
Flexbox es un modelo de layout unidimensional para organizar elementos en filas o columnas. El contenedor padre controla el espacio y alineación de los elementos hijos.

==Completar==
- mirar flex y order
```css
.container {
    display: flex; /* o inline-flex */
}
```
## Propiedades del Contenedor
### Dirección y Flujo
```css
.container {
    flex-direction: row | row-reverse | column | column-reverse;
    flex-wrap: nowrap | wrap | wrap-reverse;
    /* Shorthand */
    flex-flow: row wrap;
}
```
### Alineación
```css
.container {
    /* Alineación en eje principal */
    justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
    
    /* Alineación en eje transversal */
    align-items: flex-start | flex-end | center | stretch | baseline;
    
    /* Alineación de líneas múltiples */
    align-content: flex-start | flex-end | center | space-between | space-around | stretch;
    
    /* Espaciado entre elementos */
    gap: 10px;
    gap: 10px 20px; /* row-gap column-gap */
}
```
## Propiedades de los Items
### Orden y Flexibilidad
```css
.item {
    /* Orden de aparición (default: 0) */
    order: 1;
    
    /* Flexibilidad */
    flex-grow: 0;   /* Capacidad de crecer */
    flex-shrink: 1; /* Capacidad de encogerse */
    flex-basis: auto; /* Tamaño base */
    
    /* Shorthand */
    flex: 0 1 auto; /* grow shrink basis */
    
    /* Alineación individual */
    align-self: auto | flex-start | flex-end | center | stretch;
}
```
## Patrones Comunes
### Distribución Equitativa
```css
.equal-items {
    display: flex;
    gap: 10px;
}
.equal-items > * {
    flex: 1;
}
```
### Sidebar con Contenido
```css
.layout {
    display: flex;
    gap: 20px;
}
.sidebar {
    flex: 0 0 200px;
}
.content {
    flex: 1;
}
```
### Footer Sticky
```css
body {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}
.content {
    flex: 1;
}
.footer {
    flex-shrink: 0;
}
```

## Layout
Originalmente, los diseños web se basaban en tablas (según David Siegel’s "Creating Killer Websites").
- ### Display CSS

```css
.elemento {
    display: block; /* elemento de bloque */
    display: inline; /* elemento en línea */
    display: inline-block; /* híbrido */
    display: none; /* oculta el elemento */
}
```
- ### Position CSS

- ### Grid CSS
El modelo de **CSS Grid** es una técnica de diseño bidimensional que permite crear estructuras de página más complejas con facilidad. Utiliza una cuadrícula donde puedes definir filas y columnas para organizar los elementos.

### Propiedades del contenedor

- **`display: grid;`**: Define el contenedor como un **grid**. Todos los elementos hijos dentro de este contenedor se alinearán en un grid.
- **`grid-template-columns: repeat(3, 1fr);`**: Define las columnas del grid. En este caso, hay **3 columnas** de tamaño **igual** (`1fr` significa que cada columna tiene una fracción del espacio disponible). Usar `repeat(3, 1fr)` es equivalente a escribir `1fr 1fr 1fr`.
- **`grid-template-rows: auto;`**: Define las filas del grid. En este ejemplo, se usa `auto`, lo que significa que las filas se ajustarán automáticamente al contenido dentro de ellas.
- **`gap: 20px;`**: Define el **espacio** entre los elementos dentro del grid (se aplica tanto entre columnas como filas).
- **`grid-template-areas`**: Permite nombrar áreas del grid. En el ejemplo, se define una estructura de 3 filas y 3 columnas:
  - La primera fila tiene 3 celdas ocupadas por el área **`header`**.
  - La segunda fila tiene **`sidebar`** en la primera columna y **`main`** en las dos siguientes.
  - La tercera fila tiene 3 celdas ocupadas por **`footer`**.
### Propiedades de los elementos dentro del grid
- **`grid-column: 1 / 3;`**: Define que el **elemento** debe ocupar desde la columna 1 hasta la columna 2, abarcando así dos columnas. Es equivalente a decir que el elemento ocupa las columnas 1 y 2.
- **`grid-row: 1 / 2;`**: Define que el **elemento** debe ocupar la fila 1. En este caso, es una fila única.
- **`grid-area: header;`**: Asigna el **elemento** al área llamada `header` que se ha definido en `grid-template-areas`.
### Ejemplo
Imaginemos que estamos creando una página con un **header**, **sidebar**, **main content**, y un **footer**.

```css
.contenedor {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: auto;
    gap: 20px;
    grid-template-areas: 
        "header header header"
        "sidebar main main"
        "footer footer footer";
}

.header {
    grid-area: header;
    background-color: #f1f1f1;
}

.sidebar {
    grid-area: sidebar;
    background-color: #ddd;
}

.main {
    grid-area: main;
    background-color: #bbb;
}

.footer {
    grid-area: footer;
    background-color: #333;
    color: white;
}
```
### Tipografía CSS
- **Fallbacks**: Se pueden definir fuentes alternativas por si la principal no está disponible.
```css
.texto {
    font-family: Arial, sans-serif;
    font-size: 16px;
    font-weight: bold;
    line-height: 1.5;
    text-align: center;
    text-decoration: underline;
    text-transform: uppercase;
    letter-spacing: 2px;
}
```


### Colores y Fondos CSS
- Definir colores y fondos con nombres, hexadecimales, RGB, etc.
 color rgba legacy |  rgb(n1 n2 n3 / opacidad(opcional)) moderno | trasparent palabra clave | oklch(mas moderno) && hsl |  ==Encontrar hoja de colores==

```css
.selector {
    /* Colores */
    color: #ff0000;                      /* Color en hexadecimal */
    color: rgb(255, 0, 0);               /* Color en RGB */
    color: rgba(255, 0, 0, 0.5);         /* Color en RGBA con transparencia */
    color: hsl(0, 100%, 50%);            /* Color en HSL */
    -webkit-text-fill-color: transparent; /* Texto transparente (para usar con background-clip) */
    text-stroke: 1px yellow;              /* Borde del texto */
    text-emphasis-color: red;             /* Color de énfasis en el texto */

    /* Fondos */
    background-color: #fff;               /* Color de fondo en hexadecimal */
    background-image: url('imagen.jpg');  /* Imagen de fondo */
    background-repeat: no-repeat;         /* Evita la repetición del fondo */
    background-position: center;          /* Posición del fondo */
    background-size: cover;               /* Ajusta el tamaño del fondo */
    background-attachment: fixed;         /* Fija el fondo en su lugar (efecto parallax) */
    background-blend-mode: multiply;      /* Modo de mezcla del fondo */

    /* Gradientes */
    background: linear-gradient(to right, #fff, #000); /* Degradado lineal */
    background: radial-gradient(circle, #fff, #000);   /* Degradado radial */

    /* Colores de bordes y contornos */
    border-color: black;                  /* Color del borde */
    outline-color: blue;                  /* Color del contorno externo */

    /* Sombras */
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5); /* Sombra en el texto */
    box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.3); /* Sombra en el contenedor */

    /* Filtros de color */
    filter: hue-rotate(90deg) saturate(1.5); /* Rotación de tono y saturación */
    backdrop-filter: blur(5px) brightness(0.8); /* Filtro de fondo (efecto de desenfoque y brillo) */

    /* Nuevos atributos específicos */
    accent-color: purple;                 /* Color de acento para elementos de formulario */
    caret-color: red;                     /* Color del cursor en inputs y áreas de texto */
    scrollbar-color: blue orange;         /* Color de la barra de desplazamiento */
}
```

## Transformaciones y Transiciones CSS
Las **transformaciones** y **transiciones** en CSS permiten modificar y animar los elementos de una página web, creando efectos visuales fluidos e interactivos.

### Transformaciones

- **`transform: translate(50px, 100px);`**  
  Desplaza el elemento en el eje X e Y. En este caso, el elemento se moverá **50px** hacia la derecha y **100px** hacia abajo.

- **`transform: rotate(45deg);`**  
  Rota el elemento **45 grados** en el sentido de las agujas del reloj.

- **`transform: scale(1.5);`**  
  Aumenta el tamaño del elemento en un **1.5 veces** su tamaño original. Puedes usar valores menores a 1 para reducir el tamaño.

### Transiciones

Las **transiciones** permiten que un cambio en una propiedad de un elemento ocurra de forma suave durante un período de tiempo.

- **`transition: all 0.3s ease;`**  
  Esta transición aplica a **todas** las propiedades del elemento y toma **0.3 segundos** para completarse, utilizando una curva de aceleración **"ease"**, que comienza lento, acelera y luego desacelera.

- **`transition: background-color 0.3s ease-in-out;`**  
  Esta transición afecta solo al cambio de color de fondo (**`background-color`**) y dura **0.3 segundos**. La curva de aceleración **"ease-in-out"** hace que el cambio comience y termine de forma suave.

### Animaciones

Las **animaciones** en CSS permiten realizar movimientos y transformaciones más complejas y controladas a lo largo del tiempo.

- **`@keyframes slide`**  
  Define una animación llamada **`slide`**.  
  - **`from { transform: translateX(0); }`**: El elemento comienza en su posición original (sin desplazarse).
  - **`to { transform: translateX(100px); }`**: El elemento se mueve **100px** hacia la derecha.

- **`animation: slide 2s infinite;`**  
  Aplica la animación **`slide`** al elemento, durando **2 segundos** por ciclo. La animación se repite **infinitamente**.

### Ejemplo Visual

Imagina un cuadro que se desplaza de izquierda a derecha y cambia de color al hacer hover:

```css
.elemento {
    width: 100px;
    height: 100px;
    background-color: red;
    transition: background-color 0.3s ease;
}

.elemento:hover {
    background-color: blue;
    transform: translate(50px, 0); /* Desplaza el cuadro 50px hacia la derecha */
}
```
## Debug CSS
El uso de **`outline`** en CSS es una técnica común para depurar y visualizar los límites de los elementos en una página web. Es especialmente útil cuando estás trabajando con layouts complejos o cuando necesitas ver cómo se alinean los elementos.

```css
/* Outline para debug */
* {
    outline: 1px solid red !important;
}
```

## Otros Conceptos y Herramientas

- **Reset / Normalizer**: Uso de archivos para normalizar estilos entre navegadores.
- **Cheatsheet User Agent**: Estilos por defecto de los navegadores.
- **Comentarios**: Los comentarios en CSS se escriben como `/* comentario */`.
- **Paleta de Colores**: Al pasar el cursor sobre el valor de color en VS, se muestra una paleta de colores.
- **Borders**: El borde se define con tres propiedades: `tamaño`, `estilo` y `color` (puedes usar `currentcolor` para usar el color actual).

## Recomendaciones
- Es recomendable incluir los estilos CSS dentro del archivo **`<head>`** del documento HTML para mantener el código organizado y fácilmente accesible.

Esta estructura proporciona una organización clara y accesible de los conceptos fundamentales de CSS, con enlaces a temas específicos para profundizar más en cada área.
- - - 
## ***Sources:***
- Biblioteca y Tutorial(https://manz.dev/)
-  Standard Dessarrollo Web(https://developer.mozilla.org/en-US/)
- Estilos en tiempo real(https://codi.link/%7C%7C)

Catalogos:
- Catalogo y Apuntes CSS(https://htmlcheatsheet.com/css/)
- Catalogo de Fuentes CSS(https://kagi.com/search?q=fonts.googlefont)
- Catalogo de Diseños CSS(https://csszengarden.com/pages/alldesigns/)