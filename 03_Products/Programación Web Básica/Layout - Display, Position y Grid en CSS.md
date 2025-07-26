**Tags:** #_Todo
**MetaTags:** #CSS #ToLink
- - -
### **Display**
Controla cómo los elementos se comportan en la maquetación:

- `block` → Ocupa todo el ancho disponible, genera un salto de línea (`div`, `p`).
- `inline` → Ocupa solo el ancho de su contenido, sin salto de línea (`span`, `a`).
- `inline-block` → Similar a `inline`, pero permite definir `width` y `height`.
- `flex` → Distribuye los elementos de forma flexible dentro de un contenedor.
- `grid` → Crea un sistema de cuadrícula bidimensional.
- `none` → Oculta el elemento.

```css
.contenedor {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```
### **Position**
Controla la ubicación de los elementos en la página.

- `static` → Posición por defecto, sigue el flujo normal.
- `relative` → Se mueve con respecto a su posición original.
- `absolute` → Se posiciona con respecto a su ancestro con `position: relative`.
- `fixed` → Se mantiene fijo en la ventana del navegador.
- `sticky` → Se comporta como `relative` hasta que se desplaza un umbral, luego se fija.

```css
.caja {
    position: absolute;
    top: 50px;
    left: 100px;
}
```
### **Grid**
Sistema bidimensional basado en filas y columnas.
```css
.contenedor {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: auto;
    gap: 10px;
}
```

Cada celda dentro del `grid` se puede posicionar de manera específica:
```css
.item {
    grid-column: 1 / 3;
    grid-row: 2 / 4;
}
```
- - - 
## ***Sources:***