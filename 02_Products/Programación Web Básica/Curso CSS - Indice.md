**Tags:** #_Todo
#CSS #DesarrolloWeb #ToLink 
- - -
Håkon Wium Lie, trabajando en el CERN junto a Tim Berners-Lee, vio el potencial de la Web y HTML, pero advirtió que su diseño podía verse afectado por el desorden visual. Para solucionarlo, propuso las Hojas de Estilo en Cascada (CSS), un sistema para separar la estructura del contenido de su presentación.  

Internet Explorer 3 fue el primer navegador en implementarlo, aunque con una especificación cerrada.
# Añadir
- css resset, normlizer 
-  cheatsheet user agen(etilos por defecto de los navegadores)
- los comentarios son /\*\*/
- Si te pones encima de vs ves una paleta de colores
- color rgba legacy |  rgb(n1 n2 n3 / opacidad(opcional)) moderno | trasparent palabra clave | oklch(mas moderno) && hsl |  ==Encontrar hoja de colores==
- border , se combina con tamaño, style, color(current color), 
- puedes llamar a style desde donde quieras, pero mejor desde el head
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
## [[Flexbox CSS]]
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
## [[Box Model CSS]]

## Layout
En su originen eran elementos tablas en el libro de David Siegel’s Creating Killer Websites  
- ### [[Display CSS]]
- ### [[Position]]

## [[Flexbox CSS]]
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
## [[Tipografía CSS]]
## [[Colores y Fondos CSS]]
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