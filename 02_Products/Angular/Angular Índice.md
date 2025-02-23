**Tags:** #_Todo
#ToTag #ToLink 
- - -
==transcribir==
https://www.udemy.com/course/the-complete-guide-to-angular-2/learn/lecture/43788666#search
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

## Html en Angular
Some differences between templates and standard HTML syntax include:

Comments in the template source code are not included in the rendered output
Component and directive elements can be self-closed (e.g., <UserProfile />)
Attributes with certain characters (i.e., [], (), etc.) have special meaning to Angular. See binding docs and adding event listeners docs for more information.
The @ character has a special meaning to Angular for adding dynamic behavior, such as control flow, to templates. You can include a literal @ character by escaping it as an HTML entity code (&commat; or &#64;).
Angular ignores and collapses unnecessary whitespace characters. See whitespace in templates for more details.
Angular may add comment nodes to a page as placeholders for dynamic content, but developers can ignore these.
In addition, while most HTML syntax is valid template syntax, Angular does not support \<script> element in templates. For more information, see the Security page.
## Css en anular
https://angular.dev/guide/components/styling
## Componentes
==mucha paja==
https://angular.dev/guide/components
ejemplo:
``` typescript
@Component({
  selector: 'app-root',          // 🔹 Defines the custom HTML tag <app-root>
  standalone: true,              // 🔹 Declares this component as standalone (no NgModule needed)
  imports: [],                   // 🔹 List of imported standalone components, directives, or pipes
  templateUrl: './app.component.html',  // 🔹 Specifies the external HTML template
  styleUrl: './app.component.css',      // 🔹 Specifies the external CSS file
})
```
Every component has a few main parts:

A @Componentdecorator that contains some configuration used by Angular.
An HTML template that controls what renders into the DOM.
A CSS selector that defines how the component is used in HTML.
A TypeScript class with behaviors, such as handling user input or making requests to a server.
``` ts
@Component({
  selector: 'profile-photo',
  template: `<img src="profile-photo.jpg" alt="Your profile photo">`,
})
export class ProfilePhoto { }
```
The object passed to the @Component decorator is called the component's metadata. This includes the selector, template, and other properties described throughout this guide.

Components can optionally include a list of CSS styles that apply to that component's DOM:


``` ts
@Component({
  selector: 'profile-photo',
  template: `<img src="profile-photo.jpg" alt="Your profile photo">`,
  styles: `img { border-radius: 50%; }`,
})
export class ProfilePhoto { }
```


y default, a component's styles only affect elements defined in that component's template. 

You can alternatively choose to write your template and styles in separate files:

@Component({
  selector: 'profile-photo',
  templateUrl: 'profile-photo.html',
  styleUrl: 'profile-photo.css',
})
export class ProfilePhoto { }
check
This can help separate the concerns of presentation from behavior in your project. You can choose one approach for your entire project, or you decide which to use for each component.

Both templateUrl and styleUrl are relative to the directory in which the component resides.
#### standalone vs module(NgModule)
## Servicios
## Inyeccion de dependencias
Se usa para no instanciar un servicio, pues este tiene que sincronizarse en todas las clases en las que se importa, el decorador @injectable es la clave para no instanciar.
funcion inject y sistema de tokens
"DI" is a design pattern and mechanism for creating and delivering some parts of an app to other parts of an app that require them.

Tip: Check out Angular's Essentials before diving into this comprehensive guide.

When you develop a smaller part of your system, like a module or a class, you may need to use features from other classes. For example, you may need an HTTP service to make backend calls. Dependency Injection, or DI, is a design pattern and mechanism for creating and delivering some parts of an application to other parts of an application that require them. Angular supports this design pattern and you can use it in your applications to increase flexibility and modularity.

In Angular, dependencies are typically services, but they also can be values, such as strings or functions. An injector for an application (created automatically during bootstrap) instantiates dependencies when needed, using a configured provider of the service or value.
==explicar como se añaden eventos== se le pone on a las funciones
## Enrutamiento
Archivos de configuración de rutas:

app.routes.ts (para definir las rutas)
app.config.ts (en tu proyecto puede estar configurado para inicializar el módulo raíz)
Si aún no tienes un módulo de rutas separado, puedes generarlo con el CLI:

bash
Copy
ng generate module app-routing --flat --module=app
Esto creará un archivo (por ejemplo, app-routing.module.ts) en la carpeta src/app y lo importará en el módulo raíz (usualmente app.module.ts). En tu caso, parece que usas app.routes.ts y app.config.ts para la configuración.

## Control Flow
https://angular.dev/guide/templates/control-flow
## fomrs
(ngSubmit)
(nGModel)https://angular.dev/api/forms/NgModel
## Señales
- las señales son formas de emitir eventos 
- asReadOnly() es un metodo para no alterar señales
## Data Binding
### Event Binding
==copiar snitpets de user-input==
https://v17.angular.io/guide/event-binding
en el padre: Captura una propiedad(un valor guardado en una variable) a traves de $(event) 
en el hijo: para invocar un metodo del padre en el html del hijo, se pueden usar triggers del navegador, Ej; 
(click) (dblclick) (keyup) (keydown) (keypress) (mousedown) (mouseup) (mouseenter) (mouseleave) (mouseover) (mouseout) (submit) (change) (input) (focus) (blur) (ngModel) (ngSubmit)
### Property Binding
\<app-hijo>\[Propiedad_Heredada]="Propiedad_del_Padre" /> en el  html del padre
https://medium.com/@abdoessamadhmayda/angular-input-complete-guide-756b4bf7e924
https://medium.com/@abdoessamadhmayda/angular-input-complete-guide-756b4bf7e924
### String Interpolation
https://v17.angular.io/guide/interpolation
### Attribute Binding
==mucha paja==
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

## State Management
### State/events(zone A) y señales
las señales son contenedores trazables que notifican al framwork ante cualquier cambio de sus datos
- los objetos señal se dereferencian con los parentesis de funcion, y esto inicia una suscripcion en segundo plano asegurandose de que el componente que ha modificado el valor de la señal sea rerenderizado
## Content proyection
when you use an angular component somewhere in yout aplication like here as a wrapper around some other markdup it will be default not keep that markup around which you wrapped but replace with his own markup, para combinan el valor original con el proctado usar \<ng-content />
## Cli Comands:
- Projecto de prueba:
		npm start  to dev server
		localhost : 4200
- ng generate component "nombre del componente" (abreviacion: ng g c)
## pipes
Son operadores inpirados en unix especiales para formatear al vuelo el html y el formateo de tipos
``` ts
          <td>{{ result.interest | currency }}</td>

```
## debug
angular tiene un mapeo de memoria para poder hacer el debug con tu codigo y no el compilado, angular devtools son la hostia,
- - - 
==decoradores typescript==
==string interpolation== para cargar variables en el html
## Datos
- Para los archivos se omite la extension ts
- Angular no escanea tu repositorio, tenemos que eañadirlo al index.html y al main.ts k
==tienes que poner en el angular.json las imagenes que cargas==
- Zone.js es parte del framework y notifica de cualquien evento en cualquier componente
- variable de entorno $event para ahacer accesible en los html templates, la info de @Output para ahacer eaccesible en los html templates, 
- ?. es una dereferencia segura para los objetos, te permite asignarlos en tiempo de ejecucion
- llamar a las clases acabando en su tipo,, para evitar colisioes, ej
  class taskComponent , class taskService
  - poner private o public en el constructor es lo mismo que asignar una variable privada
  - browser module es un modulo especial que solo se puede importar en desde root-app
- To reference images stored in the public/ folder you would use a path like this: \<img src="some-image.png"> i.e., the public folder name is NOT part of that path (it's NOT \<img src="public/some-image.png">)
- - -
Part 4: Angular

Angular CLI & Setup

Templates
Directives
Routing
HTTP Client
Observables & RxJS
Guards
Interceptors
Unit Testing
Angular Material
Performance Optimization
Deployment
- - - 
## ***Sources:***
- [Angular Play Groud](https://angular.dev/playground)
- [Catalogo Angular](https://uiverse.io/)
-  [Catalogo Material](https://material.angular.io/components/categories)