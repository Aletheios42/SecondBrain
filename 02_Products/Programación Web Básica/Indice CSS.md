**Tags:** #_Todo
#CSS #DesarrolloWeb #ToLink 
- - -
## Historia
Håkon Wium Lie, trabajando en el CERN junto a Tim Berners-Lee, propuso las **Hojas de Estilo en Cascada (CSS)** para separar la estructura del contenido de su presentación, resolviendo los problemas de desorden visual en la web.  
**Internet Explorer 3** fue el primer navegador en implementarlo, aunque con una especificación cerrada.
```css
/* Sintaxis Básica */
selector {
    propiedad: valor;
}
```
## [[Selectores CSS]]
- Definen a qué elemento le aplican qué propiedad
## Especificidad y Cascada
La importancia de las reglas CSS se organiza de la siguiente manera (de mayor a menor prioridad):
- `!important`
- Estilos **inline**
- ID (`#`)
- Clases (`.`), atributos y pseudo-clases
- Elementos y pseudo-elementos
- Selector universal (`*`)
La especificidad se calcula asignando valores a cada tipo de selector y comparándolos. Se expresa en una notación A-B-C, donde:

A: Número de selectores de ID (#)
B: Número de clases (.), atributos ([attr]) y pseudo-clases (:hover)
C: Número de elementos y pseudo-elementos (h1, ::before)
**Ejemplo de especificidad:**
```css
/* Especificidad: 0-1-0 */
.mi-clase {
    color: red;
}
/* Especificidad: 1-0-0 (tiene mayor prioridad que el anterior) */
#mi-id {
    color: blue;
}
/* Especificidad: 1-0-1 (especificidad más alta) */
div#mi-id {
    color: green;
}
```
## Herencia
La **herencia** en CSS es el mecanismo por el cual ciertos estilos aplicados a un elemento padre se transmiten automáticamente a sus elementos hijos. Esto ocurre principalmente con propiedades relacionadas con el texto.
### **Restaurar valores predeterminados**
- `inherit`: Fuerza la herencia.
- `initial`: Restaura la propiedad a su valor predeterminado de CSS.
- `unset`: Si la propiedad es heredable, la hereda; si no, la restablece a `initial`.

| **Propiedades que se heredan** (Texto y presentación) | **Propiedades que NO se heredan** (Layout y diseño visual) |
| ----------------------------------------------------- | ---------------------------------------------------------- |
| `color`                                               | `margin`                                                   |
| `font-family`                                         | `padding`                                                  |
| `font-size`                                           | `border`                                                   |
| `letter-spacing`                                      | `background`                                               |
| `word-spacing`                                        | `width`, `height`                                          |
| `line-height`                                         | `display`                                                  |
| `visibility`                                          | `position`                                                 |
| `cursor`                                              |                                                            |

| **Combinador**        | **Símbolo**   | **Ejemplo** | **Descripción**                                                                 |
| --------------------- | ------------- | ----------- | ------------------------------------------------------------------------------- |
| **Descendiente**      | ` ` (espacio) | `div p`     | Selecciona todos los `<p>` dentro de `<div>`, sin importar cuán anidados estén. |
| **Hijo directo**      | `>`           | `div > p`   | Selecciona solo los `<p>` que son **hijos directos** de `<div>`.                |
| **Hermano adyacente** | `+`           | `div + p`   | Selecciona el `<p>` que está **inmediatamente después** de un `<div>`.          |
| **Hermano general**   | `~`           | `div ~ p`   | Selecciona **todos los `<p>`** que sean **hermanos** de un `<div>`.             |
### **Uso en la práctica**
```css

/* Si quieres diseñar listas con elementos directos */
ul > li {
    color: red; /* Solo afecta a los <li> que son hijos directos de <ul> */
}

/* Si quieres resaltar el primer párrafo después de un título: */
h1 + p {
    font-weight: bold; /* Solo afecta al <p> inmediatamente después del <h1> */
}
```

## **Layout: Display, Position y Grid**

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
## **Box Model CSS**
El modelo de caja en CSS define cómo se calculan las dimensiones de un elemento.
### **Estructura del Box Model**
```
+----------------------------+
|        Margin              |
|  +----------------------+  |
|  |      Border          |  |
|  |  +--------------+  |  |
|  |  |   Padding    |  |  |
|  |  | +--------+ |  |  |
|  |  | | Content | |  |  |
|  |  | +--------+ |  |  |
|  |  +--------------+  |  |
|  +----------------------+  |
+----------------------------+
```

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
## **Tipografía en CSS**
Define el aspecto del texto.

```css
.texto {
    font-family: Arial, sans-serif;
    font-size: 16px;
    font-weight: bold;
    line-height: 1.5;
    text-align: center;
    text-transform: uppercase;
}
```
### **Unidades de tamaño**
- `px` → Tamaño absoluto.
- `em` → Relativo al tamaño del elemento padre.
- `rem` → Relativo al `font-size` del `html`.
- `%` → Proporcional al contenedor.

## **[[Colores y Fondos CSS]]**
- Define el color y fondo de los elementos.

## **[[Transiciones en CSS]] y [[Transformaciones en CSS]]**
- Define animaciones y efectos.

## **Debug CSS**
Para depurar diseños, se recomienda usar `outline`:

```css
* {
    outline: 1px solid red !important;
}
```

También es útil `background-color` en layouts problemáticos.

## **Otros Conceptos y Herramientas**
- **Reset / Normalizer** → Normalizan estilos entre navegadores.
- **Paleta de Colores** → Visualización en editores como VS Code.
- **Borders** → Definidos con `tamaño`, `estilo` y `color`.

## **Buenas Prácticas**
- Mantén un código limpio y estructurado.
- Usa `rem` y `em` en vez de `px` para escalabilidad.
- Define variables CSS (`--primary-color: #3498db;`).
- Usa `flexbox` y `grid` en layouts modernos.
- Evita el uso excesivo de `!important`.
- Poner los estilos en el head

---
## ***Sources:***
- Biblioteca y Tutorial(https://manz.dev/)
-  Standard Dessarrollo Web(https://developer.mozilla.org/en-US/)
- Estilos en tiempo real(https://codi.link/%7C%7C)

Catalogos:
- Catalogo y Apuntes CSS(https://htmlcheatsheet.com/css/)
- Catalogo de Fuentes CSS(https://kagi.com/search?q=fonts.googlefont)
- Catalogo de Diseños CSS(https://csszengarden.com/pages/alldesigns/)