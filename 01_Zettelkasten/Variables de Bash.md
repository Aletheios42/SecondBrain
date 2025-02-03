**Tags:** #_Todo
#ToTag #ToLink 
- - -
- [[Variables de Globales o de Entorno Bash]] (por ejemplo, `PATH`, `USER`, `HOME`, etc.) son globales y pueden ser heredadas por procesos hijos.
- [[Variables Locales en bash]] existen dentro del shell o script en el que fueron definidas, a menos que se exporten.
- [[Variables Especiales de Bash]]: Son gestionadas internamente por Bash (por ejemplo, `$?`, `$$`, `PROMPT_COMMAND`).
- [[Variables de Localidad en Bash]]: Son específicas para la configuración regional del sistema (`LANG`, `LC_TIME`, etc.).

## **Variables de Información del Usuario y del Shell**
- `HOME`
- `USER` / `LOGNAME`
- `SHELL`
- `UID`
- `GROUPS`
## **Variables de Información del Sistema**
- `HOSTNAME`
- `MACHTYPE`
- `HOSTTYPE`
- `OSTYPE`
## **Variables de Rutas y Directorios**
- `PATH`
- `PWD`
- `OLDPWD`
- `CDPATH`
- `LD_LIBRARY_PATH`
## **Variables de Configuración de Inicio del Shell**
- `ENV`
- `BASH_ENV`
## **Variables de Configuración Regional e Idioma**
- `LANG`
- `LC_ALL`
- `LC_COLLATE`
- `LC_CTYPE`
## **Variables de Terminal y Servidor de Pantalla**
- `TERM`
- `DISPLAY`
## **Variables de Historial y Prompt del Shell**
- `HISTSIZE`
- `HISTFILESIZE`
- `HISTFILE`
- `HISTCONTROL`
- `PS1`
- `PS2`
- `PROMPT_COMMAND`
## **Variables de Proxy y Red**
- `HTTP_PROXY`
- `HTTPS_PROXY`
- `FTP_PROXY`
- `NO_PROXY` / `no_proxy`
- `ALL_PROXY` / `all_proxy`
## **Variables de Programas**
- `EDITOR`
- `VISUAL`
- `PAGER`
- `BROWSER`
## **Variables de Control de Procesos**
- `$`
- `!`
- `?`
## **Variables Especiales**
- `RANDOM`
- `SECONDS`
- `TMOUT`
- `MAIL`
## **Otras Variables**
- `LZ` – (Variable personalizada, puede ser utilizada para compresión o en contextos específicos).
---
## ***Sources:***