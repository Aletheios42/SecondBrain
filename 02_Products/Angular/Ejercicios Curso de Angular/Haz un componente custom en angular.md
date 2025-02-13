**Tags:** #_Todo
#ToTag #ToLink 
- - -
tienes que crear 3 archivos por componente .ts, .html .css

en el main pones un selector tal que asi pero con el nombre que quieras.
en links el componente y el stiilo y , 
``` typescript
@Component({
  selector: 'app-root',          // 🔹 Defines the custom HTML tag <app-root>
  standalone: true,              // 🔹 Declares this component as standalone (no NgModule needed)
  imports: [],                   // 🔹 List of imported standalone components, directives, or pipes
  templateUrl: './app.component.html',  // 🔹 Specifies the external HTML template
  styleUrl: './app.component.css',      // 🔹 Specifies the external CSS file
})
```

tras esto solo tendrias que exportar la clase para que sea accsible en el main.ts, bootstrapear eso y ya puedes llamarlo en el index.html


hacer otra version, una en la que no modificas noda en el index y tiene forma de arbol sine approot el que llama a todo y se lo comunica al index.html
# Datos
-selector: ==Cuidado con hash colition en el selector==
- template : ==revisar la opcion inline template==
-standalone = version 19 ya viene activado por defecto, hay que mirar compatibilidades, si quiero usar un modele-based component tendras que setearlo a false
templateUri con rutas relativas al archivo que contiende el markup del elemento invocado
se puede usar con el css igual in line o con ur a un archivo

- - - 
## ***Sources:***