**Tags:** #_Todo
**MetaTags:** #Linux #ToLink
- - -
 Todas las configuraciones son susceptibles de ser alteradas en la configuracion de la distribucion o de la shell

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

========
## mirar esto


## **Cambio Permanente en Arch Linux**
==ESTO NO VA AQUI==
### **Opción 1: Usar `localectl` (Recomendado)**
Este comando cambia el teclado en **Xorg y en la terminal (TTY)**:
```bash
sudo localectl set-x11-keymap es
```
Si también quieres configurarlo para la consola en modo texto (fuera de Xorg/Wayland):
```bash
sudo localectl set-keymap es
```
Para verificar los cambios:
```bash
localectl status
```
Debería mostrar:
```
System Locale: LANG=es_ES.UTF-8
VC Keymap: es
X11 Layout: es
```
### **Opción 2: Editar `/etc/default/keyboard` (Para Debian/Ubuntu y algunos Arch setups)**
Edita el archivo de configuración del teclado:
```bash
sudo vim /etc/default/keyboard
```
Asegúrate de que las líneas sean:
```
XKBLAYOUT="es"
XKBOPTIONS=""
```
Guarda (`Ctrl + X`, `Y`, `Enter`) y aplica los cambios con:
```bash
sudo dpkg-reconfigure keyboard-configuration
```
Si no usas Debian, simplemente reinicia para que se apliquen.
### **Opción 3: Configuración en i3**
Si usas **i3**, agrégalo en tu archivo de configuración:
```bash
nano ~/.config/i3/config
```
Añade esta línea para que se aplique cada vez que inicies sesión en i3:
```
exec --no-startup-id setxkbmap es
```
Guarda y recarga i3 con:
```bash
i3-msg reload
```
=========
- - - 
## ***Sources:***