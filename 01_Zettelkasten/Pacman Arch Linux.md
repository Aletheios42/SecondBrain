**Tags:** #_Todo
#ToTag #ToLink 
- - -
`pacman` es el gestor de paquetes de Arch Linux. 
## 🔍 Consultas y búsqueda
```sh
pacman -Q             # Lista los paquetes instalados
pacman -Qs <nombre>   # Busca paquetes instalados por nombre o descripción
pacman -Ql <paquete>  # Lista los archivos instalados por un paquete
pacman -Qi <paquete>  # Muestra información detallada de un paquete
pacman -Qo <archivo>  # Identifica a qué paquete pertenece un archivo
pacman -Fl <paquete>  # Lista los archivos de un paquete en los repositorios
```
## 📦 Instalación y actualización
```sh
pacman -Syu                # Actualiza la base de datos e instala actualizaciones
pacman -Sy                 # Sincroniza la base de datos de paquetes
pacman -S <paquete>        # Instala un paquete
pacman -U <archivo.tar.zst> # Instala un paquete local
```
## ❌ Eliminación de paquetes
```sh
pacman -R <paquete>         # Elimina un paquete (deja dependencias)
pacman -Rs <paquete>        # Elimina un paquete y sus dependencias no usadas
pacman -Rns <paquete>       # Elimina el paquete, dependencias y archivos de configuración
```
## 🛠 Mantenimiento y limpieza
```sh
pacman -Sc              # Borra caché de paquetes antiguos
pacman -Scc             # Borra toda la caché de paquetes
pacman -Qdt             # Muestra paquetes huérfanos
pacman -Rns $(pacman -Qdtq)  # Elimina paquetes huérfanos
```
## ⚠ Solución de problemas
```sh
pacman -Syyu                # Forza la sincronización y actualización
pacman -S --overwrite <ruta> # Fuerza la reinstalación de un archivo
pacman -D --asdeps <paquete> # Marca un paquete como dependencia
pacman -D --asexplicit <paquete> # Marca un paquete como instalado manualmente
```
## 📝 Notas adicionales
- Usar `sudo` si no tienes permisos de root.
- Para paquetes AUR, usa `yay` o `paru` en lugar de `pacman`.
- Revisar `/etc/pacman.conf` para configuraciones adicionales.
- - - 
## ***Sources:***