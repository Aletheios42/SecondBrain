## Índice

1. **Instalación y Configuración**  
   1.1 Instalación Global y Local  
   1.2 Verificación de la Instalación  
   1.3 Compilación y Modo Watch  

2. **Configuración de `tsconfig.json`**  
   2.1 Generación del Archivo  
   2.2 Ejemplo Básico y Explicación de Opciones  

3. **Introducción a TypeScript**  
   3.1 ¿Qué es TypeScript?  
   3.2 Ventajas y Diferencias con JavaScript  

4. **Fundamentos del Lenguaje**  
   4.1 Declaración de Variables  
   4.2 Tipado Estático y Tipos Primitivos  
   4.3 Inferencia de Tipos  

5. **Funciones y Parámetros Tipados**  
   5.1 Declaración de Funciones  
   5.2 Parámetros Opcionales y Valores por Defecto  

6. **Interfaces y Tipos Personalizados**  
   6.1 Uso de Interfaces  
   6.2 Alias de Tipos (`type`)  
   6.3 Comparación: `type` vs `interface`  
   6.4 Uniones e Intersecciones  

7. **Programación Orientada a Objetos (POO)**  
   7.1 Clases y Modificadores de Acceso  
   7.2 Herencia y Uso de `super()`  

8. **Genéricos**  
   8.1 Funciones y Clases Genéricas  

9. **Manejo de Asincronía**  
   9.1 Uso de Promesas  
   9.2 `async/await`  

10. **Módulos y Exportaciones**  
    10.1 Exportación e Importación de Módulos  
    10.2 Uso de Namespaces  

11. **Temas Avanzados en TypeScript**  
    11.1 Uso de `keyof typeof`  
    11.2 Tipos Condicionales  
    11.3 Tipos Mapeados  
    11.4 Inferencia Avanzada con `infer`  
    11.5 Creación de Bibliotecas  
    11.6 Decoradores (experimental)  
    11.7 Directivas Avanzadas (por ejemplo, @for – track)  

12. **Conclusión y Recomendaciones**

---

## 1. Instalación y Configuración

Para instalar TypeScript globalmente se utiliza:
```sh
npm install -g typescript
```
Verifica la instalación y la versión instalada:
```sh
tsc --version
```
También puedes instalarlo localmente para un proyecto:
```sh
npm install --save-dev typescript
```
Para compilar un archivo TypeScript sin configuración adicional:
```sh
tsc archivo.ts
```
Y para observar cambios en tiempo real (modo watch):
```sh
tsc --watch
```

---

## 2. Configuración de `tsconfig.json`

Para iniciar un proyecto con TypeScript se recomienda generar un archivo de configuración:

```sh
tsc --init
```

Un ejemplo básico de `tsconfig.json` es:

```json
{
  "compilerOptions": {
    "target": "ES6",               // Versión de ECMAScript a generar.
    "module": "CommonJS",          // Sistema de módulos.
    "strict": true,                // Habilita comprobaciones estrictas de tipos.
    "outDir": "dist",              // Directorio de salida de los archivos JavaScript.
    "rootDir": "src",              // Directorio de origen de los archivos TypeScript.
    "esModuleInterop": true        // Facilita la interoperabilidad con módulos ES6.
  }
}
```

Cada opción es clave para configurar el entorno de compilación y adaptarlo a las necesidades del proyecto.

---

## 3. Introducción a TypeScript

TypeScript es un superset de JavaScript que agrega **tipado estático**, interfaces, clases y otras características que mejoran la escalabilidad y mantenibilidad del código.

- **Ventajas:**
  - Mejora la detección de errores en tiempo de compilación.
  - Facilita el mantenimiento en proyectos grandes.
  - Provee herramientas de desarrollo como IntelliSense y refactorización avanzada.

- **Compatibilidad:**
  - Transpila a JavaScript estándar, por lo que puede ejecutarse en cualquier entorno compatible con ECMAScript (navegadores, Node.js, etc.).

---

## 4. Fundamentos del Lenguaje

### 4.1 Declaración de Variables

- **`let`**: Declara variables con alcance de bloque y permite reasignación.
- **`const`**: Declara variables inmutables, deben inicializarse en el momento de la declaración.
- **`var`**: Su uso está obsoleto debido a problemas de ámbito y hoisting.

### 4.2 Tipado Estático y Tipos Primitivos

| Tipo        | Descripción                                              |
| ----------- | -------------------------------------------------------- |
| `string`    | Cadenas de texto                                         |
| `number`    | Números enteros y decimales                              |
| `boolean`   | Valores `true` o `false`                                 |
| `null`      | Valor nulo intencional                                   |
| `undefined` | Variable sin valor asignado                              |
| `bigint`    | Números enteros de precisión arbitraria                  |
| `any`       | Desactiva el tipado (se recomienda evitarlo)             |
| `unknown`   | Similar a `any`, pero con mayor seguridad                |
| `never`     | Funciones que nunca retornan (p.ej., lanzan excepciones) |
| `void`      | Funciones que no retornan valor                          |

_**Ejemplo:**_

```ts
let nombre: string = "Carlos";
let edad: number = 25;
let activo: boolean = true;
```

### 4.3 Inferencia de Tipos

TypeScript puede determinar el tipo de una variable basándose en su valor inicial, sin necesidad de una anotación explícita:

```ts
let mensaje = "Hola"; // Se infiere que es string
```

---
## 5. Funciones y Parámetros Tipados

### 5.1 Declaración de Funciones

Las funciones se pueden tipar especificando los tipos de sus parámetros y su valor de retorno:

```ts
function suma(a: number, b: number): number {
    return a + b;
}
```

### 5.2 Parámetros Opcionales y Valores por Defecto

Se pueden definir parámetros opcionales (con `?`) o asignarles valores por defecto:

```ts
function saludar(nombre: string, edad: number = 30): void {
    console.log(`Hola, ${nombre}`);
}
saludar("Juan"); // Llama a la función sin pasar el segundo parámetro
```

---

## 6. Interfaces y Tipos Personalizados

### 6.1 Interfaces

Las interfaces definen la forma de un objeto, facilitando la verificación del cumplimiento de una estructura:

```ts
interface Persona {
    nombre: string;
    edad: number;
}
let usuario: Persona = { nombre: "Ana", edad: 30 };
```

### 6.2 Alias de Tipos (`type`)

Los alias de tipos permiten definir tipos complejos o uniones:

```ts
type ID = string | number;
let identificador: ID = 123;
```

### 6.3 Comparación: `type` vs `interface`

- **Interfaces**:  
  - Se pueden extender y fusionar.
  - Se usan principalmente para definir la forma de objetos.

- **Types**:  
  - Permiten definir uniones e intersecciones.
  - Son ideales para tipos complejos, aunque son inmutables una vez definidos.

### 6.4 Uniones e Intersecciones

- **Uniones** permiten que una variable tenga uno de varios tipos posibles:
  
  ```ts
  type Rol = "admin" | "usuario";
  ```

- **Intersecciones** combinan propiedades de múltiples tipos:
  
  ```ts
  interface A { a: number; }
  interface B { b: string; }
  type AB = A & B;
  ```

---

## 7. Programación Orientada a Objetos (POO)

### 7.1 Clases y Modificadores de Acceso

Las clases permiten encapsular datos y comportamientos. Se pueden usar modificadores como `public`, `protected` y `private` para controlar el acceso:

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

### 7.2 Herencia y `super()`

La herencia permite crear clases derivadas que extienden la funcionalidad de una clase base:

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

---

## 8. Genéricos

Los genéricos permiten escribir código reutilizable y adaptable a múltiples tipos sin perder el tipado:

```ts
function identidad<T>(valor: T): T {
    return valor;
}
console.log(identidad<string>("Hola"));
console.log(identidad<number>(42));
```

---

## 9. Manejo de Asincronía

### 9.1 Uso de Promesas

TypeScript utiliza las mismas APIs de Promesas que JavaScript para manejar operaciones asíncronas.

### 9.2 `async/await`

La sintaxis `async/await` facilita la escritura de código asíncrono de forma secuencial:

```ts
async function obtenerDatos(): Promise<string> {
    return new Promise(resolve => {
        setTimeout(() => resolve("Datos recibidos"), 2000);
    });
}
obtenerDatos().then(console.log);
```

---

## 10. Módulos y Exportaciones

### 10.1 Exportación e Importación

Para dividir el código en módulos se utiliza la sintaxis de exportación e importación:

```ts
// archivo.ts
export function saludar() {
    return "Hola";
}

// main.ts
import { saludar } from "./archivo";
console.log(saludar());
```

### 10.2 Uso de Namespaces

Los *namespaces* agrupan lógicamente el código y ayudan a evitar conflictos en el espacio global:

```ts
namespace Utilidades {
    export function log(mensaje: string): void {
        console.log("Log:", mensaje);
    }
}
Utilidades.log("Mensaje desde el namespace");
```

---

## 11. Temas Avanzados en TypeScript

### 11.1 Uso de `keyof typeof`

Permite extraer las claves de un objeto literal para usarlas como tipos:
```ts
const colores = {
    rojo: "#FF0000",
    verde: "#00FF00",
    azul: "#0000FF"
};
type ColorKeys = keyof typeof colores; // "rojo" | "verde" | "azul"
```

### 11.2 Tipos Condicionales

Los tipos condicionales definen tipos basados en condiciones:

```ts
type EsNumero<T> = T extends number ? "Número" : "No es un número";
```

### 11.3 Tipos Mapeados

Transforman sistemáticamente las propiedades de un tipo:

```ts
type Opcional<T> = {
    [P in keyof T]?: T[P];
};
```

### 11.4 Inferencia Avanzada con `infer`

Extrae tipos de estructuras complejas utilizando la palabra clave `infer`:

```ts
type Retorno<T> = T extends (...args: any[]) => infer R ? R : never;
```

### 11.5 Creación de Bibliotecas

Para crear bibliotecas en TypeScript:
- Configura `tsconfig.json` con `"declaration": true` para generar archivos de definición.
- Organiza el código en módulos y publica el paquete en NPM.

### 11.6 Decoradores (experimental)

Los decoradores permiten modificar el comportamiento de clases y sus miembros. Habilítalos en `tsconfig.json` con:

```json
{
  "experimentalDecorators": true
}
```

_**Ejemplo:**_

```ts
function Sellar(constructor: Function) {
    Object.seal(constructor);
    Object.seal(constructor.prototype);
}

@Sellar
class Producto {
    constructor(public nombre: string) {}
}
```

### 11.7 Directivas Avanzadas (@for, track, etc.)

Aunque no son parte nativa del lenguaje, algunos frameworks utilizan directivas personalizadas para tareas específicas. Se recomienda revisar la documentación del framework (como Angular o NestJS) para conocer detalles y sintaxis.

---

## 12. Conclusión y Recomendaciones

TypeScript amplía JavaScript dotándolo de un sistema de tipos robusto, lo que mejora la mantenibilidad, escalabilidad y detección temprana de errores. La adopción de TypeScript es fundamental en proyectos modernos (Angular, NestJS, etc.), ya que ofrece herramientas avanzadas para trabajar con interfaces, clases, genéricos y manejo asíncrono, junto con opciones para extender el lenguaje a través de decoradores y tipos condicionales.

**Lecturas y Referencias Adicionales:**
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- *TypeScript Deep Dive* de Basarat Ali Syed  
- Publicaciones académicas sobre sistemas de tipos y tipado estático (consultar DOIs en bases de datos IEEE o ACM)

---