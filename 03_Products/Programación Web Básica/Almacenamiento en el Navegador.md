**MetaTags:** #_Todo
**Tags:** #ToTag #ToLink
- - -

#### **9.1. `localStorage` y `sessionStorage`**
- **`localStorage`**: Almacena datos de forma persistente en el navegador, incluso después de cerrar la pestaña o recargar la página.
- **`sessionStorage`**: Similar a `localStorage`, pero los datos solo persisten mientras dure la sesión del navegador.
```  js
localStorage.setItem("nombre", "Carlos");
console.log(localStorage.getItem("nombre")); // "Carlos"
sessionStorage.setItem("edad", "30");
console.log(sessionStorage.getItem("edad")); // "30"
```
- **Eliminar datos:**
```js
localStorage.removeItem("nombre"); // Elimina un solo item
localStorage.clear(); // Elimina todo el almacenamiento local
```

#### **9.2. Cookies y su manejo en JavaScript**
- Las **cookies** permiten almacenar información pequeña en el navegador y enviarla al servidor en cada solicitud HTTP.
- Se pueden establecer con `document.cookie`.
```js
document.cookie = "usuario=Ana; expires=Fri, 31 Dec 2024 23:59:59 UTC; path=/";
console.log(document.cookie);
```
- **Leer cookies:**
```js
console.log(document.cookie);
```
- **Eliminar cookies:**
```js
document.cookie = "usuario=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/";
```

#### **9.3. IndexedDB (introducción)**
- **IndexedDB** es una base de datos orientada a objetos en el navegador, más potente que `localStorage` y `sessionStorage`.
- Permite almacenar grandes volúmenes de datos y realizar consultas avanzadas.
- Ejemplo de apertura de una base de datos:
```js
let request = indexedDB.open("MiBaseDeDatos", 1);
request.onsuccess = function(event) {
    let db = event.target.result;
    console.log("Base de datos abierta correctamente", db);
};
request.onerror = function(event) {
    console.error("Error al abrir la base de datos", event);
};
```

- - - 
## ***Sources:***
