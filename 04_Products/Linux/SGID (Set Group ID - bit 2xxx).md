**MetaTags:** #_Done 
**Tags:** #Linux #Permisos
- - -
SUID es un [Permiso Especial Linux - Unix](Permisos Especiales Linux Unix) que permite que un ejecutable **se ejecuta con los permisos de su grupo propietario en lugar del usuario que lo ejecuta**.  

- **En archivos ejecutables:** Se ejecutan con el grupo del archivo, en lugar del grupo del usuario que lo ejecuta.  
- **En directorios:** **Todos los archivos creados dentro heredan el grupo del directorio**, en lugar del grupo del usuario que los crea.  

🔹 **Uso típico:**  
- En binarios compartidos, asegura que los procesos corran con permisos específicos de grupo.  

🔹 **Ejemplo en archivos ejecutables:**  
```bash
chmod g+s script.sh
ls -l script.sh
-rwxr-sr-x 1 user shared 12345 Feb  1 12:34 script.sh
```
 **Lo que ocurre:**  
- Cualquier usuario que ejecute `script.sh` lo hará con los permisos del grupo `shared`.  



- En directorios compartidos (`/var/shared`), mantiene el grupo correcto para colaboración.  
🔹 **Ejemplo en directorios:**  
```bash
chmod g+s /var/shared
ls -ld /var/shared
drwxrwsr-x 2 user shared 4096 Feb  1 12:34 /var/shared/
```
 **Lo que ocurre:**  
- Todos los archivos creados dentro de `/var/shared` pertenecerán automáticamente al grupo `shared`.  


- - - 
## ***Sources:***