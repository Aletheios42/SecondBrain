**Tags:** #_Todo
#ToTag #ToLink 
- - -
 ==MIrar ejercicios en github== [Ejercicios](https://github.com/SuperSimpleDev/html-css-course/tree/main/1-exercise-solutions)
prerequisitos
- live-server
# HTML
## Conceptos Básicos
### Hypertext Markup Language
- Los archivos `.html` pueden ser renderizados por un navegador
- El proceso de renderizado sigue un flujo **top-bottom**
- Fases del renderizado:
  1. Parsing del HTML
  2. Construcción del DOM
  3. Procesamiento del CSS
  4. Construcción del Render Tree
  5. Layout y Paint
### Estructura Básica
```html
<!DOCTYPE html>
<html lang="es">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Título de la página</title>
    </head>
    <body>
        Contenido de la página
    </body>
</html>
```

### Explicación de Elementos Base
1. **`<!DOCTYPE html>`**:
   - Indica que el documento es HTML5.
   - Es obligatorio y debe ser la primera línea.
2. **`<html>`**:
   - Es el contenedor raíz del documento.
   - El atributo `lang` define el idioma del contenido (ej: `lang="es"` para español).
3. **`<head>`**:
   - Contiene metadatos, como el título, enlaces a CSS, scripts, etc.
   - No es visible en la página.
4. **`<body>`**:
   - Contiene el contenido visible de la página.
### DOM (Document Object Model)
- Representación en árbol del documento HTML
- Cada elemento es un nodo en el árbol
- Permite:
  - Manipulación dinámica
  - Acceso programático
  - Modificación de contenido
  - Gestión de eventos
- Interfaz principal entre JavaScript y HTML
## Elementos HTML Básicos
[Hoja de apuntes HTML](https://htmlcheatsheet.com/html/)
[[Curso de HTML - LABS - Mi primera Web estatica]]
### Atributos
- Son modificadores de elementos
- Formato nombre-valor
- Ejemplos comunes:
  ```html
  href="https://youtube.com"
  target="_blank"  <!-- abre links en nuevas tabs -->
  class="nombre-clase"
  id="identificador-unico"
  ```
### Void Elements
- No requieren tag de cierre
  ```html
  <img src="imagen.jpg">
  <br>
  <hr>
  <input type="text">
  ```
### Atributos booleanos
atributo, sin necesidad de un valor.
``` htmlº
<input type="checkbox" checked>
<button disabled>Botón deshabilitado</button>
```
Lista de atributos booleanos comunes:

- checked (para inputs tipo checkbox o radio)
- disabled (para inputs y botones)
- readonly (para inputs de texto)
- required (para formularios)
- autofocus (para enfocar automáticamente un input al cargar la página)
- hidden (para ocultar un elemento sin eliminarlo del DOM)
- multiple (para seleccionar múltiples opciones en \<select>)
- selected (para preseleccionar una opción en \<option>)
- controls (para mostrar controles en \<video> y \<audio>)
- loop (para repetir automáticamente videos y audios)
## Elementos en Bloque vs. Elementos en Línea
### Elementos en Bloque
- Ocupan todo el ancho disponible.
- Comienzan en una nueva línea.
  ```html
  <div>, <p>, <h1>-<h6>, <ul>, <ol>, <li>, <table>, <form>, <header>, <section>, <article>
  ```
  ```html
  <div>Este es un bloque</div>
  <p>Este es un párrafo.</p>
  ```
### Elementos en Línea
- Ocupan solo el espacio necesario.
- No comienzan en una nueva línea.
  ```html
  <span>, <a>, <strong>, <em>, <img>, <button>, <input>, <label>
  ```
  ```html
  <span>Este es un elemento en línea.</span>
  <a href="#">Enlace</a>
  ```
### Diferencias Clave
- **Bloque**: Pueden contener otros elementos en bloque y en línea.
- **Línea**: Solo pueden contener otros elementos en línea.
## Divs y Spans
### `<div>`
- Es un contenedor genérico en **bloque**.
- No tiene significado semántico.
- Se usa para agrupar elementos y aplicar estilos.
  ```html
  <div class="contenedor">
      <p>Párrafo dentro de un div.</p>
  </div>
  ```
### `<span>`
- Es un contenedor genérico en **línea**.
- No tiene significado semántico.
- Se usa para aplicar estilos a partes de texto.
  ```html
  <p>Este es un <span style="color: red;">texto en rojo</span>.</p>
  ```
## Elementos
### Botones
```html
<button>Hello</button>
<button type="submit">Enviar</button>
<button disabled>Deshabilitado</button>
```
### Párrafos
```html
<p>Hello</p>
<h1>Encabezado 1</h1>
<h2>Encabezado 2</h2>
```
### Anchors (Enlaces)
```html
<a href="https://youtube.com">Link To YouTube</a>
<a href="mailto:email@example.com">Enviar email</a>
<a href="tel:+123456789">Llamar</a>
```
## Elementos Multimedia

```html
<picture>
    <source media="(min-width: 800px)" srcset="large.jpg">
    <source media="(min-width: 400px)" srcset="medium.jpg">
    <img src="small.jpg" alt="Imagen responsive" loading="lazy">
</picture>

<video controls preload="metadata">
    <source src="video.mp4" type="video/mp4">
    <track kind="subtitles" src="subtitles.vtt" srclang="es">
</video>
```

## Elementos HTML Avanzados
### Elementos Semánticos
```html
<header>Encabezado del sitio</header>
<nav>
    <ul>
        <li><a href="#home">Inicio</a></li>
        <li><a href="#about">Sobre nosotros</a></li>
    </ul>
Ejemplo:
</nav>
<main>
    <article>
        <section>Sección del artículo</section>
    </article>
    <aside>Contenido relacionado</aside>
</main>
<footer>Pie de página</footer>
```
### Formularios Avanzados
``` html
<form action="/submit" method="POST" enctype="multipart/form-data">
    <fieldset>
        <legend>Información Personal</legend>
        <input type="email" 
               pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}$" 
               required>
        <input type="tel" pattern="[0-9]{9}">
        <input type="date" min="2020-01-01" max="2025-12-31">
        <input type="color">
        <input type="range" min="0" max="100" step="10">
        <input type="file" accept=".jpg,.png" multiple>
        <datalist id="opciones">
            <option value="Opción 1">
            <option value="Opción 2">
        </datalist>
    </fieldset>
</form>
```
### Elementos Multimedia
```html
<picture>
    <source media="(min-width: 800px)" srcset="large.jpg">
    <source media="(min-width: 400px)" srcset="medium.jpg">
    <img src="small.jpg" alt="Imagen responsive" loading="lazy">
</picture>

<video controls preload="metadata">
    <source src="video.mp4" type="video/mp4">
    <track kind="subtitles" src="subtitles.vtt" srclang="es">
</video>

<canvas id="myCanvas" width="200" height="100"></canvas>

<svg viewBox="0 0 100 100">
    <circle cx="50" cy="50" r="40" stroke="black" fill="red"/>
</svg>
```
### Tablas Avanzadas
```html
<table>
    <caption>Título de la tabla</caption>
    <colgroup>
        <col span="2" style="background-color: yellow">
        <col style="background-color: red">
    </colgroup>
    <thead>
        <tr>
            <th scope="col">Encabezado 1</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td colspan="2">Celda combinada</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>Pie de tabla</td>
        </tr>
    </tfoot>
</table>
```
### Elementos Interactivos Adicionales
```html
<details>
    <summary>Título expandible</summary>
    Contenido oculto por defecto
</details>

<dialog>
    Modal nativo HTML
</dialog>

<progress value="70" max="100">70%</progress>

<meter value="0.6">60%</meter>
```

- - - 
## ***Sources:***
- [Catalogo de fuentes](https://kagi.com/search?q=fonts.googlefont)
- [cheetsheet de CSS](https://htmlcheatsheet.com/css/)


## Elementos Semánticos
### `<header>`
- Encabezado de la página o sección.
  ```html
  <header>
      <h1>Mi Sitio Web</h1>
      <nav>
          <a href="#inicio">Inicio</a>
          <a href="#acerca">Acerca de</a>
      </nav>
  </header>
  ```
### `<nav>`
- Menú de navegación.
  ```html
  <nav>
      <ul>
          <li><a href="#inicio">Inicio</a></li>
          <li><a href="#acerca">Acerca de</a></li>
      </ul>
  </nav>
  ```
### `<main>`
- Contenido principal de la página.
  ```html
  <main>
      <article>
          <h2>Artículo Principal</h2>
          <p>Contenido del artículo...</p>
      </article>
  </main>
  ```
### `<footer>`
- Pie de página.
  ```html
  <footer>
      <p>Derechos reservados &copy; 2023</p>
  </footer>
  ```
## Formularios Avanzados
### Campos de Entrada
```html
<form action="/submit" method="POST">
    <label for="nombre">Nombre:</label>
    <input type="text" id="nombre" name="nombre" required>
    <button type="submit">Enviar</button>
</form>
```
### Validación
```html
<input type="email" pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}$" required>
```
## Tablas
### Estructura Básica
```html
<table>
    <thead>
        <tr>
            <th>Nombre</th>
            <th>Edad</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Juan</td>
            <td>25</td>
        </tr>
    </tbody>
</table>
```
## Elementos Interactivos
### `<details>` y `<summary>`
```html
<details>
    <summary>Más información</summary>
    <p>Contenido oculto por defecto.</p>
</details>
```
### `<dialog>`
```html
<dialog open>
    <p>Este es un modal nativo.</p>
</dialog>
```










# CSS
==¿Qué es?==
[Hoja de apuntes css](https://htmlcheatsheet.com/css/)
-  Como targetear diferentes elementos
- Prioridades de los estilos (selectores mas especificos tienen mas prioridad)
## Propiedades basicas
Hacer ejercicios replicando botones, [Seccion 2 HTML & CSS Full Course - Beginner to Pro](https://www.youtube.com/watch?v=G3e-cpL7ofc)

``` css
<style>
button {
CSS property: Css value;
background-color:
color:
border: 
height: 
border-radius:
cursor: 
}
<\style>
```
 - pixels como unidad de medida
 - colores (R, G, B)
 - atributo class en HTML para seleccionar a que elemaentos aplicarr los estilos CCS
 -  una propiedad puede afectar a mas de un elemento. en el css pones comas

## CSS Box Model
times es la fuente por defecto pero se puden importar
- height/width (es fija y puede hacer que el texto no quepa en el boton) si no pones ninguno se adapta al tamaño del texto por defecto
- padding
- border
- margain
## propiedades de texto
[Para mirar ejemplos de fuentes](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)
- font family, size, weight
- Text alling
- strong, u, 
- span

## CSS Display
blocks elementes
inline blokc elementes
inline element
## Hover Shadow Trasition
- opacitty 
transition: propiedad 0.15s
box-shadow pxl, pxl, pxl, rgba()
## Images
- si cambisa el ancho se rescala la imagen
- src = ""
- object-fit:
- object-position:
## Input
- cajas de texto
## Div
es un elemento de blocque por defecto
## Nested layout
- google drawing para pintarte  los rectangulos esta muy bien

- - - 
## Añadir conceptios
- DOM
- identacion: normalmente 2 tabs en los elemontos
- consola del navegador inspeccionar elementos  estilos y cajas
- HTML entities
