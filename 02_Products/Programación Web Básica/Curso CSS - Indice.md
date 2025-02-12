**Tags:** #_Todo
#CSS #DesarrolloWeb #ToLink 
- - -
# CSS Fundamentals

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

## Estructura

### [[Selectores principales CSS]]
### [[Unidades de Medida CSS]]
### [[Box Model CSS]]
### [[Flexbox CSS]]

## Layout
Originalmente, los diseños web se basaban en tablas (según David Siegel’s "Creating Killer Websites").
- ### [[Display CSS]]
- ### [[Position CSS]]
- ### [[Grid CSS]]

## Tipografía
- **Fallbacks**: Se pueden definir fuentes alternativas por si la principal no está disponible.
### [[Tipografía CSS]]

## Colores y Fondos
- Definir colores y fondos con nombres, hexadecimales, RGB, etc.
### [[Colores y Fondos CSS]]

## [[Transformaciones y Transiciones CSS]]
## [[Debug CSS]]

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
- [Biblioteca y Tutorial](https://manz.dev/)
-  [Standard Dessarrollo Web](https://developer.mozilla.org/en-US/)
- [Estilos en tiempo real](https://codi.link/%7C%7C)
Catalogos:
- [Catalogo y Apuntes CSS](https://htmlcheatsheet.com/css/)
- [Catalogo de Fuentes CSS](https://kagi.com/search?q=fonts.googlefont)
- [Catalogo de Diseños CSS](https://csszengarden.com/pages/alldesigns/)