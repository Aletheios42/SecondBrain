**Tags:** #_Todo
#HTML #DesarrolloWeb  #ToLink 
- - -
Prerrequisitos:
- Editor de código (copilot opcional)
- navegador google-chrome
- live previews / live server
##  Introducción a HTML5
HTML es el lenguaje de marcado estándar web desde 1993
Fue inventado por Tim Berners‐Lee junto con http (protocolo de transferencia de hipertexto) en el cern.

✅ Se encaga de describir el contenido
❌ No se encarga del estilo, pues lo hace [[Curso CSS - Indice|CSS]]
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
- Cuando un navegador encuentra `<!DOCTYPE html>` al inicio de un documento HTML, lo representa en **modo estándar**.  
  Si no se usa un `DOCTYPE`, el navegador entra en **modo quirks**, lo que puede provocar que ciertos contenidos no se muestren correctamente.
- El punto de entrada se suele llamar `index.html` porque el navegador lo busca por defecto.
- Comentarios `<!-- ... -->`
- Ya no se puede escribir XML en HTML5.
##  Elementos en HTML
Hay 121 elementos en HTML5 y los principales son:
### **Listado de elementos HTML**
#### **Elementos del `body`**
##### **Elementos semánticos**
La semántica en HTML5 significa utilizar etiquetas que describen su propósito en lugar de depender solo de `<div>` y `<span>`.  
Esto ayuda a la accesibilidad, SEO y mantenimiento del código.
```html
<header>Cabecera del sitio</header>
<nav>Menú de navegación</nav>
<main>Contenido principal</main>
<aside>Información relacionada</aside>
<article>Artículo independiente </article>
<footer>Pie de página</footer>
```
##### **Elementos de agrupación**
- `<div>`: Elemento contenedor genérico.
- `<span>`: Texto en línea sin estilo predeterminado.
##### **Elementos de contenido**
- `<h1>` - `<h6>`: Encabezados de diferentes niveles.
- `<p>`: Párrafo de texto.
- `<a>`: Enlace a otra página o recurso.
  - Se puede usar `rel="noreferrer"` para no enviar datos a la página destino. 
  - Se puede usar `href="mailto:correo@ejemplo.com"` o `href="tel:+123456789"` para correos y teléfonos. 
  - Se puede usar `download` para permitir descargas directas. 
- `<ul>`, `<ol>`, `<li>`: Listas desordenadas, ordenadas y elementos de lista.
  - Se puede cambiar el estilo de los números y guiones con `type`.
- `<table>`, `<tr>`, `<td>`: Tablas y celdas.
- `<form>`: Formularios de entrada de datos.
	  - `<fieldset>`, `<legend>`, `<label>`, `<input>`, `<textarea>`, `<button>`.
	  - `<input>` admite muchos tipos (`email`, `password`, `number`, etc.). 
	  - Se debe usar `required` en campos obligatorios. 
	  - Se puede usar `<datalist>` para sugerencias de entrada. 
- Diferencia entre `<button type="submit">` y `<input type="submit">`. 
- `<img>`: Inserta imágenes. No necesita cierre.
  - Atributos: `src`, `alt`, `title`, `loading="lazy"`.
- `<video>`: Reproduce videos.
  - Atributos: `autoplay`, `controls`, `muted`. 
- `<iframe>`: Inserta otras páginas web.
  - Se pueden bloquear integraciones con metadatos en `header`. 
  - Se usa `allow` para permisos y `allowfullscreen` para pantalla completa. 
- `<canvas>`: Lienzo para gráficos dinámicos. 
- `<dialog>`: Ventana de diálogo modal (`open`). 
- `<script>`: Código JavaScript.
  - Cuidado con `window` y colisiones de `id`. 
  - Permite eventos como `showModal()`. 
### Listado de atributos comunes
- `id`: Identificador único del elemento.
	- cada id se añade al objeto window(no es optimo ponerle id a todo)
- `class`: Clase para aplicar estilos CSS.
- `style`: Estilos en línea.
- `name`: Nombre del elemento (usado en formularios).
- `src`: Fuente de un recurso (imágenes, videos, etc.).
- `alt`: Texto alternativo en imágenes.
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
- `download` en un enlace (\<a>) permite descargar un recurso disponible directamente de tu servidor. 
#### **Elementos del head**
Los siguientes elementos son esenciales para optimizar el SEO, mejorar la compatibilidad entre dispositivos, y facilitar la compartición en redes sociales. Una implementación adecuada de estas etiquetas mejora la visibilidad del sitio en motores de búsqueda y la experiencia de usuario.
- head se puede poner varias veces
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

<!-- Etiqueta canonical: Indica la URL preferida para evitar contenido duplicado en los motores de búsqueda -->
<link rel="canonical" href="https://www.ejemplo.com/pagina-principal">

<!-- Prevención de detección de número de teléfono en iOS -->
<meta name="format-detection" content="telephone=no">

<!-- para adptar el color del banner del navegador -->
<meta name=theme-color content='#09f" 

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

<!-- RSS Feed -->
<link rel="alternate" type="application/rss+xml" title="RSS" href="/feed.xml">

<!-- Evitar envío de datos de referencia al enlazar a otras páginas -->
<link rel="noreferrer" href="https://www.ejemplo.com">

```
- -  - 
## ***Sources:***
- [Cheatsheet de HTML](https://htmlcheatsheet.com/html/)
- [Curso de midudev de HTML](https://www.youtube.com/watch?v=3nYLTiY5skU)
- [Libro sobre Programación de Web Básica](https://resilientwebdesign.com/)
-  [Standard Dessarrollo Web](https://developer.mozilla.org/en-US/)
- [Para ver previews](https://www.opengraph.xyz/)
- [Editor en linea - Catalogo de Componentes y Red social de Front](https://codepen.io/)