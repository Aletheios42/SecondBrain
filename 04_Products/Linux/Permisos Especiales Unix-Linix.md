**MetaTags:** #_Done 
**Tags:** #Linux #Permisos 
- - -

| Permiso        | Afecta a             | Efecto                                                                                                           |
| -------------- | -------------------- | ---------------------------------------------------------------------------------------------------------------- |
| **SUID**       | Archivos ejecutables | Se ejecutan con los permisos del propietario en lugar del usuario que los ejecuta.                               |
| **SGID**       | Archivos ejecutables | Se ejecutan con el grupo del archivo en lugar del usuario que los ejecuta.                                       |
| **SGID**       | Directorios          | Los archivos creados dentro heredan el grupo del directorio.                                                     |
| **Sticky Bit** | Directorios          | Solo el propietario puede eliminar sus archivos, incluso si otros tienen permisos de escritura en el directorio. |
###  [[SUID (Set User ID - bit 4xxx)]]
Un archivo **ejecutable** con SUID **se ejecuta con los permisos de su propietario en lugar del usuario que lo ejecuta**.  
### [[SGID (Set Group ID - bit 2xxx)]]
- **En archivos ejecutables:** Se ejecutan con el grupo del archivo, en lugar del grupo del usuario que lo ejecuta.  
- **En directorios:** **Todos los archivos creados dentro heredan el grupo del directorio**, en lugar del grupo del usuario que los crea.  
### [[Sticky Bit (bit 1xxx)]]
Un **directorio** con sticky bit solo el **propietario de un archivo o root puede eliminar archivos** incluso si otros tienen permisos de escritura en el directorio.
**Sin Sticky Bit (`drwxrwxrwx`)**, cualquier usuario podría eliminar archivos de otros.  

- - - 
## ***Sources:***