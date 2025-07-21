**Ejercicio 1: Nuevo proyecto y estructura básica**  
1. Instala Angular CLI (si no lo has hecho):  
   ```bash
   npm install -g @angular/cli
   ```  
2. Crea un nuevo proyecto:  
   ```bash
   ng new hola-angular
   cd hola-angular
   ng serve
   ```  
3. Verifica que la aplicación se ejecute correctamente en `http://localhost:4200/`.  

**Objetivos**:  
- Familiarizarse con la CLI de Angular.  
- Entender la estructura inicial del proyecto (carpetas `app`, `assets`, `environments`, etc.).  

**Ejercicio 2: Componente “Hola Mundo”**  
1. Crea un nuevo componente:  
   ```bash
   ng generate component hola
   ```  

2. En el archivo `hola.component.ts`, define una propiedad para mostrar en la plantilla, por ejemplo:  
   ```typescript
   export class HolaComponent {
     mensaje: string = 'Hola Mundo desde Angular';
   }
   ```  

3. En la plantilla `hola.component.html`, muestra la propiedad usando *interpolación*:  
   ```html
   <h1>{{ mensaje }}</h1>
   ```  

4. Incluye el selector `<app-hola>` en el `app.component.html` para visualizarlo.  

**Objetivos**:  
- Practicar creación de componentes con Angular CLI.  
- Entender la interpolación y cómo se muestran datos en la plantilla.  

**Ejercicio 3: Data Binding y eventos**  
1. En tu componente principal (`AppComponent` o uno nuevo) crea una propiedad `contador = 0;`.  
2. En la plantilla, muestra el valor de `contador`:  
   ```html
   <p>Valor actual: {{ contador }}</p>
   <button (click)="incrementar()">Incrementar</button>
   ```  
3. Implementa la lógica en el archivo TypeScript:  
   ```typescript
   incrementar() {
     this.contador++;
   }
   ```  

**Objetivos**:  
- Entender el *data binding* unidireccional (interpolación).  
- Manejar eventos de usuario con `(click)` y actualizar el estado en el componente.  

---

**Ejercicio 4: Two-Way Data Binding con `ngModel`**  
11. Agrega `FormsModule` en el `app.module.ts`:  
   ```typescript
   import { FormsModule } from '@angular/forms';
   
   @NgModule({
     declarations: [...],
     imports: [
       BrowserModule,
       FormsModule
       // ...
     ],
     bootstrap: [AppComponent]
   })
   export class AppModule {}
   ```  
12. Define en un componente la propiedad `nombre: string = ''`.  
13. En la plantilla, añade un campo de texto que use `[(ngModel)]`:  
   ```html
   <input [(ngModel)]="nombre" placeholder="Ingresa tu nombre">
   <p>Hola, {{ nombre }}!</p>
   ```  

**Objetivos**:  
- Practicar el *two-way data binding* utilizando `[(ngModel)]`.  
- Conocer el uso de `FormsModule`.  

---

**Ejercicio 5: Listado y directiva `*For`**  
1. Crea un arreglo en el componente, por ejemplo:  
   ```typescript
   nombres: string[] = ['Ana', 'Luis', 'María', 'Carlos'];
   ```  
2. En la plantilla, utiliza `*For` para mostrar la lista:  
   ```html
   <ul>
     <li *For="let nombre of nombres">{{ nombre }}</li>
   </ul>
   ```  
16. Opcional: agrega un botón o campo de texto para añadir nuevos nombres al arreglo.  

**Objetivos**:  
- Familiarizarse con la directiva estructural `*For`.  
- Administrar y renderizar colecciones en la plantilla.  

### Referencias y lecturas recomendadas
- [Documentación oficial de Angular (angular.io)](https://angular.io/docs)  
