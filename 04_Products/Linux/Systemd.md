**MetaTags:** #_Todo
**Tags:** #Linux #ToLink 
- - -
Systemd es un administrador de procesos,

Utiliza archivos llamados Units para llevar un registro atómico de las configuraciones

Puede ser problematico en la orquestacion de contenedores Docker,
pues systemd/journald controla la salida, en vez de volvarse  a /dev/stdout
donde Kubernetes o OpenSwift espera la salida


Podman tiene una gran compatibilidad con systemd `--systemd=true|false`
que monta tmpfs en /run y /tmp ante de inicar systemd 


- - - 
#### ***Sources:***
- [courso](https://systemd.io/)
- [Curso](https://systemd-by-example.com/)