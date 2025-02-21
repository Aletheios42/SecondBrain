**Tags:** #_Todo
#Linux #CLI #Chuletas #ToLink 
- - -
==Prefix + ?: lista los comandos==
tmux maneja las sesiones atraves de un servidor en el background y se conecta a las terminales del sistema a traves de ssh, por lo que lo hace persistente. ya que si el ssh se cae, el server de tmux sigue persistente.
- **Sesión**: Es un entorno de trabajo independiente que puede contener múltiples ventanas. Las sesiones se mantienen en el background incluso si se desconecta SSH, lo que permite recuperarlas más tarde.
- **Ventana**: Es una instancia dentro de una sesión que puede contener múltiples paneles. Cada ventana puede ejecutar diferentes tareas.
- **Panel**: Es una división dentro de una ventana que permite ejecutar comandos de forma independiente. Puedes dividir una ventana en múltiples paneles para trabajar en varias tareas simultáneamente.
## Tmux CLI
prefix + : , introduce la linea de comandos que tiene autocompletado y GUI, es la forma mas eficiente de trabajar con tmux
usa :source-file ~/.config/.tmux.config para cargar cambios en la configuracion
### **Gestión de sesiones** (desde fuera de tmux ya que hablas con el servidor)
- `tmux new-session` o `tmux new`: Crea una nueva sesión.
- `tmux new -s <nombre_sesión>`: Crea una nueva sesión con un nombre específico.
- `tmux list-sessions` o `tmux ls`: Lista todas las sesiones activas.
- `tmux attach-session` o `tmux attach`: Se reconecta a la última sesión activa.
- `tmux attach -t <nombre_sesión>`: Se conecta a una sesión específica.
- `tmux kill-session -t <nombre_sesión>`: Cierra una sesión específica.
- `tmux kill-server`: Cierra todas las sesiones y detiene el servidor de tmux.
- `tmux rename-session -t <nombre_actual> <nuevo_nombre>`: Renombra una sesión existente.
### **Gestión de ventanas**(dentro de tmux pues hablas con el cliente)
- `tmux new-window`: Crea una nueva ventana en la sesión actual.
- `tmux new-window -n <nombre_ventana>`: Crea una nueva ventana con un nombre específico.
- `tmux list-windows`: Lista todas las ventanas en la sesión actual.
- `tmux kill-window -t <número_ventana>`: Cierra una ventana específica.
- `tmux rename-window <nuevo_nombre>`: Renombra la ventana actual.
### **Gestión de paneles**
- `tmux split-window`: Divide el panel actual horizontalmente.
- `tmux split-window -v`: Divide el panel actual verticalmente.
- `tmux select-pane -U`: Cambia al panel de arriba.
- `tmux select-pane -D`: Cambia al panel de abajo.
- `tmux select-pane -L`: Cambia al panel de la izquierda.
- `tmux select-pane -R`: Cambia al panel de la derecha.
- `tmux swap-pane -U`: Intercambia el panel actual con el de arriba.
- `tmux swap-pane -D`: Intercambia el panel actual con el de abajo.
- `tmux kill-pane`: Cierra el panel actual.
### **Otros comandos útiles**
- `tmux detach-client`: Desconecta el cliente actual de la sesión (deja la sesión en segundo plano).
- `tmux source-file ~/.tmux.conf`: Recarga la configuración de tmux desde el archivo `.tmux.conf`.
- `tmux display-message <mensaje>`: Muestra un mensaje en la barra de estado.
- `tmux clock-mode`: Muestra un reloj en el panel actual.
- `tmux list-keys`: Muestra todos los atajos de teclado configurados.
- `tmux list-commands`: Muestra una lista de todos los comandos de tmux.
## Atajos de teclado

| Gestión de sesiones y ventanas          | Gestión de paneles                         |
| --------------------------------------- | ------------------------------------------ |
| **Gestión de sesiones**                 | **Gestión de paneles**                     |
| `prefix: d`  Desconectar sesión         | `prefix: %`  Dividir verticalmente         |
| `prefix: s`  Listar sesiones            | `prefix: "`  Dividir horizontalmente       |
| `prefix: (`  Cambiar a sesión anterior  | `prefix: o`  Cambiar al siguiente panel    |
| `prefix: )`  Cambiar a siguiente sesión | `prefix: ;`  Cambiar al panel anterior     |
| `prefix: L`  Última sesión activa       | `prefix: x`  Cerrar panel actual           |
| **Gestión de ventanas**                 | `prefix: espacio`  Cambiar diseño          |
| `prefix: c`  Crear nueva ventana        | `prefix: z`  Maximizar/restaurar panel     |
| `prefix: w`  Listar ventanas            | `prefix: q`  Mostrar números de paneles    |
| `prefix: n`  Siguiente ventana          | `prefix: m`  Marcar(destacar) panel actual |
| `prefix: p`  Ventana anterior           | `prefix: M`  Desmarcar panel actual        |
| `prefix: ,`  Renombrar ventana          | `prefix: l`  Cambiar al último panel       |
| `prefix: &`  Cerrar ventana actual      | `prefix: Up`  Mover panel arriba           |
|                                         | `prefix: Down`  Mover panel abajo          |
|                                         | `prefix: Left`  Mover panel izquierda      |
|                                         | `prefix: Right`  Mover panel derecha       |

| Copiar y pegar                    | Otros comandos útiles                |
| --------------------------------- | ------------------------------------ |
| `prefix: [`  Entrar en modo copia | `prefix: ?`  Mostrar lista de atajos |
| `prefix: ]`  Pegar texto copiado  | `prefix: :`  Prompt de comandos      |
|                                   | `prefix: r`  Recargar configuración  |
|                                   | `prefix: t`  Mostrar hora actual     |
|                                   | `prefix: i`  Info de la ventana      |

- - - 
## ***Sources:***
- [Learn tmux (Part 1) Boost your Linux Productivity with this 5-part Course!](https://www.youtube.com/watch?v=UxbiDtEXuxg&list=PLT98CRl2KxKGiyV1u6wHDV8VwcQdzfuKe)