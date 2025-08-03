## **EJERCICIOS HERENCIA CSS**
 **Introducción:**

Tu tarea será modificar los archivos `index.html` y `styles.css` para realizar los cambios especificados en cada ejercicio. A medida que avances, notarás cómo ciertas propiedades se heredan o se pueden restablecer usando valores como `inherit`, `initial`, `unset` o `all: unset`.

1. Abre los archivos `index.html` y `styles.css`.
2. Lee cada ejercicio y realiza los cambios en los selectores y propiedades CSS.
3. Observa cómo los cambios afectan la herencia de los estilos en la página.
4. Reflexiona sobre los efectos y responde a las preguntas de cada ejercicio.


 **Ejercicio 1: Herencia Dinámica en la Barra de Navegación**  
**Objetivo:**  
Modificar la barra de navegación para que el color de los enlaces se herede del `body`, pero que cambie dinámicamente con `:hover`.

**Pregunta:**  
¿Cómo puedes hacer que los enlaces de navegación hereden el color del `body`, pero cambien a otro color al pasar el mouse?

 **Ejercicio 2: Modificar Herencia del `button` en el `.subcontenedor`**  
**Objetivo:**  
El botón dentro del `.subcontenedor` está heredando el color de este. Evita la herencia y haz que el botón use un color independiente.

**Pregunta:**  
¿Qué propiedad puedes usar para hacer que el botón tenga su color por defecto en lugar del heredado?

 **Ejercicio 3: Variables CSS y `inherit` en Múltiples Elementos**  
**Objetivo:**  
Usar `:root` para definir una variable de color y hacer que los `<p>` dentro de `.contenedor` hereden el nuevo color global.

**Pregunta:**  
¿Cómo puedes definir un color global en `:root` y hacer que `.contenedor` y sus párrafos usen esa variable?

 **Ejercicio 4: Reset de Herencia con `unset`**  
**Objetivo:**  
Eliminar la herencia del color en el `<span>` dentro de `.articulo` y hacer que use su estilo predeterminado.

**Pregunta:**  
¿Qué propiedad CSS te permite eliminar la herencia del color en un elemento y devolverlo a su valor inicial del navegador?

 **Ejercicio 5: Evitar Herencia Global con `all: unset;`**  
**Objetivo:**  
Resetear completamente la herencia del `<p>` en el footer para que no reciba ningún estilo global.

**Pregunta:**  
¿Qué propiedad puedes usar para eliminar **todos** los estilos heredados en un solo paso?

- - - 
Aquí tienes la **plantilla HTML y CSS** para los ejercicios de herencia en CSS.  
 **index.html**
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ejercicios de Herencia en CSS</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <header>
        <h1>Ejercicios de Herencia en CSS</h1>
        <nav>
            <ul>
                <li><a href="#">Inicio</a></li>
                <li><a href="#">Sobre Nosotros</a></li>
                <li><a href="#">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section class="contenedor">
            <h2>Título de Sección</h2>
            <p class="intro">Este es un párrafo introductorio dentro de la sección.</p>

            <article class="articulo">
                <h3>Artículo Importante</h3>
                <p>Texto del artículo que hereda estilos del contenedor.</p>
                <span>Texto resaltado dentro del artículo.</span>
            </article>

            <div class="subcontenedor">
                <p>Párrafo dentro del subcontenedor.</p>
                <button>Haz clic aquí</button>
            </div>
        </section>
    </main>

    <footer>
        <p>Pie de página con información legal y enlaces.</p>
    </footer>

</body>
</html>
```
 **styles.css**
```css
/* Estilos globales */
body {
    font-family: Arial, sans-serif;
    color: black;
}

/* Barra de navegación */
nav ul {
    list-style: none;
    display: flex;
    gap: 15px;
    padding: 10px;
}

nav a {
    text-decoration: none;
    color: darkblue;
}

/* Contenedores principales */
.contenedor {
    color: blue;
    padding: 20px;
    border: 2px solid black;
}

.subcontenedor {
    color: red;
    padding: 15px;
    border: 1px dashed gray;
}

/* Botón */
button {
    background-color: gray;
    color: white;
    padding: 10px;
    border: none;
    cursor: pointer;
}
```

## **Soluciones**
 **Solución 1: Herencia Dinámica en la Barra de Navegación**  
```css
nav a {
    color: inherit;
}

nav a:hover {
    color: orange;
}
```
 **Solución 2: Modificar Herencia del `button` en el `.subcontenedor`**  
```css
.subcontenedor button {
    color: initial;
}
```
 **Solución 3: Variables CSS y `inherit` en Múltiples Elementos**  
```css
:root {
    --primary-color: purple;
}

.contenedor {
    color: var(--primary-color);
}

.contenedor p {
    color: inherit;
}
```
 **Solución 4: Reset de Herencia con `unset`**  
```css
.articulo span {
    color: unset;
}
```
 **Solución 5: Evitar Herencia Global con `all: unset;`**  
```css
footer p {
    all: unset;
}
```

