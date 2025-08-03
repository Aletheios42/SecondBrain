El laboratorio explora conceptos básicos de variables, operaciones, estructuras de control y funciones de manera interactiva familiarizandose con JavaScript ejecutando comandos en la consola del navegador.
## **Paso 1: Primer mensaje en la consola**
```js
console.log("Hola, JavaScript");
```
**Pregunta:** ¿Qué pasa si quitas las comillas?

## **Paso 2: Variables y tipos de datos**
```js
let nombre = "María";
let edad = 20;
let esEstudiante = true;
console.log(nombre, edad, esEstudiante);
```
**Pregunta:** ¿Qué sucede si intentas imprimir `apellido` sin haberlo definido?

## **Paso 3: Operaciones matemáticas**
```js
console.log(5 + 3);
console.log(10 - 4);
console.log(6 * 7);
console.log(20 / 5);
console.log(10 % 3);
```
**Pregunta:** ¿Qué ocurre si pruebas `"5" + 3`?

## **Paso 4: Concatenación de strings**
```js
let saludo = "Hola";
let persona = "Carlos";
console.log(saludo + ", " + persona + "!");
```
**Ejercicio:** Modifica el código para que combine tu nombre con una frase.

## **Paso 5: Entrada de datos con `prompt`**
```js
let nombreUsuario = prompt("¿Cómo te llamas?");
console.log("Bienvenido, " + nombreUsuario);
```
**Pregunta:** ¿Qué pasa si ingresas un número en `prompt`?

## **Paso 6: Condiciones (`if` y `else`)**
```js
let numero = Number(prompt("Ingresa un número:"));
if (numero > 0) {
    console.log("Es un número positivo");
} else if (numero < 0) {
    console.log("Es un número negativo");
} else {
    console.log("Es cero");
}
```
**Ejercicio:** Modifica el código para detectar si el número es par o impar.

## **Paso 7: Bucles (`for`)**
```js
for (let i = 1; i <= 5; i++) {
    console.log("Número:", i);
}
```
**Ejercicio:** Escribe un bucle que imprima los números del 10 al 1 en orden inverso.

## **Paso 8: Funciones**
```js
function saludar(nombre) {
    return "Hola, " + nombre + "!";
}
console.log(saludar("Ana"));
```
**Ejercicio:** Crea una función que devuelva el doble de un número.

## **Paso 9: Arrays y manipulación de datos**  

### **Crear un array y acceder a sus elementos**  
```js
let frutas = ["Manzana", "Banana", "Naranja"];
console.log(frutas[0]); // Primer elemento
console.log(frutas[1]); // Segundo elemento
console.log(frutas.length); // Cantidad de elementos
```
**Ejercicio:** Agrega otra fruta al array y muéstralo en consola.  

### **Modificar un array (agregar y eliminar elementos)**  
```js
frutas.push("Uva"); // Agrega al final
console.log(frutas);

frutas.pop(); // Elimina el último
console.log(frutas);

frutas.unshift("Mango"); // Agrega al inicio
console.log(frutas);

frutas.shift(); // Elimina el primero
console.log(frutas);
```
**Ejercicio:** Prueba qué sucede si usas `delete frutas[1]`.  

### **Recorrer un array con un bucle**  
```js
for (let i = 0; i < frutas.length; i++) {
    console.log(frutas[i]);
}
```
**Ejercicio:** Usa un `forEach` en lugar de un `for`.  

### **Buscar elementos en un array**  
```js
console.log(frutas.includes("Banana")); // ¿Existe en el array?
console.log(frutas.indexOf("Naranja")); // Posición en el array
```
**Ejercicio:** ¿Qué devuelve `indexOf` si el elemento no está en el array?  

## **Paso 10: Objetos en JavaScript**  

### **Definir un objeto con propiedades**  
```js
let persona = {
    nombre: "Carlos",
    edad: 30,
    profesion: "Ingeniero"
};
console.log(persona);
```
**Ejercicio:** Agrega una nueva propiedad al objeto y muéstrala en consola.  

### **Acceder y modificar valores de un objeto**  
```js
console.log(persona.nombre); // Acceder a una propiedad
persona.edad = 31; // Modificar un valor
console.log(persona.edad);
```
**Ejercicio:** Usa `delete` para eliminar una propiedad del objeto.  

### **Recorrer un objeto con un bucle**  
```js
for (let clave in persona) {
    console.log(clave + ": " + persona[clave]);
}
```
**Ejercicio:** Agrega una función dentro del objeto que imprima un saludo con su nombre.  

## **Paso 11: Métodos en strings y arrays**  

### **Strings: transformación y búsqueda**  
```js
let texto = "JavaScript es increíble";
console.log(texto.toUpperCase());
console.log(texto.toLowerCase());
console.log(texto.replace("increíble", "potente"));
console.log(texto.slice(0, 10)); // Extraer parte del string
```
**Ejercicio:** Usa `.split(" ")` para dividir la frase en un array de palabras.  

### **Métodos de arrays**  
```js
let numeros = [1, 2, 3, 4, 5];
let cuadrados = numeros.map(num => num * num);
console.log(cuadrados);
```
**Ejercicio:** Usa `.filter()` para obtener solo los números mayores a 2.  

## **Paso 12: Funciones avanzadas**  

### **Funciones con múltiples parámetros**  
```js
function multiplicar(a, b) {
    return a * b;
}
console.log(multiplicar(4, 5));
```
**Ejercicio:** Convierte esta función en una función flecha.  

### **Uso de `setTimeout` y `setInterval`**  
```js
setTimeout(() => console.log("Esto aparece después de 2 segundos"), 2000);
```
```js
let contador = 0;
let intervalo = setInterval(() => {
    contador++;
    console.log("Segundos:", contador);
    if (contador === 5) clearInterval(intervalo);
}, 1000);
```
**Ejercicio:** Modifica `setTimeout` para ejecutar una función propia.  

## **Paso 13: Manejo de errores y depuración**  

### **Capturar errores con `try...catch`**  
```js
try {
    let resultado = 10 / 0;
    console.log(resultado);
} catch (error) {
    console.log("Ocurrió un error:", error.message);
}
```
**Ejercicio:** Genera un error dividiendo un número por una variable no definida.  

## **Paso 14: Generación de números aleatorios**  

### **Número aleatorio entre 1 y 6 (simulación de un dado)**  
```js
let dado = Math.floor(Math.random() * 6) + 1;
console.log("Número del dado:", dado);
```
**Ejercicio:** Modifica el código para simular un lanzamiento de moneda (`Cara` o `Cruz`).  

### **Seleccionar un elemento aleatorio de un array**  
```js
let colores = ["Rojo", "Verde", "Azul", "Amarillo"];
let colorAleatorio = colores[Math.floor(Math.random() * colores.length)];
console.log("Color seleccionado:", colorAleatorio);
```
**Ejercicio:** Modifica el código para seleccionar una palabra aleatoria de una lista de frases motivacionales.  

## **Paso 16: Programación funcional con `map`, `filter` y `reduce`**  

### **Transformar un array con `map`**  
```js
let numerosDobles = numeros.map(num => num * 2);
console.log(numerosDobles);
```
**Ejercicio:** Usa `map` para convertir un array de nombres a mayúsculas.  

### **Filtrar elementos con `filter`**  
```js
let mayoresDeTres = numeros.filter(num => num > 3);
console.log(mayoresDeTres);
```
**Ejercicio:** Filtra los nombres que tienen más de cinco letras en un array de nombres.  

### **Reducir valores con `reduce`**  
```js
let sumaTotal = numeros.reduce((acumulador, num) => acumulador + num, 0);
console.log(sumaTotal);
```
**Ejercicio:** Usa `reduce` para calcular el producto de los elementos de un array.  

## **Conclusión**
- Se exploraron temas más avanzados de JavaScript en la consola.  
- La manipulación de arrays y objetos es fundamental en el desarrollo web.  
- `localStorage` permite almacenar datos de forma persistente en el navegador.  
- `map`, `filter` y `reduce` son métodos esenciales en la programación funcional.  