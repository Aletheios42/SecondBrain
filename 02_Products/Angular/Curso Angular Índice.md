**Tags:** #_Todo
#ToTag #ToLink 
- - -
# [[Setup Angular]]
# Qué es Angular
**Angular** es un **framework front-end** de código abierto desarrollado por Google, basado en **TypeScript**, que permite construir  SPA y MPA), su sistema de enrutamiento proporciona un **modelo basado en componentes**, inyección de dependencias, enlace de datos bidireccional (*two-way binding*), herramientas para manejo de estado y un ecosistema robusto para pruebas y optimización. 

La idea es constuir nuestros bloques indivualmente, cada componente puede estar codificado en multiples archivos y ensamblarlos juntos  al resto de componentes. para despues deplegar un arbol de componentes.. para despues deplegar un arbol de componentes.
#### Diferencia clave entre libreria y framework:
Framework (Ej. Angular) → Proporciona una estructura completa para el desarrollo, incluyendo enrutamiento, gestión de estado, compilación, etc.
Biblioteca (Ej. React) → Se enfoca solo en la parte de la interfaz de usuario (UI) y deja la elección de otras herramientas al desarrollador.
==decoradores typescript==
#### Que se puede consturir en angular

- compoenntes son clases que estanenheched by that component decorator
- stdalone son componentes autonomos

# Crear un Proyecto
```
ng new $project_name
```
y te pregunta
autocompletado -> Y
activar SSR -> N
CSS styles -> CSS
# Estructura de un Proyecto Angular
## 📁 Directorios y Archivos Principales
#### src
El código fuente del proyecto se encuentra en `src/`:

```
src/
├── app
│   ├── app.component.css
│   ├── app.component.html
│   └── app.component.ts
├── assets
│   └── angular-logo.png
├── favicon.ico
├── index.html
├── main.ts
└── styles.css
```
- **app/** – Contiene los [[Componentes ]] principales de la aplicación.
- **assets/** – Almacena imágenes y otros archivos estáticos.
- **favicon.ico** – Ícono del navegador.
	Dependiendo de la version el favicon esta en ./public o en ./src/assests
- **index.html** – Archivo raíz de la aplicación.
	- Angular se encarga de incrustar tu codigo de ./src/main.ts en el body de index \<app-root> a traves de "type=module" (permite export)
- **main.ts** – Punto de entrada de Angular.
	```typescript
	import { bootstrapApplication } from '@angular/platform-browser';
	import { AppComponent } from './app/app.component';
	
	bootstrapApplication(AppComponent).catch((err) => console.error(err));
	```
	1. **Importación de `bootstrapApplication`**  
	   - Esta función se encarga de inicializar la aplicación Angular sin necesidad de definir un **módulo raíz** (`AppModule`), como en versiones anteriores de Angular.  
	   - Es parte de la **API independiente** (*Standalone API*), introducida en Angular 14.
	2. **Importación del componente raíz (`AppComponent`)**  
	3. **Inicialización de la aplicación**  
- **styles.css** – Hoja de estilos global.

 #### [[Archivos de Configuracion de Proyectos Angular]]

- - - 

## Datos
- Para los archivos se omite la extension ts
- Angular no escanea tu repositorio, tenemos que eañadirlo al index.html y al main.ts k
- tienes que poner en el angular.json las imagenes que cargas
- - -
Cli Comands:
- Projecto de prueba:
		npm start  to dev server
		localhost : 4200


Part 4: Angular

Angular CLI & Setup
Components
Modules
Templates
Data Binding
Directives
Services
Dependency Injection
Routing
Forms (Template & Reactive)
HTTP Client
Observables & RxJS
Pipes
Guards
Interceptors
State Management
Unit Testing
Angular Material
Performance Optimization
Deployment
- - - 
## ***Sources:***
- https://angular.dev/playground