## Índice general
1. [Introducción a Angular](#introducción-a-angular)  
2. [Instalación y configuración inicial](#instalación-y-configuración-inicial)  
3. [Estructura de un proyecto Angular](#estructura-de-un-proyecto-angular)  
   - [Crear un Proyecto](#crear-un-proyecto)  
   - [Directorios y archivos principales](#📁-directorios-y-archivos-principales)  
   - [Configuración central](#⚙️-configuración-central)  
   - [Gestión de paquetes](#📦-gestión-de-paquetes)  
   - [Otros](#📂-otros)  
4. [Componentes](#componentes)  
5. [Templates, Directivas y Pipes](#templates-directivas-y-pipes)  
6. [Enrutamiento (Routing)](#enrutamiento-routing)  
7. [Servicios e Inyección de dependencias (DI)](#servicios-e-inyección-de-dependencias-di)  
8. [Comunicación con el servidor (HTTP)](#comunicación-con-el-servidor-http)  
9. [Formularios en Angular](#formularios-en-angular)  
10. [Programación reactiva con RxJS](#programación-reactiva-con-rxjs)  
11. [Pruebas (Testing)](#pruebas-testing)  
==Meter==
- in-templates
- ? y !
- no dar valores iniciales
- @for/@if/@else son de angular 17>, los legacy son ngFor,  ngIf, ngtemplate
- Click listener
- $event para tener acceso a los eventos
- directives: son componentes sin template
- property binding\[] mas event binding --->2 way binding(para coger un input de elementos input)
- formModule, hace que loos \<forms> no envien ningun dato al back, lo tienes que hacer explicitamente, ya que formModule cambia el comportamiento por defecto del navegador
==Ejercicios==
- displayear conditional content, modo normal y modo legacy 
## Introducción a Angular

**Angular** es un **framework front-end** de código abierto desarrollado por Google, basado en **TypeScript**, que permite construir aplicaciones **SPA** (Single Page Applications) y **MPA** (Multiple Page Applications). Su sistema de enrutamiento proporciona un **modelo basado en componentes**, inyección de dependencias, enlace de datos bidireccional (*two-way binding*), herramientas para manejo de estado y un ecosistema robusto para pruebas y optimización.

La idea principal es construir bloques de la aplicación de forma modular. Cada **componente** puede estar dividido en múltiples archivos (clase, template, estilos, etc.) y se integra con otros componentes para conformar un árbol de componentes más amplio.

### Diferencia clave entre librería y framework
- **Framework (Ej. Angular):** Proporciona una estructura completa para el desarrollo, incluyendo enrutamiento, gestión de estado, compilación y más.  
- **Biblioteca (Ej. React):** Se enfoca en la parte de la interfaz de usuario (UI) y deja la elección de herramientas complementarias al desarrollador.
### ¿Qué se puede construir en Angular?

- **Componentes:** Son clases escritas en TypeScript que se asocian a un decorador `@Component`. Definen la lógica y vista que se muestra en pantalla.  
- **Standalone Components:** A partir de Angular 14, se pueden crear componentes autónomos (*standalone*), prescindiendo de la necesidad de declararlos en un módulo.

---
## Instalación y configuración inicial
1. **Node.js y npm**  
   - Descarga [Node.js](https://nodejs.org/es). Incluye el gestor de paquetes npm.  
   - **Node.js** permite ejecutar JavaScript en el servidor y proporciona un entorno para la instalación de dependencias.

2. **TypeScript**  
   - Angular funciona sobre TypeScript (superset de JavaScript) con tipado estático y funcionalidades avanzadas de ESNext.

3. **Angular CLI**  
   - Instalar la CLI de Angular globalmente con:
     ```bash
     npm install -g @angular/cli
     ```
   - Si hay problemas de permisos en Linux/Mac:
     ```bash
     mkdir -p ~/.npm-global
     npm config set prefix '~/.npm-global'
     export PATH="$HOME/.npm-global/bin:$PATH"
     echo 'export PATH="$HOME/.npm-global/bin:$PATH"' >> ~/.bashrc  
     source ~/.bashrc
     ```

4. **Visual Studio Code** (recomendado)  
   - Plugins útiles: *Angular Essentials*, *Angular Language Service*.

---
## Estructura de un proyecto Angular
### Crear un Proyecto
Para crear un nuevo proyecto Angular:

```bash
ng new <nombre_proyecto>
```

La CLI pedirá confirmaciones y configuraciones, por ejemplo:
- ¿Deseas habilitar autocompletado de rutas? (Y/N)  
- ¿Deseas configurar *Server-Side Rendering* (SSR)? (Y/N)  
- Selección de estilo (CSS, SCSS, etc.)

Tras estos pasos, se generará la carpeta `<nombre_proyecto>` con la estructura inicial.

### 📁 Directorios y archivos principales

Dentro de `src/` se encuentra el código fuente:

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

- **app/**  
  Contiene los componentes principales de la aplicación. Por defecto, el componente raíz es `AppComponent`.

- **assets/**  
  Almacena imágenes u otros recursos estáticos.

- **favicon.ico**  
  Ícono usado en el navegador. Dependiendo de la versión de Angular, también puede ubicarse en otras carpetas (p. ej. `public/`).

- **index.html**  
  Archivo HTML raíz de la aplicación. En su `<body>` se inserta dinámicamente el `<app-root>` o el componente raíz que defina la aplicación.

- **main.ts**  
  Punto de entrada de Angular. Usualmente se llama a:
  ```typescript
  import { bootstrapApplication } from '@angular/platform-browser';
  import { AppComponent } from './app/app.component';

  bootstrapApplication(AppComponent)
    .catch(err => console.error(err));
  ```
  Esto corresponde a la *API standalone* (Angular 14+), que reemplaza la necesidad de declarar un módulo raíz (`AppModule`).

- **styles.css**  
  Archivo de estilos global de la aplicación.

### ⚙️ Configuración central

- **angular.json**  
  Configuración de Angular CLI (comandos de build, serve, test, etc.).

- **tsconfig.json**  
  Configuración global de TypeScript.

- **tsconfig.app.json**  
  Configuración de TypeScript específica para la aplicación (excluye pruebas).

- **tsconfig.spec.json**  
  Configuración de TypeScript para las pruebas unitarias.

### 📦 Gestión de paquetes

- **package.json**  
  Define dependencias, scripts y metadatos del proyecto (contiene las dependencias de Angular).

- **package-lock.json**  
  Bloquea las versiones exactas de las dependencias.

- **node_modules/**  
  Directorio donde se instalan los paquetes externos.

### 📂 Otros

- **public/**  
  Carpeta opcional para archivos estáticos (imagenes, favicons, etc.).

---

## Componentes
## 4. Componentes

Los **componentes** son la unidad fundamental en Angular. Cada componente encapsula la lógica (clase TypeScript), la plantilla (HTML) y los estilos (CSS/SCSS) correspondientes. Mediante el uso del decorador `@Component`, Angular reconoce e integra estos elementos en la aplicación.

---

### 4.1 Estructura básica

Generalmente, cada componente se define en un archivo TypeScript separado. Por convención, se usan sufijos como `.component.ts`, `.component.html` y `.component.css` para identificar código específico de cada parte.

**Ejemplo de un componente básico**  
```typescript
// app.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',             // Nombre usado en la plantilla HTML para insertar este componente
  templateUrl: './app.component.html',  // Vista asociada (HTML)
  styleUrls: ['./app.component.css']    // Estilos asociados (CSS/SCSS)
})
export class AppComponent {
  title = 'Mi Aplicación Angular';  // Variable expuesta al template

  // Lógica adicional del componente
}
```

#### Decorador `@Component`
- **selector**: Etiqueta personalizada para renderizar el componente en otras plantillas HTML.
- **template / templateUrl**: El HTML que define la estructura visual. Puede incluirse inline (`template: \`<h1>...</h1>\``) o en un archivo separado (`templateUrl`).
- **styles / styleUrls**: Hojas de estilo propias. Puede ser inline (`styles`) o externo (`styleUrls`).

---

### 4.2 Ciclo de vida de un componente

Angular proporciona una serie de **hooks** que permiten ejecutar acciones en momentos específicos del ciclo de vida de un componente. Se definen implementando las interfaces correspondientes:

1. **ngOnChanges(changes: SimpleChanges)**  
   Se llama cuando cambian los valores de las propiedades de entrada (`@Input`).

2. **ngOnInit()**  
   Se llama una sola vez tras la inicialización de las propiedades de entrada. Ideal para inicializar datos.

3. **ngDoCheck()**  
   Se invoca en cada ciclo de detección de cambios. Se usa para verificar cambios que Angular no detecta automáticamente.

4. **ngAfterContentInit()**  
   Se ejecuta tras insertar el contenido en las directivas `<ng-content>`.

5. **ngAfterContentChecked()**  
   Se ejecuta luego de que Angular verifica los enlaces del contenido proyectado.

6. **ngAfterViewInit()**  
   Se llama tras la inicialización de la vista del componente (sus hijos ya existen en el DOM).

7. **ngAfterViewChecked()**  
   Después de cada verificación de cambios en la vista.

8. **ngOnDestroy()**  
   Se llama antes de que el componente sea destruido. Útil para liberar recursos o cancelar suscripciones.

**Ejemplo**  
```typescript
import { Component, OnInit, OnDestroy } from '@angular/core';

@Component({
  selector: 'app-example',
  template: `<h2>{{ message }}</h2>`
})
export class ExampleComponent implements OnInit, OnDestroy {
  message: string = '';

  ngOnInit(): void {
    this.message = 'Componente inicializado';
    console.log('ngOnInit');
  }

  ngOnDestroy(): void {
    console.log('ngOnDestroy');
  }
}
```

---

### 4.3 Comunicación entre componentes

En aplicaciones modulares, los componentes a menudo necesitan **intercambiar datos**. Hay varias maneras de lograrlo:

#### 4.3.1 A través de propiedades de entrada y salida (`@Input` y `@Output`)

- **@Input**: Recibe datos desde el componente padre.  
- **@Output**: Emite eventos para notificar cambios al componente padre.

**Ejemplo**  
```typescript
// hijo.component.ts
import { Component, Input, Output, EventEmitter } from '@angular/core';

@Component({
  selector: 'app-hijo',
  template: `
    <p>Mensaje del padre: {{ message }}</p>
    <button (click)="enviarNotificacion()">Notificar al padre</button>
  `
})
export class HijoComponent {
  @Input() message: string = '';
  @Output() notificado = new EventEmitter<string>();

  enviarNotificacion() {
    this.notificado.emit('¡Evento desde el componente hijo!');
  }
}
```

```html
<!-- padre.component.html -->
<app-hijo
  [message]="mensajeAlHijo"
  (notificado)="onHijoNotifica($event)">
</app-hijo>
```
```typescript
// padre.component.ts
export class PadreComponent {
  mensajeAlHijo = 'Hola desde el padre';

  onHijoNotifica(event: string) {
    console.log('El hijo dice:', event);
  }
}
```

#### 4.3.2 Usando servicios compartidos e Inyección de Dependencias

Para lógica más compleja, se usan servicios que almacenan datos o métodos accesibles por varios componentes. Más detalles en la sección **Servicios e Inyección de Dependencias**.

#### 4.3.3 Router y parámetros en la URL

La navegación entre rutas puede incluir parámetros dinámicos que se comparten entre componentes. (Ver sección **Enrutamiento**).

---

### 4.4 Componentes *standalone*

Desde Angular 14, se introdujo la API *Standalone*, que permite crear componentes sin necesidad de declararlos en un Módulo (NgModule). Estos se definen con la propiedad `standalone: true` y las dependencias se importan directamente en la sección `imports` del decorador `@Component`.

```typescript
import { Component } from '@angular/core';
import { CommonModule } from '@angular/common';

@Component({
  standalone: true,
  selector: 'app-standalone',
  template: `<p>Hola, soy un componente standalone!</p>`,
  imports: [CommonModule]
})
export class StandaloneComponent {}
```

Para *bootstrap* (arrancar) la aplicación con un componente standalone, se usa `bootstrapApplication` en el `main.ts`:

```typescript
import { bootstrapApplication } from '@angular/platform-browser';
import { StandaloneComponent } from './standalone.component';

bootstrapApplication(StandaloneComponent)
  .catch(err => console.error(err));
```

---

### 4.5 Buenas prácticas

1. **Nombrado consistente**  
   Utilizar sufijos como `.component.ts`, `.component.html`, `.component.css` para identificar cada tipo de archivo.

2. **Single Responsibility**  
   Un componente debe encargarse de una sola responsabilidad visual/funcional. Si crece demasiado, conviene dividirlo en subcomponentes.

3. **Comunicación clara**  
   Hacer uso de `@Input`/`@Output` cuando la comunicación es simple y puntual. Para estados globales o complejos, preferir servicios o *state management* (NgRx, etc.).

4. **Mínimo acoplamiento**  
   Reducir la lógica en el componente cuando se trate de funcionalidades compartidas, extrayendo la lógica a servicios inyectables.

5. **Angular Style Guide**  
   Seguir las pautas oficiales de la [Angular Style Guide](https://angular.io/guide/styleguide) para mantener coherencia en el código y facilitar la colaboración.

---

### 4.6 Referencias y lecturas recomendadas

- **Documentación oficial de Angular**  
  [https://angular.io/docs](https://angular.io/docs)  
  > Instrucciones detalladas sobre creación de componentes y usos avanzados.

- **API Reference**  
  [https://angular.io/api](https://angular.io/api)  
  > Referencia a todos los decoradores, clases, métodos y propiedades disponibles en Angular.

- **Angular Style Guide**  
  [https://angular.io/guide/styleguide](https://angular.io/guide/styleguide)  
  > Lista de convenciones de nomenclatura, estructura de archivos y buenas prácticas.

- **Equipo de desarrollo original**: Miško Hevery, Igor Minar (Google).  
  > Creadores y principales promotores de Angular.

---

> **Siguiente paso**: Si deseas profundizar en **Templates, Directivas y Pipes**, o en otras secciones como *Enrutamiento*, *Servicios* o *Testing*, indícalo para elaborar esas partes.
## Templates, Directivas y Pipes
## 5. Templates, Directivas y Pipes

En esta sección se explica cómo trabajar con la capa de presentación en Angular, incluyendo el **data binding** (enlace de datos), las **directivas** que manipulan el DOM y los **pipes** para la transformación de datos en la vista.

---

### 5.1 Data Binding (Enlace de datos)

Angular ofrece varias formas de vincular datos entre el **componente** (lógica TypeScript) y la **plantilla** (HTML). Se engloban en dos enfoques principales:

1. **One-Way Data Binding** (enlace unidireccional)  
2. **Two-Way Data Binding** (enlace bidireccional)  

#### 5.1.1 One-Way Data Binding

**One-Way** significa que el flujo de datos viaja **desde el componente** (TypeScript) **hasta la vista** (HTML), o viceversa (desde la vista hasta el componente), pero no en ambas direcciones simultáneamente.

1. **Interpolación**  
   - Sintaxis: `{{ variable }}`  
   - Permite mostrar valores de variables o propiedades del componente directamente en el HTML.  
   ```html
   <h1>Hola, {{ nombre }}</h1>
   ```
   ```typescript
   export class AppComponent {
     nombre = 'Angular';
   }
   ```
   - Se puede incluir expresiones simples:
     ```html
     <p>Suma: {{ 2 + 3 }}</p> <!-- Muestra 5 -->
     ```
   - No se recomienda colocar lógica compleja para evitar sobrecargar la vista.

2. **Property Binding**  
   - Sintaxis: `[propiedad]="expresión"`  
   - Vincula la **propiedad** de un elemento HTML o de un componente hijo con un valor de la clase TypeScript.  
   ```html
   <img [src]="imagenUrl" />
   <button [disabled]="deshabilitado">Enviar</button>
   ```
   ```typescript
   export class EjemploComponent {
     imagenUrl = 'assets/angular-logo.png';
     deshabilitado = false;
   }
   ```
   - El *binding* es unidireccional: un cambio en `imagenUrl` se refleja en el `src` del `img`, pero no a la inversa.

3. **Event Binding**  
   - Sintaxis: `(evento)="expresión"`  
   - Asocia un **evento del DOM** (click, input, submit, etc.) a un método en el componente.  
   ```html
   <button (click)="contarClick()">Click me</button>
   ```
   ```typescript
   export class EjemploComponent {
     contador = 0;
     
     contarClick() {
       this.contador++;
       console.log('Clicks:', this.contador);
     }
   }
   ```
   - El flujo de datos va desde la **vista** al **componente**.

#### 5.1.2 Two-Way Data Binding ([( )])

El **Two-Way Binding** permite **sincronizar** la vista y el componente simultáneamente. Un cambio en la propiedad del componente se ve reflejado en la vista, y un cambio en la vista se ve reflejado en el componente.

- Sintaxis: `[(ngModel)]="propiedadDelComponente"`  
- Requiere importar **FormsModule** (o ReactiveFormsModule) en la configuración del módulo (o dentro de `imports` en un *Standalone Component*).

**Ejemplo con `ngModel`:**  
```html
<!-- Asegurarse de tener FormsModule disponible -->
<input [(ngModel)]="nombre" placeholder="Ingrese su nombre" />
<p>Hola, {{ nombre }}</p>
```
```typescript
export class EjemploTwoWayComponent {
  nombre: string = '';
}
```
De esta manera, al escribir en el `<input>`, la propiedad `nombre` se actualiza de forma automática y viceversa.

---

### 5.2 Directivas

Las **directivas** permiten añadir comportamiento a elementos del DOM sin necesidad de crear componentes completos.

#### 5.2.1 Tipos de Directivas

4. **Directivas Estructurales**  
   - Modifican la *estructura* del DOM (añaden, quitan o reemplazan elementos).  
   - Se indican con el prefijo `*`, como `*ngIf` y `*ngFor`.

   **Ejemplo `*ngIf`:**  
   ```html
   <p *ngIf="mostrar">Este párrafo se mostrará si mostrar === true</p>
   ```
   ```typescript
   export class EjemploNgIfComponent {
     mostrar: boolean = true;
   }
   ```

   **Ejemplo `*ngFor`:**  
   ```html
   <ul>
     <li *ngFor="let item of lista">{{ item }}</li>
   </ul>
   ```
   ```typescript
   export class EjemploNgForComponent {
     lista = ['Elemento 1', 'Elemento 2', 'Elemento 3'];
   }
   ```

5. **Directivas de Atributo**  
   - Modifican la **apariencia** o el **comportamiento** de un elemento sin alterar su estructura.  
   - Ejemplos: `[ngClass]`, `[ngStyle]`.

   **Ejemplo `ngClass`:**  
   ```html
   <div [ngClass]="{'resaltado': isActive, 'error': hasError}">
     Contenido con clases dinámicas
   </div>
   ```
   ```typescript
   export class EjemploNgClassComponent {
     isActive = true;
     hasError = false;
   }
   ```

6. **Directivas Personalizadas**  
   - Se crean para encapsular comportamientos específicos. Se definen con el decorador `@Directive()`.  
   - Ideal para añadir funcionalidad reutilizable (ej. resaltar texto, controlar enfoque, etc.).

---

### 5.3 Pipes

Los **pipes** (tuberías) transforman datos de forma declarativa dentro de la plantilla. Se usan con la sintaxis `{{ valor | pipeName }}`.

#### 5.3.1 Pipes Integrados

Angular provee varios pipes por defecto:  
- `DatePipe` (`date`): Formatear fechas.  
- `UpperCasePipe` (`uppercase`), `LowerCasePipe` (`lowercase`): Convertir textos.  
- `CurrencyPipe` (`currency`), `PercentPipe` (`percent`): Dar formato a números con monedas o porcentajes.  
- `DecimalPipe` (`number`): Formatear números con decimales.

**Ejemplo**  
```html
<p>Fecha actual: {{ hoy | date:'fullDate' }}</p>
<p>Precio: {{ precio | currency:'USD':'symbol':'1.2-2' }}</p>
```
```typescript
export class EjemploPipesComponent {
  hoy = new Date();
  precio = 1234.5;
}
```

#### 5.3.2 Pipes con Argumentos

Se pueden pasar argumentos directamente al pipe, p. ej. en `date:'shortTime'`.

```html
<p>{{ hoy | date:'shortTime' }}</p>
```

#### 5.3.3 Pipes Personalizados

Para transformar datos de forma específica, se pueden crear *pipes* propios con `@Pipe()`.

**Ejemplo**  
```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'reversa'
})
export class ReversaPipe implements PipeTransform {
  transform(value: string): string {
    return value.split('').reverse().join('');
  }
}
```
Uso en la plantilla:
```html
<p>{{ 'Hola Angular' | reversa }}</p>
<!-- Resultado: ralugnA aloH -->
```

#### 5.3.4 Pipes Puros vs. Impuros

- **Pure Pipes**: Se ejecutan solo cuando cambian los valores de entrada. Son más eficientes.  
- **Impure Pipes**: Se ejecutan en cada ciclo de detección de cambios. Útiles si el dato cambia sin que cambie la referencia (por ejemplo, modificaciones a un array interno).

```typescript
@Pipe({
  name: 'ejemploImpuros',
  pure: false  // <-- Marcar como impuro
})
```

---

### 5.4 Resumen de la sección

- **Data Binding:**  
  - **One-Way:** Interpolación (`{{}}`), Property Binding (`[propiedad]`), Event Binding (`(evento)`).
  - **Two-Way:** `[(ngModel)]` (requiere FormsModule).
- **Directivas:**  
  - Estructurales (`*ngIf`, `*ngFor`) para manipular el DOM.
  - Atributo (`[ngClass]`, `[ngStyle]`) para cambiar apariencia o comportamiento.
  - Personalizadas (`@Directive`) para funcionalidad específica.
- **Pipes:**  
  - Integrados (date, uppercase, currency, etc.).
  - Personalizados para transformaciones específicas.
  - Pure vs. Impure.

Estas herramientas combinadas permiten desarrollar vistas dinámicas y escalables en Angular de manera organizada y eficiente.

---

### 5.5 Referencias y lecturas complementarias

- **Data Binding**: [https://angular.io/guide/binding-overview](https://angular.io/guide/binding-overview)  
- **Directives**: [https://angular.io/guide/directives](https://angular.io/guide/directives)  
- **Pipes**: [https://angular.io/guide/pipes](https://angular.io/guide/pipes)  
- **Ejemplos oficiales**: [StackBlitz Angular Examples](https://stackblitz.com/angular)  
- **Autores y equipo**: Angular Team (Google), con notables contribuciones de Miško Hevery, Igor Minar, etc.

---

> **Siguiente paso**: Si deseas extender los apuntes a otras secciones (ej. Enrutamiento, Servicios, HTTP, Formularios, RxJS, Pruebas), indícalo para desarrollarlas.

## Enrutamiento (Routing)

## 6. Enrutamiento (Routing)

El **sistema de enrutamiento** en Angular permite mapear rutas de la aplicación a **componentes** específicos, facilitando la construcción de **Single Page Applications (SPA)**. Con el módulo de enrutamiento, es posible:

- Definir URLs personalizadas.  
- Cargar componentes al navegar entre distintas rutas.  
- Controlar el acceso mediante guardas (*route guards*).  
- Dividir el proyecto en **módulos cargados de forma diferida** (*lazy loading*).

---

### 6.1 Configuración básica

Para habilitar el **enrutamiento**, se emplea el `RouterModule` y se definen las rutas en un arreglo de configuración:

**Ejemplo de configuración en `app-routing.module.ts`:**
```typescript
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';

const routes: Routes = [
  { path: '', component: HomeComponent },          // Ruta raíz -> HomeComponent
  { path: 'about', component: AboutComponent },    // /about -> AboutComponent
  { path: '**', redirectTo: '' }                   // Cualquier ruta no definida -> Redirige a raíz
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule {}
```

- `path`: Indica la parte de la URL que activará la ruta.
- `component`: El componente a cargar cuando se visite esa ruta.
- `**`: Ruta comodín para redirección de páginas no encontradas (404).

En el módulo principal (p.ej. `AppModule`) se importa `AppRoutingModule` para que Angular reconozca las rutas.

**En un componente principal** (generalmente `AppComponent.html`), se utiliza la directiva `<router-outlet></router-outlet>`, que actúa como contenedor donde se renderizan los componentes asociados a las rutas:
```html
<!-- app.component.html -->
<nav>
  <a routerLink="">Inicio</a> |
  <a routerLink="about">Acerca</a>
</nav>

<!-- El contenido de la ruta seleccionada se mostrará aquí -->
<router-outlet></router-outlet>
```

---

### 6.2 Parámetros de ruta

Para rutas dinámicas (ej. detalles de un elemento con ID), se agregan *placeholders* con `:id`. Luego, los componentes pueden leer el valor del parámetro por medio de `ActivatedRoute`.

**Definición de ruta con parámetro**  
```typescript
const routes: Routes = [
  { path: 'user/:id', component: UserComponent },
  // ...
];
```

**Lectura del parámetro en el componente**  
```typescript
import { ActivatedRoute } from '@angular/router';

export class UserComponent implements OnInit {
  userId!: string;

  constructor(private route: ActivatedRoute) {}

  ngOnInit(): void {
    this.userId = this.route.snapshot.paramMap.get('id') || '';
  }
}
```
- `snapshot.paramMap.get('id')` obtiene el valor del parámetro `:id`.

Para reactualizar el valor ante cambios en la misma ruta (sin recargar el componente), se puede usar `route.paramMap.subscribe(...)` en lugar de `snapshot`.

---

### 6.3 Rutas hijas (Child Routes)

Las **rutas hijas** se utilizan para anidar componentes dentro de otros. Se definen en el arreglo `children`.

```typescript
const routes: Routes = [
  {
    path: 'admin',
    component: AdminLayoutComponent,
    children: [
      { path: '', component: DashboardComponent },
      { path: 'users', component: UsersListComponent }
    ]
  }
];
```
En la vista de `AdminLayoutComponent`, un `<router-outlet>` adicional rendereará los hijos (`DashboardComponent`, `UsersListComponent`).

---

### 6.4 Lazy Loading (Carga diferida)

El **lazy loading** mejora el rendimiento inicial de la aplicación, cargando módulos (y sus dependencias) únicamente cuando se accede a sus rutas.

1. **Crear un módulo** (p.ej. `admin.module.ts`) y su archivo de rutas (`admin-routing.module.ts`).
2. Definir las rutas con `loadChildren`.

```typescript
// app-routing.module.ts
const routes: Routes = [
  {
    path: 'admin',
    loadChildren: () =>
      import('./admin/admin.module').then(m => m.AdminModule)
  }
];
```
Con ello, cuando el usuario navegue a `/admin`, Angular descargará dinámicamente el módulo `AdminModule`.

---

### 6.5 Guards (Protección de rutas)

Los **guards** permiten controlar el acceso a determinadas rutas. Existen varios tipos:
- `CanActivate`: Se ejecuta antes de activar una ruta.  
- `CanDeactivate`: Se ejecuta antes de salir de una ruta.  
- `Resolve`: Puede precargar datos antes de renderizar un componente.  
- `CanLoad`: Evita cargar módulos *lazy* si la condición no se cumple.

**Ejemplo básico con `CanActivate`:**
```typescript
import { Injectable } from '@angular/core';
import { CanActivate, Router } from '@angular/router';

@Injectable({ providedIn: 'root' })
export class AuthGuard implements CanActivate {
  constructor(private router: Router) {}

  canActivate(): boolean {
    const userIsLoggedIn = /* lógica de autenticación */;
    if (!userIsLoggedIn) {
      this.router.navigate(['/login']);
      return false;
    }
    return true;
  }
}
```

Luego, se aplica en las rutas:
```typescript
const routes: Routes = [
  { 
    path: 'dashboard',
    component: DashboardComponent,
    canActivate: [AuthGuard] 
  }
];
```

---

### 6.6 Módulo independiente (Standalone) y Routing

A partir de Angular 14+, se puede configurar el enrutamiento sin usar `NgModule`. En lugar de `forRoot()`, se define un objeto de configuración y se pasa a `provideRouter`.

```typescript
// main.ts
import { bootstrapApplication } from '@angular/platform-browser';
import { provideRouter, Routes } from '@angular/router';
import { AppComponent } from './app/app.component';
import { HomeComponent } from './app/home/home.component';

const routes: Routes = [
  { path: '', component: HomeComponent },
  // ...
];

bootstrapApplication(AppComponent, {
  providers: [
    provideRouter(routes)
  ]
});
```

Esta aproximación es coherente con la idea de *Standalone Components*.

---

### 6.7 Buenas prácticas de enrutamiento

1. **Estructura clara de rutas**  
   Evitar anidar demasiadas rutas hijas. Mantener un diseño comprensible de la arquitectura de la aplicación.

2. **Uso prudente de guards**  
   Simplificar la lógica en guards (autenticación, roles, etc.) y delegar la complejidad a servicios especializados.

3. **Lazy loading estratégico**  
   Cargar de forma diferida solo módulos grandes o secciones menos frecuentes para optimizar tiempos de carga.

4. **Parámetros y resolvers**  
   Utilizar *Resolvers* cuando se requiera cargar datos antes de mostrar una vista, evitando pantallas en blanco mientras se esperan respuestas HTTP.

- **Ejemplos prácticos**:  
  - [StackBlitz - Angular Routing Examples](https://stackblitz.com/angular/djbmnyyevav?file=src%2Fapp%2Fapp-routing.module.ts)

---

> **Siguiente paso**: Si quieres profundizar en **Servicios e Inyección de Dependencias**, *HTTP*, *Formularios*, *RxJS* o *Pruebas*, indícalo para desarrollar esas secciones.

## Servicios e Inyección de dependencias (DI)

*(Sección pendiente de ampliación.)*

## Comunicación con el servidor (HTTP)

*(Sección pendiente de ampliación.)*

## Formularios en Angular

*(Sección pendiente de ampliación.)*

## Programación reactiva con RxJS

*(Sección pendiente de ampliación.)*

## Pruebas (Testing)

*(Sección pendiente de ampliación.)*

---

> **Nota:** Para continuar desarrollando cada sección en detalle, simplemente indica qué sección quieres ampliar.
