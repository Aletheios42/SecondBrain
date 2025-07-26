**MetaTags:** #_Todo
**Tags:** #Desarrollo #Web #Javascript 
- - -
El Dom es un objeto de javascript en forma de arbol que representa la pagina

se puede ver en la cosolola del navegador con console.dir(Document)

### **DOM y Manipulación de la Interfaz**
#### **¿Qué es el DOM? Árbol de nodos**
- El **DOM (Document Object Model)** representa la estructura jerárquica de un documento HTML en forma de árbol de nodos.
- Permite acceder, modificar y manipular elementos HTML mediante JavaScript.

#### **Selección de elementos (`getElementById`, `querySelector`, etc.)**
- `document.getElementById(id)`: Selecciona un elemento por su `id`.
- `document.querySelector(selector)`: Devuelve el primer elemento que coincida con un selector CSS.
- `document.querySelectorAll(selector)`: Devuelve una lista de nodos que coinciden con el selector.
```js
const titulo = document.getElementById("titulo");
const parrafos = document.querySelectorAll("p");
```

#### **Modificación del contenido (`textContent`, `innerHTML`, `setAttribute`)**
- `element.textContent`: Modifica solo el texto dentro de un elemento.
- `element.innerHTML`: Modifica el HTML interno (puede ser riesgoso si se usa con entrada de usuario).
- `element.setAttribute(nombre, valor)`: Modifica atributos del elemento.
```js
titulo.textContent = "Nuevo Título";
titulo.setAttribute("class", "destacado");
```

#### **Creación y eliminación de elementos (`createElement`, `appendChild`, `removeChild`)**
- `document.createElement(etiqueta)`: Crea un nuevo nodo HTML.
- `element.appendChild(nodo)`: Agrega un nodo hijo.
- `element.removeChild(nodo)`: Elimina un nodo hijo.
```js
const nuevoParrafo = document.createElement("p");
nuevoParrafo.textContent = "Este es un párrafo nuevo";
document.body.appendChild(nuevoParrafo);
```

#### **Eventos y `addEventListener`**
- Se pueden agregar eventos a los elementos para detectar interacciones del usuario.
- `element.addEventListener("evento", función)`: Asocia un evento a un elemento.
```js
document.getElementById("boton").addEventListener("click", () => {
    alert("Botón clickeado");
});
```

#### **Delegación de eventos**
- Se usa cuando hay elementos dinámicos y no se pueden asignar eventos a cada uno manualmente.
- Se captura el evento en un elemento padre y se verifica el origen del evento.
```js
document.getElementById("lista").addEventListener("click", (event) => {
    if (event.target.tagName === "LI") {
        console.log("Clic en", event.target.textContent);
    }
});
```

- - - 
#### ***Sources:***
- https://www.youtube.com/watch?v=MPFeE4_veXE