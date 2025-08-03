**Tags:** #_Todo
**MetaTags:** #CSS #ToLink
- - -
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
- - - 
## ***Sources:***