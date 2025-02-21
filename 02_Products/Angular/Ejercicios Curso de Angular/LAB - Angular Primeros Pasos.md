A continuación se muestra la versión mejorada del ejercicio, con rutas de archivos más claras y una estructura jerárquica para facilitar su seguimiento:

---

# Ejercicio 1: Configuración y Modificación de un Componente Angular

## Paso 1. Crear un nuevo proyecto Angular

Abre la terminal y ejecuta:

```bash
ng new <nombre_proyecto>
npm start
```

---

## Paso 2. Generar un nuevo componente

En la terminal, ejecuta:

```bash
ng generate component primer-componente
```

*Nota: Se recomienda usar nombres sin símbolos especiales y en minúsculas.*

---

## Paso 3. Modificar archivos del componente

### 3.1. Archivo TypeScript del componente

**Ruta:**  
`./src/app/primer-componente/primer-componente.component.ts`

**Contenido sugerido:**

```typescript
// user-profile.ts
@Component({
  selector: 'user-profile',
  template: `
    <h1>User profile</h1>
    <p>This is the user profile page</p>
  `,
  // Agrega estilos directamente en el componente (opcional)
  styles: [`
    h1 { font-size: 3em; }
  `]
})
export class UserProfile { 
  // Aquí va la lógica del componente
}
```

> Abre el navegador y verifica que la aplicación se ejecute correctamente en [http://localhost:4200](http://localhost:4200).

---

### 3.2. Separar HTML y CSS en archivos externos

Si prefieres definir la plantilla y los estilos en archivos separados, realiza lo siguiente:

1. **Modificar el componente TypeScript**  
   **Ruta:**  
   `./src/app/primer-componente/primer-componente.component.ts`

   **Actualiza el decorador @Component:**

   ```typescript
   // user-profile.ts
   @Component({
     selector: 'user-profile',
     templateUrl: './user-profile.html',
     styleUrls: ['./user-profile.css'],
   })
   export class UserProfile {
     // Comportamiento del componente
   }
   ```

2. **Crear el archivo de plantilla HTML**  
   **Ruta:**  
   `./src/app/primer-componente/user-profile.html`

   **Contenido:**

   ```html
   <!-- user-profile.html -->
   <h1>User profile</h1>
   <p>This is the user profile page</p>
   ```

3. **Crear el archivo de estilos CSS**  
   **Ruta:**  
   `./src/app/primer-componente/user-profile.css`

   **Contenido:**

   ```css
   /* user-profile.css */
   h1 {
     font-size: 3em;
   }
   ```

> Vuelve a abrir el navegador y verifica la correcta visualización en [http://localhost:4200](http://localhost:4200).

A continuación se muestra el ejercicio 2 con una presentación estructurada para importar y usar un componente que carga una foto:

---

# Ejercicio 2: Importar y Utilizar un Componente para Cargar una Foto

## Paso 1. Generar el componente ProfilePhoto

En la terminal, ejecuta:

```bash
ng generate component profile-photo
```

---

## Paso 2. Configurar el componente ProfilePhoto

### 2.1. Archivo TypeScript de ProfilePhoto

**Ruta:**  
`./src/app/profile-photo/profile-photo.component.ts`

**Contenido sugerido:**

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'profile-photo',
  template: `
    <img src="ruta-de-la-foto.jpg" alt="Profile Photo" style="max-width: 100%;">
  `,
})
export class ProfilePhoto { }
```

> *Reemplaza* `"ruta-de-la-foto.jpg"` por la URL o ruta local de la imagen que deseas mostrar.

---

## Paso 3. Modificar el componente UserProfile para importar y usar ProfilePhoto

### 3.1. Archivo TypeScript de UserProfile

**Ruta:**  
`./src/app/user-profile/user-profile.component.ts`

**Contenido sugerido:**

```typescript
import { Component } from '@angular/core';
import { ProfilePhoto } from '../profile-photo/profile-photo.component';

@Component({
  selector: 'user-profile',
  // Agrega ProfilePhoto en el array de imports
  imports: [ProfilePhoto],
  template: `
    <h1>User profile</h1>
    <profile-photo></profile-photo>
    <p>This is the user profile page</p>
  `,
})
export class UserProfile {
  // Define la lógica del componente aquí
}
```

> **Nota:**  
> Si estás utilizando componentes standalone (Angular 14+), asegúrate de incluir `standalone: true` en el decorador @Component según corresponda.

---

## Paso 4. Verificación

Abre el navegador y verifica que la aplicación se ejecute correctamente en [http://localhost:4200](http://localhost:4200). Deberías ver el título "User profile", la imagen definida en ProfilePhoto y el párrafo descriptivo.



### 3.2. Archivo HTML del componente

Ubicación: `./src/app/primer-compoente/primer-componente.component.html`

Reemplaza el contenido por:

```html
<p>user-profile works!</p>
```

---

## 4. Importar y utilizar el componente en la aplicación

### 4.1. Importar en el archivo de componente principal

Ubicación: `./src/app/app-component.compoent.ts`

Añade la siguiente línea:

```typescript
import { UserProfile } from './user-profile/user-profile.component';
```

### 4.2. Modificar la plantilla del componente principal

Ubicación: `./src/app/app-component.compoent.html`

Reemplaza el contenido por:

```html
<user-profile></user-profile>
```

---

## 5. Verificación final

Abre el navegador y comprueba que la aplicación se ejecuta correctamente en [http://localhost:4200](http://localhost:4200).

# Paso 2