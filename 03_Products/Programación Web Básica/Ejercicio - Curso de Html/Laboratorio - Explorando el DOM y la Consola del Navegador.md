Este laboratorio te permitirá experimentar con el DOM, eventos y almacenamiento en el navegador sin modificar el HTML base. 
## **HTML Base**  
Antes de comenzar, asegúrate de cargar el siguiente archivo HTML en tu navegador:  

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laboratorio JavaScript</title>
    <style>
        body { font-family: Arial, sans-serif; padding: 20px; }
        .resaltado { color: red; font-weight: bold; }
    </style>
</head>
<body>

    <h1 id="titulo">Título de prueba</h1>
    <p id="parrafo">Este es un párrafo de ejemplo.</p>
    <button id="miBoton">Haz clic aquí</button>
    <button id="contadorBoton">Contar clics</button>
    <button id="resetContador">Resetear contador</button>
    <p>Contador: <span id="contador">0</span></p>

    <script>
        console.log("Abre la consola para comenzar con la exploración.");
    </script>

</body>
</html>
```

Abre la consola del navegador (`F12` o `Ctrl + Shift + I` en la mayoría de los navegadores) y prueba los siguientes experimentos.  

## **Exploración 1: ¿Qué pasa cuando cambias el contenido de un elemento?**  
Usa la consola para modificar el contenido del elemento `h1` y observa el cambio en la página.  

```js
let titulo = document.getElementById("titulo");
titulo.textContent = "Nuevo título desde la consola";
```

 **Explora más:** ¿Qué ocurre si intentas modificar un elemento que no existe?

## **Exploración 2: ¿Cómo se agregan elementos nuevos al DOM?**  
Prueba agregar un nuevo párrafo al documento y observa cómo se comporta.

```js
let nuevoParrafo = document.createElement("p");
nuevoParrafo.textContent = "Este párrafo fue agregado desde JavaScript.";
document.body.appendChild(nuevoParrafo);
```

 **Explora más:** ¿Qué sucede si agregas el mismo párrafo varias veces?

## **Exploración 3: Modificación de estilos en tiempo real**  
Cambia el color y el tamaño del texto del párrafo `#parrafo`.  

```js
let parrafo = document.getElementById("parrafo");
parrafo.style.color = "blue";
parrafo.style.fontSize = "20px";
```

**Explora más:** ¿Puedes cambiar el color de fondo del cuerpo (`document.body.style.backgroundColor = "red"`)?

## **Exploración 4: Aplicando clases CSS dinámicamente**  
Prueba agregar y quitar la clase `.resaltado` en el párrafo.

```js
let parrafo = document.getElementById("parrafo");
parrafo.classList.add("resaltado");

setTimeout(() => {
    parrafo.classList.remove("resaltado");
}, 3000);
```

**Explora más:** ¿Cómo puedes alternar esta clase cada vez que se hace clic en el párrafo?

## **Exploración 5: ¿Cómo responder a eventos del usuario?**  
Captura el evento de clic en el botón `#miBoton` y prueba hacer diferentes acciones.  

```js
let boton = document.getElementById("miBoton");
boton.addEventListener("click", function () {
    console.log("El botón fue clickeado.");
});
```

**Explora más:** ¿Puedes cambiar el color de fondo de la página con un clic?

## **Exploración 6: Contador con `localStorage`**  
¿Puedes hacer que un botón cuente cuántas veces ha sido clickeado y recordar ese número después de recargar la página?

```js
let contador = localStorage.getItem("contador") || 0;
document.getElementById("contador").textContent = contador;

let botonContador = document.getElementById("contadorBoton");
botonContador.addEventListener("click", function () {
    contador++;
    localStorage.setItem("contador", contador);
    document.getElementById("contador").textContent = contador;
});
```

**Explora más:** ¿Puedes hacer que el contador se reinicie cuando se alcance un número determinado?

## **Exploración 7: ¿Qué pasa cuando reseteamos el almacenamiento?**  
Observa cómo desaparecen los datos almacenados al reiniciar el contador.

```js
let resetBoton = document.getElementById("resetContador");
resetBoton.addEventListener("click", function () {
    localStorage.setItem("contador", 0);
    document.getElementById("contador").textContent = 0;
});
```

**Explora más:** ¿Cómo puedes hacer que el contador solo se borre después de una confirmación del usuario?

## **Exploración 8: Guardando objetos en `localStorage`**  
Prueba almacenar un objeto en `localStorage` y recuperar sus datos tras recargar la página.

```js
let usuario = { nombre: "Carlos", edad: 30 };
localStorage.setItem("usuario", JSON.stringify(usuario));

let usuarioGuardado = JSON.parse(localStorage.getItem("usuario"));
console.log(usuarioGuardado);
```

**Explora más:** ¿Cómo puedes actualizar solo una propiedad del objeto sin perder las demás?

## **Exploración 9: Creación dinámica de botones**  
Prueba crear un botón nuevo desde la consola y agrégalo a la página.

```js
let nuevoBoton = document.createElement("button");
nuevoBoton.textContent = "Botón dinámico";
document.body.appendChild(nuevoBoton);
```

**Explora más:** ¿Puedes hacer que este botón realice una acción específica al hacer clic?

## **Exploración 10: Capturando las teclas presionadas**  
Observa qué tecla está presionando el usuario en tiempo real.

```js
document.addEventListener("keydown", function (event) {
    console.log("Tecla presionada:", event.key);
});
```

**Explora más:** ¿Puedes hacer que la página cambie de color dependiendo de la tecla presionada?

## **Exploración 11: Creando una lista dinámicamente**  
Crea y agrega una lista con varios elementos al documento.

```js
let lista = document.createElement("ul");

for (let i = 1; i <= 3; i++) {
    let item = document.createElement("li");
    item.textContent = "Elemento " + i;
    lista.appendChild(item);
}

document.body.appendChild(lista);
```

**Explora más:** ¿Cómo puedes agregar elementos nuevos cuando el usuario hace clic en un botón?