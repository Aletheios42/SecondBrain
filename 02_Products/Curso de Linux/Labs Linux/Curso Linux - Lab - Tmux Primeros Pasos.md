**Tags:** #_Todo
#Linux #ToLink 
- - -
### Primeros Pasos
1. Crear una sesión llamada "dev":
   ```bash
   tmux new -s dev
   ```
2. Listar sesiones activas:
   ```bash
   tmux ls
   ```
3. Conectarse a una sesión llamada "dev":
   ```bash
   tmux attach -t dev
   ```
4. Renombrar una sesión:
   ```bash
   tmux rename-session -t dev desarrollo
   ```
5. Cerrar una sesión llamada "dev":
   ```bash
   tmux kill-session -t dev
   ```

---
==Hacer mas patrones de trabajo==
	- 3 terminales divider el primer contenerdor en veritcal y luego el del la izquieda en vertical
	- 5 terminales: divides en vertical, despues el del la derecha se vuelve a dividir en vertical y despeus el contenedor de mas a la derecha(el mas nuevo) se divide en horizontal, cambias el focus al de la izquierda del todo y lo devides en horizontal tambien. (mue probablemente tienes que hacer resize en las divisiones verticales para ajustar bien al trabajo concreto)
###  Patron de trabajo 1
``` bash
# Inicia tmux
tmux
# Desconecta la sesion
ctrl + b + d
# Lista las sesiones latentes de tmux
tmux list-sessions
# Recupera la ultima sesion abierta
tmux attach
# Divide el contenedor por la vertical
crtl + b + %
# Situa el focus en el panel de la izquierda
crtl + b + Arrow-Left
# Divide el contenedor por la horizontal
crtl + b + ""
# Situa el focus en el panel de la arriba
crtl + b + Arrow-Up
# abre top
crtl + b + % top
# Desplaza el focus al panel de abajo
crtl + b + Arrow-Down
# abre el journal
crtl + b + journalctl -j
```
### Navegcion
Muevete por todos los paneles,  ventanas y sesiones
### Nombres por doquier
ponerle nombre a todo lo vivo
- - - 
## ***Sources:***