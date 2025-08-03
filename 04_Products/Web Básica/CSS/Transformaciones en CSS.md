**MetaTags:** #_Todo
**Tags:** #CSS #ToLink 
- - -
Las **transformaciones** en CSS permiten modificar la apariencia de los elementos, alterando su posición, tamaño, rotación e inclinación.

## Propiedades principales

- **`translate(x, y)`** → Mueve el elemento en los ejes X e Y.
- **`rotate(θdeg)`** → Rota el elemento en sentido horario.
- **`scale(x, y)`** → Escala el tamaño del elemento.
- **`skew(xθ, yθ)`** → Inclina el elemento.
- **`matrix(a, b, c, d, e, f)`** → Aplica múltiples transformaciones en una sola función.

## Ejemplo
```css
.caja {
    transform: rotate(15deg) scale(1.2);
}
```
**Consejo**: Usa `will-change` en elementos animados para optimizar el rendimiento.
```css
.elemento {
    will-change: transform;
}
```
- - - 
## ***Sources:***