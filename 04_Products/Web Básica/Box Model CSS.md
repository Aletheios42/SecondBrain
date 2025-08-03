**MetaTags:** #_Investigar
**Tags:** #CSS #ToLink
- - -
### **Estructura del Box Model**
![[Box_Model_Diagram_CSS.jpg]]


el paddin es la distancia del borde hacia adentro
el margin es la distancia del borde hacia afuera
```css
.caja {
    width: 200px;
    height: 100px;
    padding: 10px;
    border: 2px solid black;
    margin: 20px;
}
```

### **Box Sizing**
Por defecto, `width` y `height` solo incluyen el contenido, excluyendo `padding` y `border`.  
Para simplificar los cálculos:

```css
* {
    box-sizing: border-box;
}
```


### Listado de propiedades
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
![[Box_Model_Diagram_CSS.jpg]]
- - - 
## ***Sources:***
