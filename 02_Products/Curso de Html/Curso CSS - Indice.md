**Tags:** #_Todo
#ToTag #ToLink 
- - -
## 1. Fundamentos
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
## 2. Box Model
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
## 3. Layout
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
## 4. Flexbox
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
## 5. Grid
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
## 6. Tipografía
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
## 7. Colores y Fondos
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
## 8. Transformaciones y Transiciones
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
## 9.Debug
```css
/* Outline para debug */
* {
    outline: 1px solid red !important;
}
```
- - - 
## ***Sources:***
- [Catalogo de fuentes](https://kagi.com/search?q=fonts.googlefont)
- [cheetsheet de CSS](https://htmlcheatsheet.com/css/)
- [Hoja de apuntes css](https://htmlcheatsheet.com/css/)