**Tags:** #_Todo
#ToTag #ToLink 
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


## Hdmi
Tu salida HDMI se llama **HDMI-A-0** y está **conectada**, así que puedes configurarla con `xrandr`. Aquí tienes algunas opciones dependiendo de cómo quieras usar el monitor externo:

### **1. Extender el Escritorio (colocar HDMI a la derecha de la pantalla principal)**
```bash
xrandr --output HDMI-A-0 --mode 1920x1080 --right-of eDP
```

### **2. Duplicar la Pantalla**
Si quieres que ambas pantallas muestren lo mismo:
```bash
xrandr --output HDMI-A-0 --mode 1920x1080 --same-as eDP
```

### **3. Usar Solo la Pantalla HDMI**
Si deseas apagar la pantalla del laptop y usar solo el monitor externo:
```bash
xrandr --output eDP --off --output HDMI-A-0 --mode 1920x1080
```

### **4. Ajustar la Posición Manualmente**
Si el monitor externo está arriba:
```bash
xrandr --output HDMI-A-0 --mode 1920x1080 --above eDP
```
Si está a la izquierda:
```bash
xrandr --output HDMI-A-0 --mode 1920x1080 --left-of eDP
```

### **5. Escalar la Pantalla HDMI (Si el Monitor No Usa Todo el Espacio)**
Si notas bordes negros o que la imagen no llena la pantalla:
```bash
xrandr --output HDMI-A-0 --scale 1x1
```
Si necesitas ajustar el escalado manualmente:
```bash
xrandr --output HDMI-A-0 --scale 1.5x1.5
```

### **Guardar la Configuración**
Para que estos cambios sean persistentes, agrégalos a `~/.xprofile` o `~/.xinitrc`:

```bash
echo "xrandr --output HDMI-A-0 --mode 1920x1080 --right-of eDP" >> ~/.xprofile
```
Si usas **i3**, agrégalo en `~/.config/i3/config`:
```bash
exec --no-startup-id xrandr --output HDMI-A-0 --mode 1920x1080 --right-of eDP
```

## bluethooth




## **2. Cambio Permanente en Arch Linux**
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
sudo nano /etc/default/keyboard
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

## Audio Alsamixer
para los perfiles de audio
- - - 
## ***Sources:***