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

==explicar como se añaden eventos== se le pone on a las funciones
## Property Binding
## Attribute Binding
In the previous lecture, you were introduced to "Property Binding" - a key Angular feature that allows you to bind element properties to dynamic values.

For example, <img \[src]="someSrc"> binds the src property of the underlying HTMLImageElement DOM object to the value stored in someSrc.

Whilst it might look like you're binding the src attribute of the <img> tag, you're actually NOT doing that. Instead, property binding really targets the underlying DOM object property (in this case a property that's also called src) and binds that.

This might look like a subtle detail (and often it indeed doesn't matter) but it's important to understand this difference between element attributes and property. This article can help with understanding this difference.

Whilst it won't make a difference in Angular apps in many cases, it DOES matter if you're trying to set attributes on elements dynamically. Attributes which don't have an equally-named underlying property.

For example, when binding ARIA attributes, you can't target an underlying DOM object property.

Since "Property Binding" wants to target properties (and not attributes), that can be a problem. That's why Angular offers a slight variation of the "Property Binding" syntax that does allow you to bind attributes to dynamic values.

It looks like this:

```
<div 
  role="progressbar" 
  [attr.aria-valuenow]="currentVal" 
  [attr.aria-valuemax]="maxVal">...</div>
  ```
By adding attr in front of the attribute name you want to bind dynamically, you're "telling" Angular that it shouldn't try to find a property with the specified name but instead bind the respective attribute - in the example above, the aria-valuenow and aria-valuemax attributes would be bound dynamically.

## State/events(zone A) y señales
las señales son contenedores trazables que notifican al framwork ante cualquier cambio de sus datos
- los objetos señal se dereferencian con los parentesis de funcion, y esto inicia una suscripcion en segundo plano asegurandose de que el componente que ha modificado el valor de la señal sea rerenderizado
## Cli Comands:
- Projecto de prueba:
		npm start  to dev server
		localhost : 4200
- ng generate component "nombre del componente" (abreviacion: ng g c)

- - - 
==decoradores typescript==
## Datos
- Para los archivos se omite la extension ts
- Angular no escanea tu repositorio, tenemos que eañadirlo al index.html y al main.ts k
- tienes que poner en el angular.json las imagenes que cargas
- Zone.js es parte del framework y notifica de cualquien evento en cualquier componente
- variable de entorno $event para ahacer accesible en los html templates, la info de @Output para ahacer eaccesible en los html templates, la info de O#@Output
- - -

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