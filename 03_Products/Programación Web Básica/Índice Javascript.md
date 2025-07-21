- [ ] **Tags:** #_Todo
#Javascript #ToLink 
- - -
### **Introducción a JavaScript**  
JavaScript (JS) es un lenguaje de programación dinámico, de un solo hilo y basado en prototipos, que admite paradigmas orientados a objetos, imperativos y funcionales. Su ejecución es interpretada o compilada justo a tiempo (JIT), proporcionando flexibilidad y alto rendimiento. Regulado por el estándar ECMAScript, ha evolucionado con versiones clave como **ES5** (2009), que introdujo `strict mode` y `JSON.parse()`, y **ES6** (2015), que añadió `let`, `const`, funciones flecha, clases y módulos. **ESNext** continúa incorporando características como `async/await`, `optional chaining` y `BigInt`.

JavaScript está integrado en todos los navegadores modernos, eliminando la necesidad de instalación. Puede ejecutarse directamente en la consola del navegador (`F12` → Consola). Para entornos fuera del navegador, se emplea **Node.js**

A diferencia de html y css, si el navegador detecta codigo javascript qmal escript este dejara de parsear el documento y lanzara un error.

El potencial publicitario de internet motivo a ethan 
La consola del navegador permite ejecutar código en tiempo real, depurar errores y monitorear variables. `console.log()` se usa para imprimir información:
### **Fundamentos del Lenguaje**
##### Comentarios
// : para comentar lineas
/* */: para comentar parrafos 

#### **Variables y constantes**
- `var`: Declaración obsoleta con ámbito de función.
- `let`: Variable con ámbito de bloque, permite reasignación.
- `const`: Variable de solo lectura, no permite reasignación.
##### Valores "Negativos"
- NaN: Es un valor numerico que representa un valor no numerico: Ej: 0 / 0 = NaN, typeof(NaN) = number
- Null: pagina de memoria cuya referencia es 0, es decir 0x0000
- Undefined: no hay referencia
- 0: es un int, 0 de toda la vida
![IMG](variables_nulas.png)
#### **Tipos de datos primitivos**
| Tipo        | Descripción                     |
| ----------- | ------------------------------- |
| `string`    | Cadenas de texto                |
| `number`    | Números enteros y decimales     |
| `boolean`   | `true` o `false`                |
| `null`      | Valor nulo intencional          |
| `undefined` | Variable declarada sin valor    |
| `symbol`    | Identificadores únicos          |
| `bigint`    | Enteros de precisión arbitraria |
#### **Operadores**
- **Aritméticos**: `+`, `-`, `*`, `/`, `%`, `**`
- **Comparación**: `==`, `!=`, `===`, `!==`, `>`, `<`, `>=`, `<=`
- **Lógicos**: `&&`, `||`, `!`
- **Ternario**: `condición ? valor_si_verdadero : valor_si_falso`
#### **Conversión de tipos**
- `parseInt()`, `parseFloat()`: Convertir cadenas a números.
- `Number()`: Conversión directa a número.
- `String()`: Conversión a cadena de texto.
- `Boolean()`: Conversión a booleano (`0`, `null`, `undefined` → `false`).
### **Control de Flujo**
#### **Condicionales**
- `if` / `else if` / `else`: Evaluación de condiciones secuenciales.
- `switch`: Evaluación de múltiples casos con `case` y `default`.
#### **Bucles**
| Bucle      | Descripción                                                 |
| ---------- | ----------------------------------------------------------- |
| `for`      | Iteración con contador definido.                            |
| `while`    | Bucle basado en una condición.                              |
| `do while` | Ejecuta al menos una vez antes de evaluar la condición.     |
| `for...in` | Itera sobre propiedades de un objeto.                       |
| `for...of` | Itera sobre valores de un iterable (arrays, strings, etc.). |
#### **Manejo de Errores**
- `try...catch`: Captura y maneja errores en tiempo de ejecución.
- `throw`: Lanza un error manualmente.
- `finally`: Bloque opcional que se ejecuta siempre, haya o no error.
### **Funciones y Ámbito**
#### **Declaración y expresión de funciones**
- **Declaración de función:** Se define con `function nombre() {}` y puede llamarse antes de su declaración debido al **hoisting**.
- **Expresión de función:** Se asigna a una variable (`const fn = function() {}`) y no se puede invocar antes de su asignación.
#### **Parámetros y valores por defecto**
- Los parámetros de una función pueden tener valores predeterminados que se usan si no se pasa un argumento.
- Evita la necesidad de comprobar si un parámetro es `undefined` dentro de la función.
```js
function saludo(nombre = "Usuario", edad = 18) {
    console.log(`Hola, ${nombre}. Tienes ${edad} años.`);
}
saludo(); // "Hola, Usuario. Tienes 18 años."
saludo("Ana"); // "Hola, Ana. Tienes 18 años."
saludo("Ana", 30); // "Hola, Ana. Tienes 30 años."
```
#### **Funciones Flecha (`=>`)**
- Sintaxis más corta para funciones anónimas.
- No tienen su propio `this`, sino que heredan del contexto léxico.
```js
const suma = (a, b) => a + b;
console.log(suma(2, 3)); // 5
```
#### **Closures y Ámbito Léxico**
- Un **closure** ocurre cuando una función interna recuerda el ámbito en el que fue definida, incluso después de que la función externa haya terminado su ejecución.
- Esto permite crear funciones con un estado encapsulado.
```js
function contador(inicial) {
    let valor = inicial;
    return function incrementar() {
        valor++;
        return valor;
    };
}
const contarDesdeCinco = contador(5);
console.log(contarDesdeCinco()); // 6
console.log(contarDesdeCinco()); // 7
```
#### **Funciones de orden superior y callbacks**
- Una **función de orden superior** recibe otra función como parámetro o devuelve una función.
- Un **callback** es una función pasada como argumento a otra función para ser ejecutada posteriormente.
```js
function operar(a, b, operacion) {
    return operacion(a, b);
}
const multiplicar = (x, y) => x * y;
console.log(operar(3, 4, multiplicar)); // 12

// Ejemplo de callback con `setTimeout`
setTimeout(() => console.log("Esto se ejecuta después de 2 segundos"), 2000);
```
### **Objetos y Programación Orientada a Objetos (POO)**
#### **Introducción a los objetos (`{ clave: valor }`)**
- En JavaScript, un objeto es una colección de pares clave-valor.
- Se pueden crear con **literales de objeto**, el constructor `Object()`, o `Object.create()`.
```js
const persona = { nombre: "Ana", edad: 30 };
console.log(persona.nombre); // "Ana"
```
#### **Propiedades y métodos de objetos**
- **Propiedades**: Son valores asociados a una clave dentro del objeto.
- **Métodos**: Son funciones definidas dentro de un objeto.
```js
const usuario = {
    nombre: "Carlos",
    saludar() {
        console.log(`Hola, soy ${this.nombre}`);
    }
};
usuario.saludar(); // "Hola, soy Carlos"
```
#### **`this` y su comportamiento**
- `this` hace referencia al objeto que llama al método.
- Su valor cambia dependiendo del **contexto de ejecución**.
```js
const objeto = {
    valor: 42,
    mostrar() {
        console.log(this.valor);
    }
};
objeto.mostrar(); // 42
```
#### **Clases y `class` en ES6**
- Introducen una sintaxis más clara para la creación de objetos basados en prototipos.
- Se definen con la palabra clave `class`.
```js
class Persona {
    constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
    }
    saludar() {
        console.log(`Hola, soy ${this.nombre}`);
    }
}
const juan = new Persona("Juan", 25);
juan.saludar(); // "Hola, soy Juan"
```
#### **Herencia con `extends` y `super`**
- `extends` permite que una clase herede propiedades y métodos de otra.
- `super` llama al constructor de la clase padre.
```js
class Estudiante extends Persona {
    constructor(nombre, edad, curso) {
        super(nombre, edad);
        this.curso = curso;
    }
}
const maria = new Estudiante("María", 22, "JavaScript");
console.log(maria.curso); // "JavaScript"
```
#### **Getters, setters y `static`**
- **Getters (`get`)**: Permiten acceder a propiedades calculadas.
- **Setters (`set`)**: Permiten modificar propiedades con validación.
- **`static`**: Define métodos que pertenecen a la clase, no a las instancias.
```js
class Circulo {
    constructor(radio) {
        this.radio = radio;
    }
    get diametro() {
        return this.radio * 2;
    }
    set diametro(valor) {
        this.radio = valor / 2;
    }
    static info() {
        return "Esta es una clase para círculos";
    }
}
const c = new Circulo(5);
console.log(c.diametro); // 10
c.diametro = 20;
console.log(c.radio); // 10
console.log(Circulo.info()); // "Esta es una clase para círculos"
```
### **Arrays y Métodos Avanzados**
#### **Creación y manipulación de arrays**
- Un **array** es una estructura de datos ordenada.
- Se pueden declarar con `[]` o con `new Array()`.
```js
const numeros = [1, 2, 3, 4, 5];
console.log(numeros[0]); // 1
```
- Métodos de modificación:
  - `push()`: Agrega un elemento al final.
  - `pop()`: Elimina el último elemento.
  - `shift()`: Elimina el primer elemento.
  - `unshift()`: Agrega un elemento al inicio.
  - `splice()`: Modifica el array (añadiendo o eliminando elementos).
```js
let frutas = ["manzana", "plátano"];
frutas.push("naranja");
console.log(frutas); // ["manzana", "plátano", "naranja"]
#### **Métodos importantes**
    mirar: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
```
| Método      | Descripción                                                 |
| ----------- | ----------------------------------------------------------- |
| `map()`     | Crea un nuevo array aplicando una función a cada elemento.  |
| `filter()`  | Filtra elementos según una condición.                       |
| `reduce()`  | Reduce el array a un solo valor acumulando resultados.      |
| `forEach()` | Ejecuta una función para cada elemento.                     |
| `find()`    | Devuelve el primer elemento que cumpla una condición.       |
| `some()`    | Retorna `true` si algún elemento cumple la condición.       |
| `every()`   | Retorna `true` si todos los elementos cumplen la condición. |
```js

const numeros = [1, 2, 3, 4, 5];
const cuadrados = numeros.map(n => n * n);
console.log(cuadrados); // [1, 4, 9, 16, 25]
```
#### **Desestructuración y spread/rest operators**
- **Desestructuración:** Extrae valores de arrays y objetos en variables individuales.
```js
const [a, b, c] = [10, 20, 30];
console.log(a, b, c); // 10 20 30
```
- **Spread operator (`...`)**: Expande arrays u objetos.
```js
const numeros1 = [1, 2, 3];
const numeros2 = [...numeros1, 4, 5];
console.log(numeros2); // [1, 2, 3, 4, 5]
```
- **Rest operator (`...`)**: Agrupa valores en una función.
```js
function sumar(...valores) {
    return valores.reduce((a, b) => a + b, 0);
}
console.log(sumar(1, 2, 3, 4)); // 10
```
### **Asincronía y Manejo de Promesas**
#### **Introducción a la asincronía**
- JavaScript es **single-threaded**, lo que significa que ejecuta código en un solo hilo.
- Para evitar bloqueos, usa un modelo **asíncrono y basado en eventos**.
- La asincronía permite ejecutar tareas en segundo plano sin bloquear el flujo principal.
#### ** `setTimeout()` y `setInterval()`**
- `setTimeout(función, tiempo)`: Ejecuta una función después de un tiempo determinado (ms).
- `setInterval(función, tiempo)`: Ejecuta una función repetidamente en intervalos de tiempo.
```js
console.log("Inicio");
setTimeout(() => console.log("Ejecutado después de 2 segundos"), 2000);
console.log("Fin");
```
#### ** Promesas (`Promise`, `resolve`, `reject`, `then`, `catch`, `finally`)**
- Una **Promise** representa una operación asincrónica con tres estados:
  - `pending`: En espera.
  - `fulfilled`: Resuelta con éxito.
  - `rejected`: Ocurrió un error.
```js
const promesa = new Promise((resolve, reject) => {
    setTimeout(() => resolve("Éxito"), 2000);
});

promesa.then(resultado => console.log(resultado)).catch(error => console.error(error));
```
#### ** `async/await` y su sintaxis**
- `async` convierte una función en asíncrona y devuelve una **Promise**.
- `await` pausa la ejecución hasta que una **Promise** se resuelva.
```js
async function obtenerDatos() {
    let respuesta = await fetch("https://jsonplaceholder.typicode.com/todos/1");
    let datos = await respuesta.json();
    console.log(datos);
}
obtenerDatos();
```
#### ** `fetch()` y manejo de peticiones HTTP**
- `fetch(url)` devuelve una **Promise** que resuelve en una respuesta HTTP.
- Se usa para hacer peticiones GET, POST, PUT, DELETE.
```js
fetch("https://jsonplaceholder.typicode.com/posts/1")
    .then(res => res.json())
    .then(datos => console.log(datos))
    .catch(error => console.error("Error en la petición", error));
```
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

### **Módulos y Desarrollo Escalable**

#### **Módulos en ES6 (`import` y `export`)**
- Permiten dividir el código en archivos reutilizables.
- Se usa `export` para exponer funciones o variables y `import` para utilizarlas en otro archivo.
```js
// archivo utilidades.js
export function saludar(nombre) {
    return `Hola, ${nombre}`;
}
// archivo principal.js
import { saludar } from "./utilidades.js";
console.log(saludar("Carlos"));
```

#### **Organización de código en múltiples archivos**
- Separar la lógica en archivos específicos mejora la mantenibilidad y escalabilidad.
- Ejemplo de estructura de un proyecto modular:
```
/proyecto
│── index.html
│── main.js
│── /modulos
│   ├── usuario.js
│   ├── productos.js
│   └── carrito.js
```

#### **Uso de herramientas como Webpack y Vite**
- **Webpack**: Empaqueta archivos y sus dependencias en un solo archivo optimizado.
- **Vite**: Ofrece un entorno de desarrollo más rápido con hot reload.
```bash
npm install --save-dev webpack vite
```
### **Buenas Prácticas y Conceptos Avanzados**

#### **Principios SOLID en JavaScript**
- **S**ingle Responsibility: Cada módulo debe tener una única responsabilidad.
- **O**pen/Closed: El código debe ser extensible sin modificarlo.
- **L**iskov Substitution: Una subclase debe ser sustituible por su superclase.
- **I**nterface Segregation: Interfaces específicas en lugar de generales.
- **D**ependency Inversion: Los módulos de alto nivel no deben depender de los de bajo nivel.
#### **Patrones de diseño comunes**
- **Factory Pattern**: Crea objetos sin especificar la clase exacta.
- **Singleton Pattern**: Garantiza una única instancia de una clase.
- **Observer Pattern**: Permite que objetos reaccionen a cambios en otros.
```js
class Singleton {
    static instance;
    constructor() {
        if (!Singleton.instance) {
            Singleton.instance = this;
        }
        return Singleton.instance;
    }
}
```
#### **Evitar el callback hell**
- Usar **promesas** y `async/await` en lugar de múltiples callbacks anidados.
```js
async function obtenerDatos() {
    let datos = await fetch("https://jsonplaceholder.typicode.com/posts");
    return await datos.json();
}
obtenerDatos().then(data => console.log(data));
```
#### **Testing en JavaScript (Jest, Mocha)**
- **Jest** y **Mocha** son herramientas populares para realizar pruebas unitarias.
```bash
npm install --save-dev jest
```
```js
// test.js
const suma = (a, b) => a + b;
test("Suma de 2 + 2 es 4", () => {
    expect(suma(2, 2)).toBe(4);
});


## Interacion con localStorage

[[Almacenamiento en el Navegador]]
```
- - - 
## ***Sources:***
-  [Curso de Dessarrollo Web](https://developer.mozilla.org/en-US/docs/Web/JavaScript 
- [Espécificación Oficial](https://tc39.es/ecma262/
- [Cheatsheet JS](https://htmlcheatsheet.com/js/
- [Libro corto sobre la web](https://resilientwebdesign.com/

