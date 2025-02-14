 
EJERCICIOS PROGRAMACION WEB BASICA

 Ejercicio 1: Creación de una página simple con fuentes y colores

 Enunciado:
Crea una página web sencilla con los siguientes elementos:
1. Un título principal (h1) con el texto "Bienvenidos a mi página".
2. Un subtítulo (h2) con el texto "Este es mi primer ejercicio".
3. Un párrafo que contenga una breve descripción de ti mismo.
4. Aplica una fuente personalizada desde Google Fonts a todo el texto.
5. El color de fondo debe ser un tono suave de azul, y el texto debe ser de color oscuro (como un gris oscuro).
6. Asegúrate de que el contenido esté centrado en la página tanto vertical como horizontalmente.
 
 Requisitos:
- Utiliza Google Fonts para agregar una fuente.
- Usa Flexbox para centrar el contenido.
 
 Ejercicio 2: Estilo de una tarjeta de presentación
 Enunciado:
Crea una tarjeta de presentación con las siguientes características:
1. La tarjeta debe tener un borde redondeado y un sombreado debil.
2. Dentro de la tarjeta, incluye los siguientes elementos:
   - Un nombre con una etiqueta `<h1>`.
   - Una descripción corta en un párrafo.
   - Un botón que diga "Contactar".
3. La tarjeta debe estar centrada en la página utilizando Flexbox.
4. Aplica colores de fondo para los elementos: 
   - El fondo de la tarjeta debe ser blanco.
   - El texto debe ser oscuro.
   - El botón debe tener un color de fondo contrastante con texto blanco.
 Requisitos:
- Usa Flexbox para centrar la tarjeta.
- El botón debe cambiar de color al pasar el ratón sobre él (hover).
 
 Ejercicio 3: Navegación simple con enlace a la tarjeta de contacto
 
 Enunciado:
Crea una barra de navegación simple con enlaces a diferentes secciones de la página:
1. Crea una estructura de navegación horizontal con 3 enlaces:
   - **Inicio**
   - **Acerca de**
   - **Contacto** (Este enlace llevará a una tarjeta de presentación en la misma página).
2. Cada enlace debe ser un `<a>` dentro de un `<nav>`, y debe estar estilizado con colores.
3. Cuando se pase el ratón sobre un enlace, debe cambiar el color de fondo.
4. Utiliza Flexbox para alinear los enlaces de manera horizontal y centrarlos en la parte superior de la página.
5. Al hacer clic en el enlace "Contacto", debe llevar al usuario directamente a una sección de la página donde se encuentre la tarjeta de presentación (puedes usar el atributo `id` para lograrlo).
 Requisitos:
- Usa Flexbox para organizar los enlaces.
- Aplica un color de fondo al pasar el ratón (hover) y cambia el color del texto.
- Asegúrate de que al hacer clic en "Contacto", el usuario sea redirigido hacia la tarjeta de presentación dentro de la misma página.
 
 Ejercicio 4: Layout de 3 columnas con Flexbox
 Enunciado:
Crea un layout de 3 columnas que contenga las siguientes secciones:
1. Una barra lateral izquierda con un ancho fijo, que contenga una lista de enlaces.
2. Un contenido principal en el centro con un texto que describa algo interesante.
3. Una barra lateral derecha con enlaces de redes sociales.
4. Asegúrate de que el layout se vea bien en dispositivos de diferentes tamaños (responsivo).
5. Aplica Flexbox para organizar las columnas y asegurarte de que se adapten bien.
 Requisitos:
- Utiliza Flexbox para crear el layout de 3 columnas.
- Las barras laterales deben tener un ancho fijo, y el contenido principal debe ocupar el espacio restante.
- Asegúrate de que el diseño sea responsive (ajustable a pantallas pequeñas).
 
 Ejercicio 5: Incrustar un video de YouTube
 Enunciado:
Crea una sección en tu página donde se incruste un video oficial de Angular. Debes hacer lo siguiente:

1. Encuentra el video oficial de Angular en YouTube. Puedes buscar uno de su canal oficial, como el siguiente: [Angular Official Channel](https://www.youtube.com/c/Angular).
2. Incrusta el video en tu página utilizando el código `<iframe>` proporcionado por YouTube. Asegúrate de que el video se ajuste correctamente al tamaño de la pantalla.
3. Dale un estilo adecuado al video para que se vea bien dentro de un contenedor. Asegúrate de que tenga un ancho máximo de 100% y un alto proporcional para que se ajuste en cualquier tamaño de pantalla.
4. Añade un título (h3) que diga "Aprende Angular" encima del video.
 Requisitos:
- Usa el código de incrustación de YouTube (`<iframe>`).
- Asegúrate de que el video sea responsivo y se ajuste bien al tamaño de la pantalla.
- Aplica un estilo básico para que el video esté bien centrado y no se desborde del contenedor.
 
 Ejercicio 6: Layout de múltiples pantallas con 3 paneles de video

 Enunciado:
Crea un layout de 3 paneles en disposición vertical (|) para mostrar videos en cada panel. Cada panel debe contener un video diferente. Los pasos son los siguientes:

1. Crea un contenedor principal que tenga tres paneles, uno al lado del otro.
2. Cada panel debe contener un video de YouTube incrustado. Puedes utilizar los mismos videos o diferentes para cada uno.
3. Usa Flexbox para asegurarte de que los tres paneles se distribuyan de manera proporcional en la pantalla.
4. Los videos deben ocupar todo el espacio dentro de cada panel, pero sin desbordarse.
5. Asegúrate de que el layout sea responsivo, de manera que en pantallas más pequeñas los paneles se apilen verticalmente en lugar de estar en una sola fila.
6. Añade un título general que diga "Paneles de Video" encima del layout.

 Requisitos:
- Usa Flexbox para crear un layout con 3 paneles.
- Los videos deben ser responsivos y ajustarse al tamaño de su contenedor.
- El layout debe adaptarse a diferentes tamaños de pantalla (pantallas pequeñas deben apilar los paneles).
- Utiliza el código de incrustación de YouTube (`<iframe>`) para insertar los videos.


SOLUCIONES:

 Ejercicio 1: Creación de una página simple con fuentes y colores

 Solución:
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mi Página</title>
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Roboto', sans-serif;
      background-color: b3cde0;
      color: 333;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    h1 {
      text-align: center;
    }
    h2 {
      text-align: center;
    }
  </style>
</head>
<body>
  <div>
    <h1>Bienvenidos a mi página</h1>
    <h2>Este es mi primer ejercicio</h2>
    <p>Hola, soy un estudiante aprendiendo HTML y CSS. Este es mi primer ejercicio en la materia.</p>
  </div>
</body>
</html>
```

 Ejercicio 2: Estilo de una tarjeta de presentación

 Solución:
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tarjeta de Presentación</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: f4f4f4;
      margin: 0;
    }
    .card {
      width: 300px;
      padding: 20px;
      background-color: white;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      text-align: center;
    }
    h1 {
      font-size: 24px;
      margin-bottom: 10px;
    }
    p {
      font-size: 16px;
      margin-bottom: 20px;
    }
    button {
      padding: 10px 20px;
      background-color: 4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: 45a049;
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Juan Pérez</h1>
    <p>Desarrollador web y apasionado por la tecnología.</p>
    <button>Contactar</button>
  </div>
</body>
</html>
```

 Ejercicio 3: Navegación simple con enlace a la tarjeta de contacto

 Solución:
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Navegación Simple</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
    }
    nav {
      display: flex;
      justify-content: center;
      background-color: 333;
    }
    nav a {
      color: white;
      padding: 14px 20px;
      text-decoration: none;
    }
    nav a:hover {
      background-color: ddd;
      color: black;
    }
    .section {
      padding: 50px;
      text-align: center;
    }
  </style>
</head>
<body>
  <nav>
    <a href="inicio">Inicio</a>
    <a href="acerca-de">Acerca de</a>
    <a href="contacto">Contacto</a>
  </nav>
  
  <div id="inicio" class="section">
    <h2>Bienvenido a mi sitio web</h2>
  </div>
  
  <div id="acerca-de" class="section">
    <h2>Sobre mí</h2>
    <p>Soy un desarrollador web en constante aprendizaje.</p>
  </div>
  
  <div id="contacto" class="section">
    <h2>Tarjeta de Contacto</h2>
    <div class="card">
      <h1>Juan Pérez</h1>
      <p>Desarrollador web y apasionado por la tecnología.</p>
      <button>Contactar</button>
    </div>
  </div>
</body>
</html>
```

 Ejercicio 4: Layout de 3 columnas con Flexbox

 Solución:
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Layout de 3 Columnas</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      height: 100vh;
    }
    .container {
      display: flex;
      flex: 1;
    }
    .sidebar {
      width: 200px;
      background-color: f4f4f4;
      padding: 20px;
    }
    .main {
      flex: 1;
      padding: 20px;
      background-color: fff;
    }
    .right-sidebar {
      width: 200px;
      background-color: f4f4f4;
      padding: 20px;
    }
    @media (max-width: 768px) {
      .container {
        flex-direction: column;
      }
      .sidebar, .right-sidebar {
        width: 100%;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="sidebar">
      <h3>Menú</h3>
      <ul>
        <li><a href="">Inicio</a></li>
        <li><a href="">Acerca de</a></li>
        <li><a href="">Servicios</a></li>
      </ul>
    </div>
    <div class="main">
      <h1>Contenido Principal</h1>
      <p>Esta es la sección principal del sitio web.</p>
    </div>
    <div class="right-sidebar">
      <h3>Redes Sociales</h3>
      <ul>
        <li><a href="">Facebook</a></li>
        <li><a href="">Twitter</a></li>
        <li><a href="">Instagram</a></li>
      </ul>
    </div>
  </div>
</body>
</html>
```

 Ejercicio 5: Incrustar un video de YouTube

 Solución:
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Aprende Angular</title>
  <style>
    iframe {
      width: 100%;
      height: 315px;
      max-width: 800px;
      margin: 0 auto;
      display: block;
    }
    h3 {
      text-align: center;
    }
  </style>
</head>
<body>
  <h3>Aprende Angular</h3>
  <iframe src="https://www.youtube.com/embed/7lP4JWbo6uM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</body>
</html>
```
 
 Ejercicio 6: Layout de múltiples pantallas con 3 paneles de video

 Solución:
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Paneles de Video</title>
  <style>
    .container {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
    }
    .panel {
      flex: 1;
      padding: 10px;
      box-sizing: border-box;
    }
    iframe {
      width: 100%;
      height: 100%;
    }
    h3 {
      text-align: center;
    }
  </style>
</head>
<body>
  <h3>Paneles de Video</h3>
  <div class="container">
    <div class="panel">
      <iframe src="https://www.youtube.com/embed/7lP4JWbo6uM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>
    <div class="panel">
      <iframe src="https://www.youtube.com/embed/7lP4JWbo6uM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>
```
