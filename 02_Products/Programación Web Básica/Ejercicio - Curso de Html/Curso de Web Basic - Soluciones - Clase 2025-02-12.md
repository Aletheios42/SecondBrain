
```markdown
# Soluciones de los Ejercicios

## Ejercicio 1: Creación de una página simple con fuentes y colores

### Solución:
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
      background-color: #b3cde0;
      color: #333;
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

---

## Ejercicio 2: Estilo de una tarjeta de presentación

### Solución:
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
      background-color: #f4f4f4;
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
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #45a049;
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

---

## Ejercicio 3: Navegación simple con enlace a la tarjeta de contacto

### Solución:
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
      background-color: #333;
    }
    nav a {
      color: white;
      padding: 14px 20px;
      text-decoration: none;
    }
    nav a:hover {
      background-color: #ddd;
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
    <a href="#inicio">Inicio</a>
    <a href="#acerca-de">Acerca de</a>
    <a href="#contacto">Contacto</a>
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

---

## Ejercicio 4: Layout de 3 columnas con Flexbox

### Solución:
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
      background-color: #f4f4f4;
      padding: 20px;
    }
    .main {
      flex: 1;
      padding: 20px;
      background-color: #fff;
    }
    .right-sidebar {
      width: 200px;
      background-color: #f4f4f4;
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
        <li><a href="#">Inicio</a></li>
        <li><a href="#">Acerca de</a></li>
        <li><a href="#">Servicios</a></li>
      </ul>
    </div>
    <div class="main">
      <h1>Contenido Principal</h1>
      <p>Esta es la sección principal del sitio web.</p>
    </div>
    <div class="right-sidebar">
      <h3>Redes Sociales</h3>
      <ul>
        <li><a href="#">Facebook</a></li>
        <li><a href="#">Twitter</a></li>
        <li><a href="#">Instagram</a></li>
      </ul>
    </div>
  </div>
</body>
</html>
```

---

## Ejercicio 5: Incrustar un video de YouTube

### Solución:
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

---

## Ejercicio 6: Layout de múltiples pantallas con 3 paneles de video

### Solución:
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
- - - 