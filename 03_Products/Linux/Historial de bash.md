**MetaTags:** #_Done
**Tags:** #Bash #ToLink
- - -
###### TIP:
- Si quieres que una busqueda **no** aparezca en el historial, que empieze por espacio.
- 
``` bash
history | grep "lo que quieras buscar"
```
## Comandos de Historial

| Atajo  | Función                                     |
| ------ | ------------------------------------------- |
| Ctrl-p | Moverse al comando anterior (flecha arriba) |
| Ctrl-n | Moverse al siguiente comando (flecha abajo) |
| Alt-<  | Ir al inicio del historial                  |
| Alt->  | Ir al final del historial                   |
| Ctrl-r | Búsqueda incremental inversa                |
| Alt-p  | Búsqueda inversa no incremental             |
| Alt-n  | Búsqueda hacia adelante no incremental      |
| Ctrl-o | Ejecutar ítem actual y avanzar al siguiente |
## Expansión del Historial

| Secuencia | Función                                          |
| --------- | ------------------------------------------------ |
| !!        | Repetir último comando                           |
| !number   | Repetir comando número 'number' del historial    |
| !string   | Repetir último comando que comience con 'string' |
| !?string  | Repetir último comando que contenga 'string'     |

- - - 
## ***Sources:***