**Tags:** #_Todo
**MetaTags:** #CSS  #ToLink
- - -
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
- - - 
## ***Sources:***