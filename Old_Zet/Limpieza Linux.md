**Tags:** #_Todo
#ToTag #ToLink 
- - -
==funciona mierar y sintetizar==
Para ver cuánto ocupa un directorio en Linux, usa `du` o `ncdu`:

### **1. Ver tamaño total de un directorio**
```bash
du -sh /ruta/del/directorio
```
Ejemplo:
```bash
du -sh /var
```
Esto te dirá cuánto espacio ocupa `/var` en una forma legible (MB/GB).

---

### **2. Ver tamaño de subdirectorios ordenados**
```bash
du -h --max-depth=1 /ruta/del/directorio | sort -h
```
Ejemplo:
```bash
du -h --max-depth=1 /var | sort -h
```
Esto te mostrará el tamaño de cada subdirectorio dentro de `/var`, ordenado de menor a mayor.

---

### **3. Usar `ncdu` para una vista interactiva**
Si quieres una forma más visual:
```bash
sudo pacman -S ncdu
ncdu /
```
Esto abrirá una interfaz donde puedes navegar y ver qué ocupa más espacio.

Si solo quieres analizar `/var`:
```bash
ncdu /var
```

---

### **4. Buscar archivos grandes (>500MB)**
```bash
find / -type f -size +500M -exec ls -lh {} + | awk '{ print $9 ": " $5 }'
```
Esto mostrará archivos mayores a 500MB y sus tamaños.

---

Si ves que un directorio ocupa demasiado, podemos optimizarlo o moverlo a `/home`.

- - - 
## ***Sources:***