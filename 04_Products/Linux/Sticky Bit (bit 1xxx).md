**MetaTags:** #_Done 
**Tags:** #Linux #Permisos
- - -
Es un [Permiso Especial Linux - Unix](Permisos Especiales Linux Unix) que para directorios, solo el **propietario de un archivo o root puede eliminarlo,** incluso si otros tienen permisos de escritura en el directorio. **Sin Sticky Bit (`drwxrwxrwx`)**, cualquier usuario podría eliminar archivos de otros.  

🔹 **Uso típico:**  
- **Evitar que los usuarios borren archivos ajenos en carpetas compartidas** (`/tmp`).  

🔹 **Ejemplo:**  
```bash
chmod +t /tmp # chmod 1xxx /tmp
ls -ld /tmp
$ drwxrwxrwt 10 root root 4096 Feb  1 12:34 /tmp/
```
 **Lo que ocurre:**  
- Todos los usuarios pueden escribir en `/tmp`, pero **solo el dueño de un archivo puede eliminarlo**.  
- - - 
## ***Sources:***