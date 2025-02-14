**Tags:** #_Todo
#ToTag #ToLink 
- - -
## **1. Manipulación del DOM (Document Object Model)**
Permite acceder y modificar elementos HTML en la página.

### **Ejemplo: Cambiar el contenido de un elemento**
```js
document.getElementById("miElemento").innerText = "Nuevo contenido";
```

### **Ejemplo: Crear un nuevo elemento y agregarlo al DOM**
```js
const nuevoDiv = document.createElement("div");
nuevoDiv.innerText = "Hola, soy un nuevo div!";
document.body.appendChild(nuevoDiv);
```

## **2. Manejo de Eventos**
Permite responder a acciones del usuario, como clics o teclas presionadas.

### **Ejemplo: Escuchar un clic en un botón**
```js
document.getElementById("miBoton").addEventListener("click", () => {
    alert("¡Botón clickeado!");
});
```

### **Ejemplo: Capturar teclas presionadas**
```js
document.addEventListener("keydown", (evento) => {
    console.log(`Tecla presionada: ${evento.key}`);
});
```

## **3. Manipulación de CSS y Estilos**
Podemos cambiar estilos dinámicamente desde JavaScript.

### **Ejemplo: Cambiar el color de fondo**
```js
document.body.style.backgroundColor = "lightblue";
```

### **Ejemplo: Agregar o quitar clases**
```js
document.getElementById("miElemento").classList.add("clase-nueva");
```

## **4. Manejo del Local Storage y Session Storage**
Permite almacenar datos en el navegador.

### **Ejemplo: Guardar un dato**
```js
localStorage.setItem("usuario", "Juan");
console.log(localStorage.getItem("usuario")); // "Juan"
```

### **Ejemplo: Eliminar un dato**
```js
localStorage.removeItem("usuario");
```

## **5. Comunicación con el Servidor (AJAX y Fetch API)**
Permite hacer peticiones HTTP sin recargar la página.

### **Ejemplo: Obtener datos de una API con `fetch`**
```js
fetch("https://jsonplaceholder.typicode.com/todos/1")
    .then(response => response.json())
    .then(data => console.log(data));
```

## **6. Uso del `navigator` para Información del Navegador**
Accede a datos como la ubicación, el sistema operativo y la conexión.

### **Ejemplo: Ver el agente del usuario**
```js
console.log(navigator.userAgent);
```

### **Ejemplo: Acceder a la geolocalización**
```js
navigator.geolocation.getCurrentPosition(pos => {
    console.log(`Latitud: ${pos.coords.latitude}, Longitud: ${pos.coords.longitude}`);
});
```

## **7. Control de la Historia del Navegador (`history` y `location`)**
Permite cambiar la URL y manipular el historial.

### **Ejemplo: Redireccionar a otra página**
```js
window.location.href = "https://ejemplo.com";
```

### **Ejemplo: Navegar en el historial**
```js
history.back();  // Ir a la página anterior
history.forward();  // Ir a la siguiente página
```

## **8. WebSockets para Comunicación en Tiempo Real**
Permite enviar y recibir datos en tiempo real.

### **Ejemplo: Conectar a un WebSocket**
```js
const socket = new WebSocket("wss://echo.websocket.org");

socket.onopen = () => {
    socket.send("Hola, servidor!");
};

socket.onmessage = event => {
    console.log("Mensaje recibido:", event.data);
};
```

## 🔹 **9. APIs del Navegador**
JavaScript tiene acceso a muchas APIs avanzadas:

- **Clipboard API:** Copiar y pegar texto.
- **Notifications API:** Mostrar notificaciones en el escritorio.
- **Speech API:** Reconocimiento y síntesis de voz.
- **WebRTC:** Comunicación en tiempo real (cámaras, micrófonos).
### **Ejemplo: Mostrar una notificación**
```js
Notification.requestPermission().then(permission => {
    if (permission === "granted") {
        new Notification("Hola desde JS!");
    }
});
```
- - - 
## ***Sources:***