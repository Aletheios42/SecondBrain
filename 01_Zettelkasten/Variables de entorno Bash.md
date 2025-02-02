**Tags:** #_Done 
#Linux #Bash #ToLink 
- - -
Para ver todas las variables de entorno actuales, usa:
```bash
printenv
env
```
### **1. Información del Shell y del Usuario**
- **`HOME`**: Directorio de inicio del usuario actual.
- **`USER`** o **`LOGNAME`**: Nombre de usuario del usuario actual.
- **`SHELL`**: Ruta al shell del usuario actual.
- **`UID`**: ID numérico del usuario actual.
- **`GROUPS`**: Grupos a los que pertenece el usuario actual.
---
### **2. Información del Sistema**
- **`HOSTNAME`**: Nombre del equipo (host).
- **`HOSTTYPE`**: Tipo de hardware del sistema (por ejemplo, `x86_64`).
- **`OSTYPE`**: Tipo de sistema operativo (por ejemplo, `linux-gnu`).
- **`MACHTYPE`**: Tipo de máquina (por ejemplo, `x86_64-pc-linux-gnu`).

---
### **3. Rutas y Directorios**
- **`PATH`**: Lista de directorios donde el shell busca ejecutables.
- **`PWD`**: Directorio de trabajo actual.
- **`OLDPWD`**: Directorio de trabajo anterior (antes del último `cd`).
- **`CDPATH`**: Lista de directorios usados como ruta de búsqueda para `cd`.
---
### **4. Comportamiento del Shell**
- **`HISTSIZE`**: Número de comandos que se recuerdan en el historial.
- **`HISTFILESIZE`**: Número máximo de líneas en el archivo de historial.
- **`HISTFILE`**: Archivo donde se guarda el historial (por defecto, `~/.bash_history`).
- **`HISTCONTROL`**: Controla cómo se guardan los comandos en el historial (por ejemplo, ignorar duplicados).
- **`PS1`**: Cadena del prompt principal (personaliza la línea de comandos).
- **`PS2`**: Cadena del prompt secundario (para comandos de varias líneas).
- **`PROMPT_COMMAND`**: Comando que se ejecuta antes de mostrar el prompt principal.
---
### **5. Idioma y Configuración Regional**
- **`LANG`**: Configuración regional predeterminada (por ejemplo, `en_US.UTF-8`).
- **`LC_ALL`**: Anula todas las configuraciones regionales.
- **`LC_COLLATE`**: Controla el orden de clasificación para ordenar.
- **`LC_CTYPE`**: Controla la clasificación de caracteres y la conversión de mayúsculas/minúsculas.
---
### **6. Terminal y Pantalla**
- **`TERM`**: Tipo de terminal (por ejemplo, `xterm-256color`).
- **`DISPLAY`**: Servidor de pantalla X11 (por ejemplo, `:0`).
- **`COLUMNS`**: Número de columnas en la terminal.
- **`LINES`**: Número de líneas en la terminal.
---
### **7. Variables Específicas de Programas**
- **`EDITOR`**: Editor de texto predeterminado (por ejemplo, `vim`, `nano`).
- **`VISUAL`**: Editor de pantalla completa (a menudo igual que `EDITOR`).
- **`PAGER`**: Programa de paginación predeterminado (por ejemplo, `less`).
- **`BROWSER`**: Navegador web predeterminado.
---
### **8. Control de Procesos y Trabajos**
- **`$`**: ID del proceso (PID) del shell actual.
- **`!`**: PID del último comando en segundo plano.
- **`?`**: Estado de salida del último comando ejecutado.
---
### **9. Gestión del Entorno**
- **`ENV`**: Archivo para configuraciones de entorno en shells no interactivos.
- **`BASH_ENV`**: Archivo para configuraciones de entorno al iniciar Bash.

---
### **10. Red y Proxy**
- **`HTTP_PROXY`**: Servidor proxy para solicitudes HTTP.
- **`HTTPS_PROXY`**: Servidor proxy para solicitudes HTTPS.
- **`FTP_PROXY`**: Servidor proxy para solicitudes FTP.
- **`NO_PROXY`**: Lista de dominios excluidos del proxy.

---
### **11. Misceláneos**
- **`RANDOM`**: Genera un número aleatorio entre 0 y 32767.
- **`SECONDS`**: Número de segundos desde que se inició el shell.
- **`TMOUT`**: Cierra la sesión automáticamente después de un número de segundos.
- **`MAIL`**: Ruta al buzón de correo del usuario.
- - - 
## ***Sources:***