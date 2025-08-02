**MetaTags:** #_Done 
**Tags:** #Linux #Permisos
- - -
SUID es un [Permiso Especial Linux - Unix](Permisos Especiales Linux Unix) que permite que un ejecutable **se ejecuta con los permisos de su propietario en lugar del usuario que lo ejecuta**.  

🔹 **Uso típico:** Permitir que programas críticos (como `passwd`) funcionen con permisos elevados sin necesidad de ser root.  

🔹 **Ejemplo:**  
```bash
chmod u+s /usr/bin/passwd  # chmod 4xxx /usr/bin/passwd
ls -l /usr/bin/passwd
$ -rwsr-xr-x 1 root root 54256 Feb  1 12:34 /usr/bin/passwd
```
 **Lo que ocurre:**  
- Cualquier usuario puede ejecutar `passwd`, pero el programa correrá con permisos de **root**.  
- Sin SUID, el usuario necesitaría privilegios de root para modificar `/etc/shadow`.  
- - - 
## ***Sources:***