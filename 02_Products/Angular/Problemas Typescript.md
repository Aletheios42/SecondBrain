### 1. Calculadora Básica
**Objetivo:**  
Desarrollar una calculadora simple en TypeScript que realice operaciones básicas: suma, resta, multiplicación y división.

**Pasos a seguir:**

1. **Definir funciones para cada operación:**  
   - Crea una función `add` que reciba dos números y retorne su suma.
   - Crea una función `subtract` que reciba dos números y retorne la diferencia.
   - Crea una función `multiply` que reciba dos números y retorne el producto.
   - Crea una función `divide` que reciba dos números y retorne el cociente.  
     - Asegúrate de verificar que el divisor no sea cero y, en ese caso, muestra un mensaje de error o retorna un valor especial (por ejemplo, `NaN` o `undefined`).

2. **Validación de entradas:**  
   - En cada función, asegúrate de que los parámetros sean de tipo `number` (esto lo hace TypeScript, pero puedes agregar validaciones extra si lo deseas).

3. **Prueba de la Calculadora:**  
   - Llama a cada función con ejemplos concretos (por ejemplo, `5 + 7`, `10 - 3`, `4 * 6`, `20 / 4` y también un ejemplo de división por cero).
   - Imprime el resultado de cada operación en la consola.

---
### 2. Gestor de Tareas
**Objetivo:**  
Crear una aplicación sencilla en TypeScript que permita gestionar una lista de tareas, incluyendo la posibilidad de agregar nuevas tareas, listarlas y marcarlas como completadas.

**Pasos a seguir:**

1. **Definir la estructura de una tarea:**  
   - Crea una interfaz llamada `Task` que contenga las siguientes propiedades:
     - `id`: número (único para cada tarea).
     - `description`: string (la descripción de la tarea).
     - `completed`: boolean (estado de la tarea; `false` por defecto).

2. **Almacenamiento de tareas:**  
   - Declara un array de tareas que actuará como la "base de datos" en memoria.

3. **Función para agregar una nueva tarea:**  
   - Implementa una función `addTask` que reciba una descripción y cree una nueva tarea con un `id` único y `completed` en `false`.
   - Agrega la nueva tarea al array de tareas.
   - Imprime un mensaje confirmando que la tarea ha sido agregada.

4. **Función para listar tareas:**  
   - Implementa una función `listTasks` que recorra el array e imprima cada tarea (puedes incluir el estado y el id).

5. **Función para marcar una tarea como completada:**  
   - Implementa una función `completeTask` que reciba un `id` y actualice el estado de la tarea a `completed = true`.
   - Si el `id` no existe, muestra un mensaje de error.

6. **Prueba del Gestor:**  
   - Agrega varias tareas utilizando `addTask`.
   - Marca al menos una tarea como completada.
   - Lista las tareas para verificar los cambios.
---
### 3. Administrador de Contactos
**Objetivo:**  
Crear un sistema simple en TypeScript para administrar contactos, permitiendo agregar, buscar y eliminar contactos.

**Pasos a seguir:**

1. **Definir la estructura de un contacto:**  
   - Crea una interfaz llamada `Contact` que contenga las siguientes propiedades:
     - `id`: número (único para cada contacto).
     - `name`: string (nombre del contacto).
     - `phone`: string (teléfono del contacto).
     - `email`: string (correo electrónico del contacto).

2. **Almacenamiento de contactos:**  
   - Declara un array de contactos para almacenar la información en memoria.

3. **Función para agregar un contacto:**  
   - Implementa una función `addContact` que reciba los datos del contacto y lo agregue al array.  
     - Puedes generar el `id` automáticamente (por ejemplo, incrementándolo).
     - Imprime un mensaje confirmando la adición del contacto.

4. **Función para buscar un contacto:**  
   - Implementa una función `searchContact` que reciba un string (parte del nombre) y retorne o imprima los contactos cuyo nombre contenga esa cadena (búsqueda parcial).

5. **Función para eliminar un contacto:**  
   - Implementa una función `removeContact` que reciba un `id` y elimine el contacto correspondiente del array.
   - Si el `id` no existe, muestra un mensaje de error.

6. **Prueba del Administrador de Contactos:**  
   - Agrega varios contactos utilizando `addContact`.
   - Realiza una búsqueda con `searchContact` para encontrar un contacto.
   - Elimina un contacto utilizando `removeContact`.
   - Lista los contactos restantes para verificar la eliminación.

---
## Solución 1: Calculadora Básica

```ts
// calculadora.ts

// 1. Función para sumar dos números
function add(a: number, b: number): number {
  return a + b;
}

// 2. Función para restar dos números
function subtract(a: number, b: number): number {
  return a - b;
}

// 3. Función para multiplicar dos números
function multiply(a: number, b: number): number {
  return a * b;
}

// 4. Función para dividir dos números (con validación de división por cero)
function divide(a: number, b: number): number | undefined {
  if (b === 0) {
    console.error("Error: División por cero.");
    return undefined;
  }
  return a / b;
}

// 5. Pruebas de la Calculadora
console.log("5 + 7 =", add(5, 7));
console.log("10 - 3 =", subtract(10, 3));
console.log("4 * 6 =", multiply(4, 6));

const divisionResult = divide(20, 4);
if (divisionResult !== undefined) {
  console.log("20 / 4 =", divisionResult);
}

// Prueba de división por cero:
divide(10, 0);
```

## Solución 2: Gestor de Tareas

```ts
// gestorTareas.ts

// 1. Definir la estructura de una tarea mediante una interfaz
interface Task {
  id: number;
  description: string;
  completed: boolean;
}

// 2. Array que actúa como "base de datos" en memoria
let tasks: Task[] = [];

// 3. Función para agregar una nueva tarea
function addTask(description: string): void {
  // Generar un id único (incremental)
  const id = tasks.length > 0 ? tasks[tasks.length - 1].id + 1 : 1;
  const newTask: Task = {
    id,
    description,
    completed: false,
  };
  tasks.push(newTask);
  console.log(`Tarea agregada: [ID: ${newTask.id}] ${newTask.description}`);
}

// 4. Función para listar todas las tareas
function listTasks(): void {
  console.log("\nListado de Tareas:");
  tasks.forEach((task) => {
    console.log(
      `ID: ${task.id} | Descripción: ${task.description} | Completada: ${task.completed ? "Sí" : "No"}`
    );
  });
}

// 5. Función para marcar una tarea como completada
function completeTask(id: number): void {
  const task = tasks.find((t) => t.id === id);
  if (task) {
    task.completed = true;
    console.log(`Tarea con ID ${id} marcada como completada.`);
  } else {
    console.log(`Error: No se encontró la tarea con ID ${id}.`);
  }
}

// 6. Pruebas del Gestor de Tareas
addTask("Comprar leche");
addTask("Enviar correo a cliente");
addTask("Realizar informe semanal");
listTasks();

completeTask(2);
listTasks();
```

---
## Solución 3: Administrador de Contactos

```ts
// administradorContactos.ts

// 1. Definir la estructura de un contacto mediante una interfaz
interface Contact {
  id: number;
  name: string;
  phone: string;
  email: string;
}

// 2. Array para almacenar los contactos y una variable para generar IDs
let contacts: Contact[] = [];
let nextContactId: number = 1;

// 3. Función para agregar un contacto
function addContact(name: string, phone: string, email: string): void {
  const contact: Contact = {
    id: nextContactId++,
    name,
    phone,
    email,
  };
  contacts.push(contact);
  console.log(`Contacto agregado: [ID: ${contact.id}] ${contact.name}`);
}

// 4. Función para buscar contactos por nombre (búsqueda parcial)
function searchContact(searchTerm: string): Contact[] {
  const results = contacts.filter((contact) =>
    contact.name.toLowerCase().includes(searchTerm.toLowerCase())
  );
  console.log(`\nResultados de búsqueda para "${searchTerm}":`);
  results.forEach((contact) => {
    console.log(
      `ID: ${contact.id} | Nombre: ${contact.name} | Tel: ${contact.phone} | Email: ${contact.email}`
    );
  });
  return results;
}

// 5. Función para eliminar un contacto por ID
function removeContact(id: number): void {
  const index = contacts.findIndex((contact) => contact.id === id);
  if (index !== -1) {
    const removed = contacts.splice(index, 1)[0];
    console.log(`Contacto eliminado: [ID: ${removed.id}] ${removed.name}`);
  } else {
    console.log(`Error: No se encontró contacto con ID ${id}.`);
  }
}

// 6. Pruebas del Administrador de Contactos
addContact("Juan Pérez", "123456789", "juan@example.com");
addContact("María López", "987654321", "maria@example.com");
addContact("Carlos García", "456789123", "carlos@example.com");

searchContact("mar");

removeContact(2);

console.log("\nContactos restantes:");
contacts.forEach((contact) => console.log(contact));
```