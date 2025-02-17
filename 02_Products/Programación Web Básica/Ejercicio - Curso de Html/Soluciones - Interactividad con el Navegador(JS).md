
```js
// 1. Modificar el texto de un elemento
const cambiarTextoBtn = document.createElement("button");
cambiarTextoBtn.innerText = "Cambiar Texto";
cambiarTextoBtn.addEventListener("click", () => {
    document.getElementById("miElemento").innerText = "Nuevo contenido";
    alert("Se ha cambiado el texto del elemento.");
});
document.body.appendChild(cambiarTextoBtn);

// 2. Agregar un nuevo elemento al DOM
const agregarElementoBtn = document.createElement("button");
agregarElementoBtn.innerText = "Agregar Elemento";
agregarElementoBtn.addEventListener("click", () => {
    const nuevoDiv = document.createElement("div");
    nuevoDiv.innerText = "Soy un nuevo div";
    nuevoDiv.classList.add("caja");
    document.getElementById("contenedor").appendChild(nuevoDiv);
    alert("Nuevo div agregado");
});
document.body.appendChild(agregarElementoBtn);

// 3. Cambiar estilo de un elemento
const cambiarEstiloBtn = document.createElement("button");
cambiarEstiloBtn.innerText = "Cambiar Estilo";
cambiarEstiloBtn.addEventListener("click", () => {
    document.getElementById("miElemento").classList.toggle("destacada");
    alert("Se ha cambiado el estilo del elemento.");
});
document.body.appendChild(cambiarEstiloBtn);

// 4. Guardar y leer datos de LocalStorage
localStorage.setItem("mensaje", "Hola, almacenado en LocalStorage");
const leerLocalBtn = document.createElement("button");
leerLocalBtn.innerText = "Leer LocalStorage";
leerLocalBtn.addEventListener("click", () => {
    alert(localStorage.getItem("mensaje"));
});
document.body.appendChild(leerLocalBtn);

// 5. Hacer una petición a una API
const fetchAPIBtn = document.createElement("button");
fetchAPIBtn.innerText = "Obtener Datos API";
fetchAPIBtn.addEventListener("click", () => {
    fetch("https://jsonplaceholder.typicode.com/todos/1")
        .then(response => response.json())
        .then(data => alert(`Título: ${data.title}`));
});
document.body.appendChild(fetchAPIBtn);

// 6. Capturar la tecla presionada
document.addEventListener("keydown", (evento) => {
    alert(`Tecla presionada: ${evento.key}`);
});

// 7. Mostrar información del navegador
alert(`Tu navegador es: ${navigator.userAgent}`);

// 8. Redireccionar a otra página
const redirigirBtn = document.createElement("button");
redirigirBtn.innerText = "Ir a ejemplo.com";
redirigirBtn.addEventListener("click", () => {
    window.location.href = "https://ejemplo.com";
});
document.body.appendChild(redirigirBtn);

// 9. Usar geolocalización
navigator.geolocation.getCurrentPosition(pos => {
    alert(`Latitud: ${pos.coords.latitude}, Longitud: ${pos.coords.longitude}`);
});

// 10. Conectar con WebSocket
const socket = new WebSocket("wss://echo.websocket.org");
socket.onopen = () => {
    alert("Conexión WebSocket abierta. Enviando mensaje...");
    socket.send("Hola, servidor!");
};
socket.onmessage = event => {
    alert(`Mensaje recibido: ${event.data}`);
};
```