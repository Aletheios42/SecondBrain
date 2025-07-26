**Tags:** #_Done
**MetaTags:** #Linux
- - -
Es un archivo especial que contiene la ruta a un archivo o directorio. Constituye un inodo propio en la [[Tabla de Inodos]] y contiene la ruta a otro archivo, permitiéndole referenciar archivos en cualquier sistema de archivos o incluso rutas inexistentes. 
A diferencia del [[Enlace Duro]], requiere resolución de ruta en cada acceso, lo que provoca overhead y se rompe si el archivo destino se mueve o elimina.
Se crean:
``` bash
ln -s ExitingFile SimbolicLink
```
- - - 
## ***Sources:***