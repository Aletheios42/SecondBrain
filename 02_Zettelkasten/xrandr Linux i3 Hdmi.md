**MetaTags:** #_Done
**Tags:** #Linux #ToLink
- - -
Si tu salida HDMI se llama **HDMI-A-0** y está **conectada**, así que puedes configurarla con `xrandr`. Aquí tienes algunas opciones dependiendo de cómo quieras usar el monitor externo:
### **Guardar la Configuración**
Para que estos cambios sean persistentes, agrégalos a `~/.xprofile` o `~/.xinitrc`:

```bash
echo "xrandr --output HDMI-A-0 --mode 1920x1080 --right-of eDP" >> ~/.xprofile
```
Si usas **i3**, agrégalo en `~/.config/i3/config`:
```bash
exec --no-startup-id xrandr --output HDMI-A-0 --mode 1920x1080 --right-of eDP
```

### **Duplicar la Pantalla**
Si quieres que ambas pantallas muestren lo mismo:
```bash
xrandr --output HDMI-A-0 --mode 1920x1080 --same-as eDP
```

### ** Extender el Escritorio (colocar HDMI a la derecha de la pantalla principal)**
```bash
xrandr --output HDMI-A-0 --mode 1920x1080 --right-of eDP
```

### **Ajustar la Posición Manualmente**
Si el monitor externo está arriba:
```bash
xrandr --output HDMI-A-0 --mode 1920x1080 --above eDP
```
Si está a la izquierda:
```bash
xrandr --output HDMI-A-0 --mode 1920x1080 --left-of eDP
```

### **Escalar la Pantalla HDMI (Si el Monitor No Usa Todo el Espacio)**
Si notas bordes negros o que la imagen no llena la pantalla:
```bash
xrandr --output HDMI-A-0 --scale 1x1
```
Si necesitas ajustar el escalado manualmente:
```bash
xrandr --output HDMI-A-0 --scale 1.5x1.5
```

### **Usar Solo la Pantalla HDMI**
Si deseas apagar la pantalla del laptop y usar solo el monitor externo:
```bash
xrandr --output eDP --off --output HDMI-A-0 --mode 1920x1080
```

- - - 
## ***Sources:***