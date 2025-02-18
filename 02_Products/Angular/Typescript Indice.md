**Tags:** #_Todo
#ToTag #ToLink 
- - -
### **Introducción a TypeScript**

TypeScript (TS) es un superset tipado de JavaScript que agrega seguridad y escalabilidad al código. Desarrollado por Microsoft, TypeScript transpila a JavaScript estándar, permitiendo su ejecución en cualquier entorno compatible con ECMAScript. 

A diferencia de JavaScript, TypeScript introduce **tipado estático**, interfaces, clases avanzadas y herramientas de desarrollo como IntelliSense y refactorización mejorada. Se compila a través de `tsc` (TypeScript Compiler) y es compatible con cualquier versión de JavaScript.

### **Fundamentos del Lenguaje**

#### **Declaración de Variables**
- `let`: Variable mutable con ámbito de bloque.
- `const`: Variable inmutable, debe inicializarse al declararse.
- `var`: Obsoleto, evita su uso.

#### **Tipado Estático**
| Tipo        | Descripción                      |
| ----------- | -------------------------------- |
| `string`    | Cadenas de texto                 |
| `number`    | Números enteros y decimales      |
| `boolean`   | `true` o `false`                 |
| `null`      | Valor nulo intencional           |
| `undefined` | Variable sin valor asignado      |
| `bigint`    | Enteros de precisión arbitraria  |
| `any`       | Desactiva el tipado (evitar uso) |
| `unknown`   | Similar a `any`, pero más seguro |
| `never`     | Funciones que nunca retornan     |
| `void`      | Funciones que no retornan valor  |

Ejemplo de declaración tipada:
```ts
let nombre: string = "Carlos";
let edad: number = 25;
let activo: boolean = true;
```

#### **Inferencia de Tipos**
TypeScript puede inferir el tipo sin necesidad de declararlo explícitamente:
```ts
let mensaje = "Hola"; // TypeScript infiere que es string
```

### **Funciones y Parámetros Tipados**
#### **Declaración de Funciones**
```ts
function suma(a: number, b: number): number {
    return a + b;
}
```

#### **Parámetros Opcionales y Valores por Defecto**
```ts
function saludar(nombre: string, edad?: number) {
    console.log(`Hola, ${nombre}`);
}
saludar("Juan"); // Válido
```
### **Interfaces y Tipos Personalizados**

#### **Interfaces**
```ts
interface Persona {
    nombre: string;
    edad: number;
}
let usuario: Persona = { nombre: "Ana", edad: 30 };
```

#### **Tipos Personalizados (`type`)**
```ts
type ID = string | number;
let identificador: ID = 123;
```

### **Programación Orientada a Objetos (POO)**
#### **Clases y Modificadores de Acceso**
```ts
class Animal {
    protected nombre: string;
    constructor(nombre: string) {
        this.nombre = nombre;
    }
    saludar(): void {
        console.log(`Hola, soy ${this.nombre}`);
    }
}
```
#### **Herencia y `super()`**
```ts
class Perro extends Animal {
    constructor(nombre: string) {
        super(nombre);
    }
    ladrar(): void {
        console.log("Guau Guau!");
    }
}
```

### **Genéricos**
Permiten escribir código reutilizable y flexible:
```ts
function identidad<T>(valor: T): T {
    return valor;
}
console.log(identidad<string>("Hola"));
console.log(identidad<number>(42));
```

### **Manejo de Asincronía**
#### **Promesas y `async/await`**
```ts
async function obtenerDatos(): Promise<string> {
    return new Promise(resolve => {
        setTimeout(() => resolve("Datos recibidos"), 2000);
    });
}
obtenerDatos().then(console.log);
```

### **Módulos y Exportaciones**
#### **Exportación e Importación**
```ts
// archivo.ts
export function saludar() {
    return "Hola";
}
// main.ts
import { saludar } from "./archivo";
console.log(saludar());
```

### **Configuración y Compilación**
Instalar TypeScript:
```bash
npm install -g typescript
```
Compilar un archivo:
```bash
tsc archivo.ts
```
Generar un `tsconfig.json`:
```bash
tsc --init
```

### **Conclusión**
TypeScript proporciona un entorno robusto para el desarrollo escalable en JavaScript, mejorando la mantenibilidad y detección de errores. Su adopción es clave en proyectos modernos como Angular y NestJS.

- - - 
## ***Sources:***