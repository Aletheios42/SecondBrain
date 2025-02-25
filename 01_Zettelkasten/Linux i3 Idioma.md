**Tags:** #_Todo
#ToTag #ToLink 
- - -

- - -
 Todas las configuraciones son susceptibles de ser alteradas en la configuracion de la distribucion o de la shell
## Idioma
Para cambiar el **layout del teclado a español** en Linux, hay varias formas según el entorno que uses. Aquí te dejo los métodos más comunes:
## **1. Cambio Temporal (Para la Sesión Actual)**
Si solo quieres cambiar el teclado en la sesión actual sin reiniciar, usa:  

```bash
setxkbmap es
```
Si usas **i3**, puedes ejecutarlo en una terminal o agregarlo a tu configuración de i3 para que se aplique al inicio.

Verifica que el cambio se realizó correctamente con:  
```bash
setxkbmap -query
```
Debe mostrar algo como:
```
layout:     es
```

==ideas para mejorar el parrafo==

listar configuracion actual de teclado:
xmodmap -pke

por defecto:
setxkbmap -option
sexkbmap -option terminate:la norma que cambia las teclas

xev para hacer pruebas

- - - 
## ***Sources:***