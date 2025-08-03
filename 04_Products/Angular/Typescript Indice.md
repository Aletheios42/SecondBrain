**Tags:** #_Todo
#ToTag #ToLink 
- - -
### **Instalación y configuración**
Para instalar TypeScript globalmente en el sistema, se utiliza `npm`:
```sh
npm install -g typescript
```
Para verificar la instalación y la versión instalada:
```sh
tsc --version
```
También se puede instalar localmente en un proyecto:
```sh
npm install --save-dev typescript
```
Para compilar archivos TypeScript sin configuración adicional:
```sh
tsc archivo.ts
```
También se puede usar la opción `--watch` para recompilar automáticamente al detectar cambios:
```sh
tsc --watch
```
### **Configuración de `tsconfig.json`**
Para configurar un proyecto TypeScript, se recomienda crear un archivo `tsconfig.json` con:
```sh
tsc --init
```
Este archivo define opciones de compilación. Un ejemplo básico:
```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "CommonJS",
    "strict": true,
    "outDir": "dist",
    "rootDir": "src",
    "esModuleInterop": true
  }
}
```

Explicación de opciones clave:
- **`target`**: Especifica la versión de ECMAScript a generar.
- **`module`**: Define el sistema de módulos (`CommonJS`, `ESNext`, etc.).
- **`strict`**: Habilita comprobaciones estrictas de tipos.
- **`outDir`** y **`rootDir`**: Especifican directorios de salida y origen.
- **`esModuleInterop`**: Mejora la interoperabilidad con módulos ES6.

Esto generará los archivos JavaScript en la carpeta definida en `outDir`.

### **Introducción a TypeScript**
TypeScript (TS) es un superset de JavaScript que agrega seguridad y escalabilidad al código. Desarrollado por Microsoft, TypeScript transpila a JavaScript estándar, permitiendo su ejecución en cualquier entorno compatible con ECMAScript. 

A diferencia de JavaScript, TypeScript introduce **tipado estático**, interfaces, clases avanzadas y herramientas de desarrollo como IntelliSense y refactorización mejorada. Se compila a través de `tsc` (TypeScript Compiler) y es compatible con cualquier versión de JavaScript.

TypeScript transpila a JavaScript estándar, lo que permite ejecutarlo en cualquier entorno que soporte ECMAScript.
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
Ejemplo: 
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

==Añadir==
- keyof typeof
- tipos condicionales
- tipos mapeados
- tipos con infer
- type vs interface
- union / intersecion
- namespace
- import
- creacion de bibliotecas
- Decoradores
- @for --> track
- - - 
## ***Sources:***
- https://www.typescriptlang.org/cheatsheets/