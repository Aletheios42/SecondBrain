**Tags:** #_Todo
#HTML #DesarrolloWeb  #ToLink 
- - -
==Manteniendo el contenido tengo que dividir los elementos en body y head==
==ademas en el body tengoq ue separar entre lo semantico y la agrupacion==
prerrequisitos:
- Editor de código (copilot opcional)
- navegador google-chrome
- live previews / live server
##  Introducción a HTML5
HTML es el lenguaje de marcado estándar web desde 1993
Fue inventado por Tim Berners‐Lee junto con http (protocolo de transferencia de hipertexto) en el cern
✅ Se encaga de describir el contenido
❌ No se encarga del estilo, pues lo hace CSS
❌ No se encarga de la interactividad, pues lo hace javascript

En HTML, los elementos se construyen a partir de etiquetas, atributos y contenido. Un **elemento** es la combinación de:
- **Etiqueta de apertura**
- **Contenido** (si lo tiene)
- **Etiqueta de cierre** (excepto en elementos vacíos)

| Concepto           | Descripción                                                                                |
| ------------------ | ------------------------------------------------------------------------------------------ |
| **Etiqueta (Tag)** | Marca el inicio o fin de un elemento. Se escribe entre `< >`.                              |
| **Elemento**       | Incluye la etiqueta de apertura, el contenido y la etiqueta de cierre.                     |
| **Atributo**       | Proporciona información adicional sobre un elemento. Se define en la etiqueta de apertura. |
- Cuando un navegador encuentra `<!DOCTYPE html>` al inicio de un documento HTML, lo representa en **modo estándar**. Si no se usa un `DOCTYPE`, el navegador entra en **modo quirks**, lo que puede provocar que ciertos contenidos no se muestren correctamente. 
- El punto de entrada se suele llamar index.html porque el navegador lo busca por defecto
- Comentarios <-!-- ---->
- Ya no se puede escribir XML
##  Elementos en HTML
Hay 121 elementos en HTML5 y los principales son:
### Listado de elementos HTML
- `<html>`: Contenedor raíz de una página web.
- `<head>`: Contiene metadatos como idioma y estilos.
- `<title>`: Define el título de la página (visible en la pestaña del navegador).
- `<body>`: Contiene el contenido visible de la página.
- `<div>`: Elemento contenedor genérico.
- `<span>`, `<strong>`, `<em>`: Texto en línea con diferentes estilos.
- `<h1>` - `<h6>`: Encabezados de diferentes niveles.
- `<p>`: Párrafo de texto.
- `<a>`: Enlace a otra página o recurso.
- `<img>`: Inserta imágenes. No necesita cierre.
	- Atributos: src, alt, tittle, loading lazy(no cargues cosas arriba, va a dar un parpadeo)
- `<ul>`, `<ol>`, `<li>`: Listas desordenadas, ordenadas y elementos de lista. 
- `<table>`, `<tr>`, `<td>`: Tablas y celdas. 
- `<form>`: Formularios de entrada de datos.
	- fieldset, legend, label(for o embolber input con label), placeholder
- `<input>`, `<textarea>`, `<button>`: Elementos de formulario. No necesita cierre y ay muchos tipos
Algunos de estos elemento tienen atributos propios, investigar cual con cual
##  Etiquetas en HTML
Las **etiquetas** se utilizan para marcar el inicio y el fin de un elemento. Se escriben entre `< >`. Existen dos tipos principales:
- **Etiqueta de apertura**: Indica el inicio de un elemento. Ejemplo: `<p>`.
- **Etiqueta de cierre**: Indica el final de un elemento. Ejemplo: `</p>`.
## Atributos en HTML
Los **atributos** proporcionan información adicional sobre un elemento. Siempre se colocan en la **etiqueta de apertura** y suelen tener un **nombre** y un **valor**, separados por `=`.
Ejemplo:
```html
<a href="https://www.ejemplo.com">Visita Ejemplo</a>
```
Explicación:
- `<a>`: Etiqueta de apertura.
- `href`: Atributo.
- `"https://www.ejemplo.com"`: Valor del atributo.
- "Visita Ejemplo": Contenido del elemento.
- `</a>`: Etiqueta de cierre.
### Listado de atributos comunes
- `id`: Identificador único del elemento.
	- cada id se añade al objeto window(no es optimo ponerle id a todo)
- `class`: Clase para aplicar estilos CSS.
- `style`: Estilos en línea.
- `name`: Nombre del elemento (usado en formularios).
- `src`: Fuente de un recurso (imágenes, videos, etc.).
- `alt`: Texto alternativo en imágenes.
- `href`: Enlace de anclaje en `<a>`.
- `target`: Especifica dónde abrir un enlace.
- `title`: Muestra un texto emergente al pasar el cursor.
- `checked`: Indica que un `<input>` tipo checkbox o radio está seleccionado.
- `disabled`: Deshabilita un elemento interactivo.
- `readonly`: Hace que un campo de entrada no sea editable.
- `required`: Obliga a completar un campo en formularios.
- `autofocus`: Hace que un campo reciba foco al cargar la página.
- `hidden`: Oculta un elemento sin eliminarlo del DOM. Booleano
- `multiple`: Permite seleccionar múltiples archivos en `<input type="file">`.
- `selected`: Marca una opción por defecto en `<select>`.
## SEO
Aquí tienes un conjunto de etiquetas `<meta>` y `<link>` esenciales para colocar en el `<head>` de tu documento HTML. Estas etiquetas ayudan con **SEO, redes sociales, rendimiento y compatibilidad**.
### 📌 **Meta Tags Esenciales**
```html
<!-- Configuración del conjunto de caracteres -->
<meta charset="UTF-8">

<!-- Compatibilidad con Internet Explorer -->
<meta http-equiv="X-UA-Compatible" content="IE=edge">

<!-- Adaptabilidad en dispositivos móviles -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Descripción de la página (SEO) -->
<meta name="description" content="Breve descripción de la página (máx. 160 caracteres).">

<!-- Palabras clave (no es tan relevante hoy en día, pero algunas herramientas lo usan) -->
<meta name="keywords" content="HTML, SEO, tutorial, desarrollo web">

<!-- Autor de la página -->
<meta name="author" content="Tu Nombre">

<!-- Control de indexación para motores de búsqueda -->
<meta name="robots" content="index, follow">  <!-- O "noindex, nofollow" si quieres bloquearlo -->

<!-- No se que poner revisar con chat gpt -->
<link rel="canonical" href="https://www.ejemplo.com/pagina-principal">

<!-- Prevención de detección de número de teléfono en iOS -->
<meta name="format-detection" content="telephone=no">

<!-- Configuración de idioma -->
<meta http-equiv="content-language" content="es">

```
### 📌 **Meta Tags para Redes Sociales (Open Graph & Twitter Cards)**

```html
<!-- Open Graph (Facebook, LinkedIn, WhatsApp) -->
<meta property="og:title" content="Título de la página">
<meta property="og:description" content="Descripción breve para redes sociales">
<meta property="og:image" content="https://www.ejemplo.com/imagen.jpg">
<meta property="og:url" content="https://www.ejemplo.com">
<meta property="og:type" content="website">
<meta property="og:locale" content="es_ES">

<!-- Twitter Cards -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Título de la página">
<meta name="twitter:description" content="Descripción breve para Twitter">
<meta name="twitter:image" content="https://www.ejemplo.com/imagen.jpg">
<meta name="twitter:site" content="@tuusuario">
```
### 📌 **Etiquetas `<link>` Importantes**

```html
<!-- Favicon -->
<link rel="icon" href="favicon.ico" type="image/x-icon">

<!-- Favicon para dispositivos Apple -->
<link rel="apple-touch-icon" sizes="180x180" href="apple-touch-icon.png">

<!-- Estilos CSS -->
<link rel="stylesheet" href="styles.css">

<!-- Fuente personalizada desde Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">

<!-- Preload de un recurso crítico -->
<link rel="preload" href="styles.css" as="style">

<!-- Sitemap para SEO -->
<link rel="sitemap" type="application/xml" title="Sitemap" href="/sitemap.xml">

<!-- Canonical (evita contenido duplicado) -->
<link rel="canonical" href="https://www.ejemplo.com">

<!-- RSS Feed -->
<link rel="alternate" type="application/rss+xml" title="RSS" href="/feed.xml">
```
- - - 
### AÑADIR
- en el head para indicar la codificacion  \<meta charset="uft-8">
- \<meta name=viewport content="width=device-width">
- \<meta name=robots content=index, follow"
- \<meta name=theme-color content='#09f" para adptar el color del banner del navegador
- link rel=ico type image  href.... para el favico.ico
- meta name description content="msg" (SEO) es el campo de la descripcion del navegdor, aunque a veces google no te respeta y pone la que el quiere
- open graph
- tambien hay añadir mas elementos como small, foot o aside, main
- head se puede poner varias veces
- al linkear a otras paginas rel="nonreferer" para no mandar datos a la pagina destino
- se puede usar href con mails y telefonos y whatsapp
- atributo download y wrappping con a, solo hay que decir que tienes que tener el recurso en tu server
- ol le salen numeros, ul le salen guiones, y tiene atributos para cambiar los guinos nuemros y demas 1:15 midudev html
- type, darle caña a esto y especificar email.
- required en los formularios
- datalist
- button typo summit vs input
- etiqueta video(autoplay, controles, muted)
- iframe estudiar este elemento para integrar paginas web (puedes evitar con metadatos en header que tu pagina sea incluida en otra pagina) allow para los permisos y allow fullscreen
- canvas  para dibujar
- Dialog(open)
- script. el objeto window (cuidado con hash colition con los nombres de las id)y eventos showmodal
- ==Que es la semantica==
- -  - 
## ***Sources:***
- [Cheatsheet de HTML](https://htmlcheatsheet.com/html/)
- [Curso de midudev de HTML](https://www.youtube.com/watch?v=3nYLTiY5skU)
- [Libro sobre Programación de Web Básica](https://resilientwebdesign.com/)
-  [Standard Dessarrollo Web](https://developer.mozilla.org/en-US/)
- [Para ver previews](https://www.opengraph.xyz/)