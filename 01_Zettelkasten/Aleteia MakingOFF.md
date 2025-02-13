**Tags:** #_Todo
#ToTag #ToLink 
- - - 

Verifica las instalaciones con estos comandos:
```bash
node --version
npm --version
ng version
```

Si no tienes Angular CLI instalado, instálalo con:
```bash
npm install -g @angular/cli
```

### Creacion del proyecto

```bash
ng new markdown-notes
```

Durante la creación del proyecto, el CLI te hará algunas preguntas. Responde así:
1. Would you like to add Angular routing? → Yes
2. Which stylesheet format would you like to use? → CSS
3. SSR  -> No


##### creacmos la estructura de carpetas
De acuerdo, vamos a crear una estructura de carpetas organizada para el proyecto. Ejecuta los siguientes comandos para crear la estructura base:

```bash
# Dentro de src/app
mkdir -p src/app/core
mkdir -p src/app/shared
mkdir -p src/app/features/markdown-editor
mkdir -p src/app/features/markdown-viewer
mkdir -p src/app/features/notes-list
```

Esta estructura incluye:
- `core/`: Para servicios singleton, interceptores, guards, etc.
- `shared/`: Para componentes, pipes y directivas reutilizables
- `features/`: Módulos funcionales de la aplicación
  - `markdown-editor/`: Editor de markdown
  - `markdown-viewer/`: Visualizador de markdown
  - `notes-list/`: Lista de apuntes

##### Instalamos libreria para procesar markdown
npm install marked

vamos a crear el primer componente para la lista de apuntes. 
En Angular, los componentes son las piezas básicas de la interfaz de usuario.

Ejecuta este comando para crear el componente de lista:
```bash
ng generate component features/notes-list/notes-list
```

Esto creará varios archivos en la carpeta `src/app/features/notes-list/notes-list`:
- `notes-list.component.ts`: La lógica
- `notes-list.component.html`: El template HTML
- `notes-list.component.css`: Los estilos
- `notes-list.component.spec.ts`: Para testing

Ahora necesitamos agregar este componente a las rutas. Abre el archivo `src/app/app-routing.module.ts` y reemplaza su contenido con:

```typescript
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { NotesListComponent } from './features/notes-list/notes-list/notes-list.component';

const routes: Routes = [
  { path: '', redirectTo: 'notes', pathMatch: 'full' },
  { path: 'notes', component: NotesListComponent }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

- - - 
## ***Sources:***