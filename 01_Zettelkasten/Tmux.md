**Tags:** #_Todo
#Linux #CLI #Chuletas #ToLink 
- - -
==Prefix + ?: lista los comandos==
tmux maneja las sesiones atraves de un servidor en el background y se conecta a las terminales del sistema a traves de ssh, por lo que lo hace persistente. ya que si el ssh se cae, el server de tmux sigue persistente.

- **Sesión**: Es un entorno de trabajo independiente que puede contener múltiples ventanas. Las sesiones se mantienen en el background incluso si se desconecta SSH, lo que permite recuperarlas más tarde.
  
- **Ventana**: Es una instancia dentro de una sesión que puede contener múltiples paneles. Cada ventana puede ejecutar diferentes tareas.

- **Panel**: Es una división dentro de una ventana que permite ejecutar comandos de forma independiente. Puedes dividir una ventana en múltiples paneles para trabajar en varias tareas simultáneamente.

Aquí tienes una lista más completa de los comandos de **CLI de tmux** que te pueden ser útiles:

---
### **Gestión de sesiones**
- `tmux new-session` o `tmux new`: Crea una nueva sesión.
- `tmux new -s <nombre_sesión>`: Crea una nueva sesión con un nombre específico.
- `tmux list-sessions` o `tmux ls`: Lista todas las sesiones activas.
- `tmux attach-session` o `tmux attach`: Se reconecta a la última sesión activa.
- `tmux attach -t <nombre_sesión>`: Se conecta a una sesión específica.
- `tmux kill-session -t <nombre_sesión>`: Cierra una sesión específica.
- `tmux kill-server`: Cierra todas las sesiones y detiene el servidor de tmux.
- `tmux rename-session -t <nombre_actual> <nuevo_nombre>`: Renombra una sesión existente.

---
### **Gestión de ventanas**
- `tmux new-window`: Crea una nueva ventana en la sesión actual.
- `tmux new-window -n <nombre_ventana>`: Crea una nueva ventana con un nombre específico.
- `tmux list-windows`: Lista todas las ventanas en la sesión actual.
- `tmux kill-window -t <número_ventana>`: Cierra una ventana específica.
- `tmux rename-window <nuevo_nombre>`: Renombra la ventana actual.

---

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

---

### **Otros comandos útiles**
- `tmux detach-client`: Desconecta el cliente actual de la sesión (deja la sesión en segundo plano).
- `tmux source-file ~/.tmux.conf`: Recarga la configuración de tmux desde el archivo `.tmux.conf`.
- `tmux display-message <mensaje>`: Muestra un mensaje en la barra de estado.
- `tmux clock-mode`: Muestra un reloj en el panel actual.
- `tmux list-keys`: Muestra todos los atajos de teclado configurados.
- `tmux list-commands`: Muestra una lista de todos los comandos de tmux.

| Gestión de sesiones y ventanas             | Gestión de paneles                            |
| ------------------------------------------ | --------------------------------------------- |
| **Gestión de sesiones**                    | **Gestión de paneles**                        |
| `Ctrl + b + d`  Desconectar sesión         | `Ctrl + b + %`  Dividir verticalmente         |
| `Ctrl + b + s`  Listar sesiones            | `Ctrl + b + "`  Dividir horizontalmente       |
| `Ctrl + b + (`  Cambiar a sesión anterior  | `Ctrl + b + o`  Cambiar al siguiente panel    |
| `Ctrl + b + )`  Cambiar a siguiente sesión | `Ctrl + b + ;`  Cambiar al panel anterior     |
| `Ctrl + b + L`  Última sesión activa       | `Ctrl + b + x`  Cerrar panel actual           |
| **Gestión de ventanas**                    | `Ctrl + b + espacio`  Cambiar diseño          |
| `Ctrl + b + c`  Crear nueva ventana        | `Ctrl + b + z`  Maximizar/restaurar panel     |
| `Ctrl + b + w`  Listar ventanas            | `Ctrl + b + q`  Mostrar números de paneles    |
| `Ctrl + b + n`  Siguiente ventana          | `Ctrl + b + m`  Marcar(destacar) panel actual |
| `Ctrl + b + p`  Ventana anterior           | `Ctrl + b + M`  Desmarcar panel actual        |
| `Ctrl + b + ,`  Renombrar ventana          | `Ctrl + b + l`  Cambiar al último panel       |
| `Ctrl + b + &`  Cerrar ventana actual      | `Ctrl + b + Up`  Mover panel arriba           |
|                                            | `Ctrl + b + Down`  Mover panel abajo          |
|                                            | `Ctrl + b + Left`  Mover panel izquierda      |
|                                            | `Ctrl + b + Right`  Mover panel derecha       |

| Copiar y pegar                       | Otros comandos útiles                   |
| ------------------------------------ | --------------------------------------- |
| `Ctrl + b + [`  Entrar en modo copia | `Ctrl + b + ?`  Mostrar lista de atajos |
| `Ctrl + b + ]`  Pegar texto copiado  | `Ctrl + b + :`  Prompt de comandos      |
|                                      | `Ctrl + b + r`  Recargar configuración  |
|                                      | `Ctrl + b + t`  Mostrar hora actual     |
|                                      | `Ctrl + b + i`  Info de la ventana      |
## ***Sources:***
- [Learn tmux (Part 1) Boost your Linux Productivity with this 5-part Course!](https://www.youtube.com/watch?v=UxbiDtEXuxg&list=PLT98CRl2KxKGiyV1u6wHDV8VwcQdzfuKe)