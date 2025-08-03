# Configuración y Modificación de un Componente Angular para una Galería de Arte

#### 1. Crear el proyecto Angular  
Se recomienda abrir la terminal y ejecutar:
```bash
ng new web-galeria
cd web-galeria
npm start
```
Una vez iniciada la aplicación, se podrá comprobar su correcto funcionamiento visitando [http://localhost:4200](http://localhost:4200).
#### 2. Generar el componente principal "galeria-arte"  
Se sugiere generar el componente sin pruebas unitarias para simplificar el laboratorio:
```bash
ng generate component galeria-arte --skip-tests
```
Esto crea los archivos correspondientes en `./src/app/galeria-arte/`.
#### 3. Configurar el componente con plantilla y estilos en línea  
En el archivo `galeria-arte.component.ts` se establecerá el componente con template y estilos embebidos.
El contenido se define de la siguiente manera:
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'galeria-arte',
  template: `
    <h1>Galería de Arte</h1>
    <p>Explora nuestras obras de arte.</p>
  `,
  styles: [`
    h1 { font-family: 'Georgia', serif; color: #333; }
    p { font-size: 1.2em; }
  `]
})
export class GaleriaArteComponent { }
```
Dado que `GaleriaArteComponent` se exporta, se debe importar en `app.component.ts` y utilizar su selector `<galeria-arte></galeria-arte>` en el archivo `app.component.html`.  

Se invita a comprobar que la aplicación se visualiza correctamente en [http://localhost:4200](http://localhost:4200).
#### 4. Separar la plantilla y los estilos en archivos externos  
Una vez verificado el funcionamiento del componente inline, se procederá a trasladar la plantilla y los estilos a archivos externos para mejorar la organización.

- **Modificar el decorador `@Component` en `galeria-arte.component.ts`:**
  ```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'galeria-arte',
  imports: [],
  templateUrl: './galeria-arte.component.html',
  styleUrl: './galeria-arte.component.css',
})
export class GaleriaArteComponent {}

  ```

==poner un html mejor==
- **Crear o actualizar el archivo `galeria-arte.component.html`:**
  ```html
  <h1>Galería de Arte</h1>
  <p>Explora nuestras obras de arte.</p>
  ```

- **Crear o actualizar el archivo `galeria-arte.component.css`:**
  ```css
  h1 {
    font-family: 'Georgia', serif;
    color: #333;
  }
  p {
    font-size: 1.2em;
  }
  ```

Después de realizar estos cambios, se recomienda recargar la aplicación en [http://localhost:4200](http://localhost:4200) para confirmar que la separación de la plantilla y los estilos se refleja correctamente en la interfaz.

---
# Segundo Componente
### 1. Preparar el Recurso (Imagen)

- Crear (o asegurarse de que existe) la carpeta `src/assets` en el proyecto.
- Colocar una imagen (por ejemplo, `obra1.jpg`) dentro de la carpeta `src/assets`.  
  *Ejemplo:*  
  ```
  web-arte/
  ├── src/
      ├── assets/
          └── obra1.jpg
  ```

---

### 2. Actualizar el Componente **obra-arte**

#### 2.1. Modificar `obra-arte.component.ts`  
Se importa Input y se añaden dos propiedades de entrada (`imagen` y `descripcion`) para recibir datos desde el componente padre.  
```typescript
import { Component, Input } from '@angular/core';

@Component({
  selector: 'obra-arte',
  templateUrl: './obra-arte.component.html',
  styleUrls: ['./obra-arte.component.css']
})
export class ObraArteComponent {
  @Input() imagen: string = '';
  @Input() descripcion: string = '';
}
```

#### 2.2. Modificar `obra-arte.component.html`  
Se actualiza la plantilla para mostrar la imagen y la descripción.
```html
<div class="obra">
  <img [src]="imagen" alt="Obra de Arte" style="max-width: 100%;">
  <p>{{ descripcion }}</p>
</div>
```

*Opcional:* Se pueden añadir estilos específicos en `obra-arte.component.css` para resaltar la presentación.
### 3. Actualizar el Componente **galeria-arte**
#### 3.1. Modificar `galeria-arte.component.ts`  
Se crea una lista de obras, cada una con la ruta de la imagen y la descripción correspondiente.  
```typescript
import { Component } from '@angular/core';
import { ObraArteComponent } from '../obra-arte/obra-arte.component';

@Component({
  selector: 'galeria-arte',
  imports: [ObraArteComponent],
  templateUrl: './galeria-arte.component.html',
  styleUrls: ['./galeria-arte.component.css']
})
export class GaleriaArteComponent {
  // Se define un arreglo de obras de arte
  obras: { imagen: string, descripcion: string }[] = [
    {
      imagen: 'assets/obra1.jpg', // La ruta relativa a la carpeta assets
      descripcion: 'Descripción de la obra 1'
    },
    {
      imagen: 'assets/obra1.jpg',
      descripcion: 'Otra descripción para la obra 2'
    }
    // Se pueden añadir más objetos para representar otras obras
  ];
}
```
#### 3.2. Modificar `galeria-arte.component.html`  
Se utiliza un bucle `*ngFor` para iterar sobre la lista de obras y renderizar cada componente `obra-arte` pasando los datos correspondientes mediante property binding.
```html
<h1>Galería de Arte</h1>
<p>Explora nuestras obras de arte.</p>

<div class="galeria">
  <obra-arte 
      @for (obra of obras; track obra.description) {
	
    [imagen]="obra.imagen"
    [descripcion]="obra.descripcion">
	}
  </obra-arte>
</div>
```

---

### 4. Verificar la Integración

- Asegurarse de que en `app.component.html` se utilice el selector `<galeria-arte></galeria-arte>` para renderizar la galería principal.
- Ejecutar la aplicación con `npm start` (o `ng serve`) y visitar [http://localhost:4200](http://localhost:4200) para comprobar que:
  - La galería se muestra correctamente.
  - Cada obra de arte se renderiza con la imagen (cargada desde `src/assets/obra1.jpg`) y la descripción correspondiente.

---

# Ejercicio 3: Ejercicios de Binding en Angular

#### 3.1 Property Binding

1. **Definir una propiedad en el componente principal**  
   - En el archivo `galeria-arte.component.ts`, declara una propiedad (por ejemplo, `tamañoCuadro: number = 300;` o `colorFondo: string = '#f0f0f0';`).

2. **Aplicar property binding en la plantilla**  
   - En `galeria-arte.component.html`, utiliza property binding para asignar el valor de la propiedad a un atributo HTML o estilo:
     - Ejemplo para atributos: `<div [attr.data-size]="tamañoCuadro">...</div>`
     - Ejemplo para estilos: `<div [style.backgroundColor]="colorFondo">...</div>`
   - Asegúrate de que los cambios de la propiedad en el componente se reflejen dinámicamente en la vista.

#### 3.2 Event Binding

1. **Definir un método para manejar eventos**  
   - En `galeria-arte.component.ts`, crea un método (por ejemplo, `actualizarCuadro()`) que modifique alguna propiedad del componente (por ejemplo, cambiar `tamañoCuadro` o `colorFondo`).

2. **Vincular un evento en la plantilla**  
   - En `galeria-arte.component.html`, añade un elemento interactivo (por ejemplo, un botón) y usa event binding para conectar el evento al método definido:
     ```html
     <button (click)="actualizarCuadro()">Actualizar Obra</button>
     ```
   - Verifica que al hacer clic se ejecute el método y se actualice la vista de acuerdo con la nueva propiedad.

3. **Prueba y verificación**  
   - Ejecuta la aplicación en [http://localhost:4200](http://localhost:4200) y prueba las interacciones de binding para confirmar que:
     - Los valores de las propiedades se muestran correctamente en la vista.
     - Los eventos disparan los métodos esperados, actualizando dinámicamente la interfaz.
