**Tags:** #_Todo
#CSS #DesarrolloWeb #ToLink 
- - -
Håkon Wium Lie was working at CERN at the same time as Tim Berners‐Lee. He immediately recognised the potential of the World Wide Web and its language, HTML. He also realised that the expressive power of the language was in danger of being swamped by visual features. Lie proposed a new format to describe the presentation of HTML documents: Cascading Style Sheets.
win explorer 3 fue el primero en darle soporte y tiene una especifacion cerrada
# Añadir
- css resset, normlizer 
-  cheatsheet user agen(etilos por defecto de los navegadores)
- los comentarios son /\*\*/
- Si te pones encima de vs ves una paleta de colores
- color rgba legacy |  rgb(n1 n2 n3 / opacidad(opcional)) moderno | trasparent palabra clave | oklch(mas moderno) && hsl |  ==Encontrar hoja de colores==
- border , se combina con tamaño, style, color(current color), 
## Fundamentos
puedes llamar a style desde donde quieras, pero mejor desde el head
## Selectores
 por etiquetas
- puedes llamar al selector como un elemento por ejemplo h1, y todos los elementos h1 cambiaran(buen ejercicio)
por clases
- en css hay que ponerle un "." del nombre de la clase
show
- revisar esto
## Fuentes
- font-family se hereda, se le pueden dar fallbacks 
## Herencia
no todo se hereda 
atributos: inheri
- - - 
todo copiado del gpt solo tomar como referencia
### Sintaxis básica
```css
selector {
    propiedad: valor;
}
```
### Especificidad y Cascada
1. Importancia (del más al menos importante):
   - `!important`
   - Estilos inline
   - ID (#)
   - Clases (.), atributos y pseudo-clases
   - Elementos y pseudo-elementos
   - Selector universal (*)
### Selectores principales
```css
/* Básicos */
* { } /* Universal */
p { } /* Elemento */
.clase { } /* Clase */
#id { } /* ID */
[type="text"] { } /* Atributo */

/* Combinadores */
div p { } /* Descendiente */
div > p { } /* Hijo directo */
div + p { } /* Hermano adyacente */
div ~ p { } /* Hermanos generales */

/* Pseudo-clases */
:hover
:focus
:first-child
:last-child
:nth-child(n)

/* Pseudo-elementos */
::before
::after
::first-letter
::selection
```
## Box Model
```css
.elemento {
    /* Content */
    width: 200px;
    height: 100px;
    
    /* Padding */
    padding: 10px; /* todos los lados */
    padding: 10px 20px; /* vertical horizontal */
    padding: 10px 20px 15px 25px; /* arriba derecha abajo izquierda */
    
    /* Border */
    border: 1px solid black;
    border-radius: 5px;
    
    /* Margin */
    margin: 10px;
    
    /* Box sizing */
    box-sizing: border-box; /* incluye padding y border en width/height */
}
```
## Layout
En su originen eran elementos tablas en el libro de David Siegel’s Creating Killer Websites  
### Display
```css
.elemento {
    display: block; /* elemento de bloque */
    display: inline; /* elemento en línea */
    display: inline-block; /* híbrido */
    display: none; /* oculta el elemento */
}
```
### Position
```css
.elemento {
    position: static; /* default */
    position: relative; /* relativo a su posición normal */
    position: absolute; /* relativo al ancestro posicionado más cercano */
    position: fixed; /* relativo al viewport */
    position: sticky; /* híbrido entre relative y fixed */
    
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 1;
}
```
## Flexbox
```css
.contenedor {
    display: flex;
    flex-direction: row | column;
    justify-content: flex-start | center | flex-end | space-between | space-around;
    align-items: stretch | flex-start | center | flex-end;
    gap: 10px;
}

.item {
    flex: 1; /* grow | shrink | basis */
    order: 1;
    align-self: center;
}
```
## Grid
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

.item {
    grid-column: 1 / 3;
    grid-row: 1 / 2;
    grid-area: header;
}
```
## Tipografía
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
## Colores y Fondos
```css
.elemento {
    /* Colores */
    color: #ff0000;
    color: rgb(255, 0, 0);
    color: rgba(255, 0, 0, 0.5);
    color: hsl(0, 100%, 50%);
    
    /* Fondos */
    background-color: #fff;
    background-image: url('imagen.jpg');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    
    /* Gradientes */
    background: linear-gradient(to right, #fff, #000);
    background: radial-gradient(circle, #fff, #000);
}
```
## Transformaciones y Transiciones
```css
.elemento {
    /* Transformaciones */
    transform: translate(50px, 100px);
    transform: rotate(45deg);
    transform: scale(1.5);
    
    /* Transiciones */
    transition: all 0.3s ease;
    transition: background-color 0.3s ease-in-out;
}

/* Animaciones */
@keyframes slide {
    from { transform: translateX(0); }
    to { transform: translateX(100px); }
}

.elemento {
    animation: slide 2s infinite;
}
```
## Debug
```css
/* Outline para debug */
* {
    outline: 1px solid red !important;
}
```
- - - 
## ***Sources:***
- [Biblioteca y Tutorial](https://manz.dev/)
-  [Standard Dessarrollo Web](https://developer.mozilla.org/en-US/)
- [Estilos en tiempo real](https://codi.link/%7C%7C)
Catalogos:
- [Catalogo y Apuntes CSS](https://htmlcheatsheet.com/css/)
- [Catalogo de Fuentes CSS](https://kagi.com/search?q=fonts.googlefont)
- [Catalogo de Diseños CSS](https://csszengarden.com/pages/alldesigns/)