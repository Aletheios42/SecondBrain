**Tags:** #_Todo
#Linux #Cursos 
- - -
Prequisitos: 
- Curso de VirtualBox (Virtualizacion 0)
- Curso de  Vim (opcional pero vendria genial hacerlo antes)
- un ordenador en condiciones
# Linux Basics
 ## Linux Architecture
- **uname**: Display system information (`uname -a`, `uname -r`, `uname -m`)
- Kernel (monolithic vs microkernel)
- Shell (Bash, Zsh, Fish) vs terminal
- User Space (GNU tools, libraries)
- **TTY**: Terminal types (`tty`, `pts`, `/dev/tty*`)
##  Linux Families
- **Debian-based Systems**
     - Ubuntu, Debian
     - Package management: `apt`, `dpkg`
     - Configuration: `/etc/apt/`, `/etc/network/interfaces`
 - **RHEL-based Systems**
     - CentOS, Fedora, RHEL
     - Package management: `yum`, `dnf`, `rpm`
     - Configuration: `/etc/yum.repos.d/`, `/etc/sysconfig/`
 - **SUSE-based Systems**
     - openSUSE, SUSE Linux Enterprise
     - Package management: `zypper`
     - Configuration: `/etc/zypp/`, `/etc/sysconfig/`
 - **Others**
     - Arch Linux, Manjaro, Slackware, Gentoo, parrot , kali linux
 
 ## **File System Hierarchy**
[[Sistema de Archivos de Linux]]
[[Directorios de sistema en Linux]]

- File types: regular, directory, symbolic links, device files, blocks.
# Bash Interpreter
GNU Bash o simplemente Bash (Bourne-again shell) es una interfaz de usuario de línea de comandos popular, específicamente un shell de Unix; así como un lenguaje de scripting. 
## Text Editors
- **vi/vim**: Modes (normal, insert, command), basic commands (`:wq`, `:q!`, `dd`, `yy`, `p`) 
	- --help, -set, sintax, tabs, buffers, registers, macros, marcas y marcas de archivo " m, \` " colorscheme, :tutor
- **nano**: Basic usage (save, exit, search)
- **emacs**: Basic commands (Ctrl+X, Ctrl+S, Ctrl+C)
## [[Atajos de Bash]]
[[Curso de Linux - Ejercicio - Bash Atajos y navegacion]]

---
## Programas del sistema I
#### Miscellaneous
- **tty**: Muestra el nombre del shelll actual
- **date**: Display or set the system date and time
- **cal**: Display a calendar
- **bc**: Calculadora de precisión arbitraria
- **reboot**: Reinicia el sistema
- **shutdown**: Shutdown or reboot the system
#### Documentation Access
 [[Buildtin vs Command]]
 Ejercicio de usar el man y explicar que significan los ... (acepta multiples )
Ejercicio mirar en los manuales los comandos de miscelanea

- **man**: Manual pages
  - **Sections**: 1 (commands), 2 (system calls), 3 (library functions)
  - mandb
  - **man -k keyword**: Search manual pages. man -f . te da una lista de todos tus manuales
  - **man -f command**: Show all available pages
  - - man -w: ubicacion de los manuales 
  - - man -a: Lista las versiones disponibles
  
- **info**: GNU documentation
  - More detailed than man pages
  - Hypertext format
  - **Navigation**: `n` (next), `p` (previous), `u` (up)

- **--help**: Quick reference for commands
  - Available for most GNU utilities
  - Shows common options and usage
#### 📂 Manipulación de archivos y directorios
 [[Rutas en Linux]]
 Ejercicio para listar las rutas de los archivos de los manuales
 [[Globbing]]:

- **ls**: Lista archivos y directorios
  - **options**: `-R` (recursive), `-l` (long format), `-i` (inode), `-a` (all), `-d` (directories), `-t` (sort by time)
- **cd**: Cambia de directorio
  - **options**: `-` (previous directory), `~` (home directory), `/` (root directory)
- **pwd**: Muestra la ruta del directorio actual
- **mkdir**: Crea un directorio
  - **-p**: Crea directorios padres si no existen
- **rmdir**: Elimina un directorio vacío
- **rm**: Elimina archivos o directorios
  - **-f**: Fuerza la eliminación sin preguntar
  - **-r**: Elimina directorios y su contenido recursivamente
  - **-i**: Pregunta antes de eliminar
- **cp**: Copia archivos o directorios
  - **-r**: Copia directorios recursivamente
- **mv**: Mueve o renombra archivos
- **ln**: Crea enlaces
  - **-s**: Crea enlaces simbólicos
#### 📝 Visualización y 🔍 Análisis de archivos
 [[Lab - Examen exhaustivo de archivos de sistema]]
 Ejercicio con printf sobre el ASCII, hexadecimal, octal, binario, etc.
 Ejercicio con echo y stat (touch puede molar)

- **cat**: Muestra el contenido de un archivo
  - **-E**: Muestra `$` al final de cada línea
- **tac**: Muestra el contenido de un archivo en orden inverso
- **tee**: Redirige salida a un archivo y a la vez la muestra en pantalla
- **less**: Visualiza archivos de texto
	- press h to see help page
- **head**: Muestra las primeras líneas de un archivo
  - **-n**: Especifica el número de líneas a mostrar
- **tail**: Muestra las últimas líneas de un archivo
  - **-n**: Especifica el número de líneas a mostrar
- **echo**: Muestra texto en la salida estándar
- **printf**: Formatea y muestra texto
- **touch**: Cambia las marcas de tiempo de un archivo o lo crea si no existe
- **stat**: Muestra el estado del archivo
- **file**: Determina el tipo de archivo
- **diff**: Compara archivos línea por línea
- **diff3**: Compara tres archivos y muestra diferencias
- **patch**: Aplica diferencias a archivos
#### Historial de comandos
 bash_history

- **history**: Muestra el historial de comandos
  - **!n**: Ejecuta el comando número `n` del historial
  - **!-n**: Ejecuta el comando `n` posiciones antes del último
  - **!!**: Repite el último comando
  - **!string**: Ejecuta el comando más reciente que comienza con `string`
  - **Ctrl+R**: Busca en el historial de comandos interactivamente
- - -
### Meter ejercicios de programas sistema I
- - - 
## How Sentences Are Made
#### [[Secuencias de Escape en Caracteres]]
#### Sentences: Basic units of execution
Sintax  ---> <infile cmd1 operador cmd2 > outfile
 Binary Operators "&&, ||, ;, |"
 [[Redirecciones en Unix-Linux]]
#### Expansiones
[[Ejercicio -  Expansiones]]
- Pathname expansion:
- Tilde Expansion: \`date\`
- Arithmetic Expansion: $()  --> Append: expr
- [[Expansión de Llaves en Bash]]: {a,b,c} {a..c}
- Parameter Expansion: $var 
#### quoting 
- single quote
- double quote
- invertida quote (deprecated)
#### Command susbtitution "<(), double qutes, $() "
 [[Curso Linux - Lab - Monitoreo de la Ejecución de un Comando en una Shell[]] 
 ejercicio con variables de entorno y env -i para demostras esto , meter ejericio de hacer un prompt en tu bashrc
 
- comandos exec y eval
---

## Programas del sistema II
#### Variable managment
- **env**: Display environment variables
- **printenv**: Display environment variables
- **locale**: Display locale settings
- **set**: Set or display shell options and positional parameters
- **unset**: Unset or display shell environments
- **export**: Set environment variables
  - **option**: `-p` (Display exported variables)
- **source**: Execute commands from a file
- **alias**: Create command aliases
- **unalias**: Remove command aliases
- **exit**: Exit the shell
#### Selección y Sustitución de Texto
Buscar los ejercicios del sepe
Ejercicio para añadir en el manual los atajos de bash y de tmux, y asi poder mirarlo en el manual.

- **tr**: Sustituye o elimina caracteres
 - **-d**: Delete characters
 - **-s**: Squeeze repeated characters
  - **-t**: Truncate
- **paste**: Une líneas de archivos
- **join**: Une líneas de archivos basadas en un campo común
- **split**: Divide archivos en partes más pequeñas
- **cut**: Extrae secciones de líneas en archivos
  - **-d**: Delimiter
  - **-f**: Fields
- **column**: Formatea texto en columnas
- **strings**: Extrae cadenas imprimibles de archivos binarios
#### Searching Files
 [[Linux - Ejercicio - Busca Archivos por el Sistema]]

- **locate / updatedb**: Find files by name / Actualiza la base de datos de locate
- **find**: Search for files in a directory hierarchy
  - **exec**: Execute a command on found files
	  - **+**: Placeholder for multiple files
	  - **/**: Search from root directory
  - **lots of flags**: Consultar `man find` para más opciones.
- **xargs**: Build and execute command lines from standard input
	- I
#### Filtrado de texto
 [[Chuleta_Regex_Apuntes.jpg]]
 Meter ejercicios de regex, de url mirar el viedo de luke smith
 Meter ejercicios de sed, de url mirar el viedo de luke smith
 **Tools**: `grep`, `sed`, `awk`, `find` (en algunas distros, además en algunas se puede poner la flag `-regex`)
 [[Ejercicio - Regex]] y buscar más ejercicios del sepe

- **sort**: Ordena líneas de un archivo
  - **-n**: Sort numerically
- **uniq**: Filtra líneas duplicadas
- **wc**: Cuenta líneas, palabras y caracteres en un archivo
  - **-c**: Count bytes
  - **-w**: Count words
  - **-l**: Count lines
- **grep**: Filtrado de texto
  - **-E**: Extended regex
  - **-i**: Ignore case
  - **-n**: Show line numbers
  - **-v**: Invert match
  - **-f**: Read patterns from a file
  - **-r**: Recursive search
- **sed**: Procesamiento y edición de texto.
  - **s/OldPattern/NewPattern/(g)**: Sustituye patrones (el delimitador `/` puede ser cambiado por otro carácter si es necesario).
- **awk**: Procesamiento de texto avanzado.
#### Compression and Sync
Mirar el ejercicio de christine

- **gzip**: Compress files
- **bzip2**: Compress files
- **xz**: Compress files
- **tar**: Archive files
- **cpio**: Copy files to and from archives
- **rsync**: Sync files/directories
- **shasum**: Compute and check SHA checksums
- - - 
### Meter ejercicios de programas sistema II
- - - 
## manejar mi enviroment
 [[Lab - Explorando Las Variables de Bash]]
[[Lab - Tmux Primeros Pasos]]
[[Variables de Bash]] 
Ejercicio añadir tmux a tu bashrc

 - Archivos de configuracion bashrc y profile
	 - .bash_profile 
	 - .bashrc 
	 - .bash_logout 
	 - .bash_history
	 
 - [[Multiplexores]]
	- screen 
	- [[Tmux]]
- - -
## Programas del sistema III
#### 🔒 Gestión de usuarios
[[Lab - Gestión de Usuarios y Permisos]]
 **root #** vs **regular user $**
 Archivos: `/etc/passwd`, `/etc/shadow`, `/etc/skel`
 **sudoer**
 **privilegios del usuario instalador**
 **User and Group ID Numbering Conventions**

- **su**: Cambia de usuario pero no de environment
  - **-l / --login**: Ejecuta una shell como root con su environment
  - **-**: Ejecuta una shell como root con su environment
- **sudo**: Ejecuta comandos como root
  - **-u**: Ejecuta como otro usuario
- **whoami**: Muestra el usuario actual
- **who**: Muestra usuarios conectados
- **id**: Muestra UID y GID del usuario actual
  - **-u**: Muestra solo el UID
  - **-n**: Muestra el nombre en lugar del ID
- **groups**: Muestra grupos de un usuario
  - **-u**: Muestra solo el UID
  - **-n**: Muestra el nombre en lugar del ID
- **(add/del)user**: Crea/Elimina un nuevo usuario (diferencia con `useradd`)
- **usermod**: Modifica un usuario
  - **-a**: Añade al usuario a un grupo
  - **-G**: Especifica grupos adicionales
- **(add/del)group**: Crea/Elimina un nuevo grupo (diferencia con `groupadd`)
- **groupmod**: Modifica un grupo
- **chage**: Cambia la caducidad de la contraseña de un usuario
- **mask**: Resta permisos
- **umask**: Configura permisos por defecto

#### 🔒 Gestión de permisos
 Mirar laboratorio del sepe
 **permisos Linux - Unix**
 [[Permisos Especiales Unix-Linux]]
 **“a(all), u(user), g(group), o(other)”**
 **symbolic vs octal 0xxxx**

- **su**: Cambia de usuario pero no de environment
  - **-**: Para el environment del argumento
- **sudo**: Ejecuta comandos como root
  - **-u**: Ejecuta como otro usuario
- **whoami**: Muestra el usuario actual
- **who**: Muestra usuarios conectados
- **id**: Muestra UID y GID del usuario actual
- **groups**: Muestra grupos de un usuario
- **(add/del)user**: Crea/Elimina un nuevo usuario (diferencia con `useradd`)
- **usermod**: Modifica un usuario
  - **-a**: Añade al usuario a un grupo
  - **-G**: Especifica grupos adicionales
- **(add/del)group**: Crea/Elimina un nuevo grupo (diferencia con `groupadd`)
- **groupmod**: Modifica un grupo
- **passwd**: Cambia la contraseña de un usuario
- **chmod**: Cambia permisos de archivos
  - **06777**: Permisos en formato octal
  - **-w**: Quita permisos de escritura
  - **u:x**: Añade permiso de ejecución al usuario
- **chown**: Cambia el propietario de un archivo
- **chgrp**: Cambia el grupo de un archivo

#### 🛠 Gestión de procesos y señales
Ejercicios en **64. Managing process priority**
[[Jobs en Linux]]  y [[Procesos en Linux]]
[[Ejercicio - Procesos]]
**cmd &**: Ejecuta un comando en segundo plano
**zombies**: Procesos terminados pero no liberados
Si **tty=?**: Es un proceso de red
Different stats of a process like "D", "S", "T", "Z" etc

entender que top es un script que llama a ps.

- **ps**: Lista procesos activos
  - **a**: Muestra procesos de todos los usuarios
  - **u**: Muestra formato de usuario
  - **x**: Muestra procesos sin terminal
  - **e**: Muestra environment
  - **l**: Formato largo
  - **f**: Formato de árbol
  - Las 3 sintaxis: Unix, Berkeley, GNU
- **pgrep**: Busca procesos por nombre
  - **-u**: Filtra por usuario
  - **-a**: Muestra el comando completo
  - **-t**: Filtra por terminal
- **bg**: Envía un proceso a segundo plano
- **fg**: Devuelve un proceso a primer plano
- **jobs**: Lista procesos en segundo plano
  - **-l**: Muestra PIDs
  - Ejercicio con `sleep` y moverlo entre foreground y background.
- **top**: Muestra procesos en tiempo real
  - En la parte superior se muestran las medias
- **kill**: Termina un proceso por PID
  - **-s**: Especifica una señal
  - **%**: Termina un proceso en segundo plano
  - **Tabla de señales**: Consultar `man kill`
  - Ejercicios de Christine: **63. Sending signals to process**
- **killall**: Termina procesos por nombre (SIGTERM)
- **pkill**: Termina procesos por coincidencia de nombre
  - **-a**: Muestra el comando completo
  - **-g**: Filtra por grupo
- **nice**: Ejecuta un proceso con prioridad modificada
  - **nice level, priority on Linux, ranges**
- **renice**: Cambia la prioridad de un proceso
- **w**: Muestra quién está conectado y qué está haciendo
- **uptime**: Muestra el tiempo de actividad del sistema
- **sleep**: Retrasa la ejecución por un tiempo especificado
- **at**: Programa un comando para ejecutarse en un momento específico
- **nohup**: Ejecuta un comando inmune a cierres de sesión
#### ⏳ Gestión de memoria y rendimiento
 [[Paquete Sysstat]]
 Ejercicio de usar `cut` y `grep` en archivos del sistema para imitar comandos de este paquete (hacerlo antes de ver los comandos). Ejemplo: imitar `sar` con `cut`, `grep` y `top`.

- **free**: Muestra el uso de memoria
- **vmstat**: Información sobre CPU, memoria, swap
- **iostat**: Estadísticas de CPU y discos
- **uptime**: Muestra el tiempo encendido del sistema
- **dstat**: Alternativa a `vmstat`
- **sar**: Registra el uso de CPU y memoria
#### Partitions and Disks
[[Ejercicio -  Usbs en Linux]]
[[Ejercicio -  Hacer Paticiones y Formatearlas]]

- **dd**: Convierte y copia archivos
- **df**: Muestra el uso del espacio en disco
- **du:**
- **fdisk/gparted**: Editor de particiones MBR/GPT
- **mount**: Monta un sistema de archivos
- **umount**: Desmonta un sistema de archivos
- **findmount**: Encuentra la ruta de un dispositivo de almacenamiento.
- **fsck**: Verifica y repara un sistema de archivos
- **fdisk**: Manipulador de tabla de particiones
- **mkfs**: Crea un sistema de archivos
- **genisoimage**: Crea archivos ISO
- **whodid**: Verifica la propiedad de un archivo
- **md5sum**: Calcula y verifica el resumen MD5
- **makeswap:**
- **swapoff:** 
- - - 
### Meter ejercicios de programas sistema III
- - - 
# Bash Scripting

##  Shell Scripting Basics

- Shebang: #!/bin/bash, #!/usr/bin/env bash
- Variables: Declaration, usage, scope
- Local vs Global Variables:
- Local: Defined within a function
- Global: Accessible throughout the script
## Conditionals
- Test: test, [ ], [[ ]]
- File tests (-f, -d, -r)
- String comparisons (=, !=, -z, -n)
- Numeric comparisons (-eq, -ne, -gt, -lt)
- if-else: Syntax and examples
- case: Syntax and examples
## Loops
Ejercicio copia 100 veces "Me encanta aprender Linux"(de las 3 maneras esta bien)

- for: Syntax and examples
- while: Syntax and examples
- until: Syntax and examples
## Functions
- Definition and usage
- Arguments and return values
- .bashrc
##  Advanced Scripting
- Arrays: Declaration, iteration, manipulation
- Input/Output: read, echo, printf
- Error Handling: set -e, trap, exit codes
- bash-Macros: EJ: IFS
- makefifo, makenod
# System Administration
##  Boot Process
- BIOS/UEFI, GRUB, init, systemd
- Configuration files:
- /etc/default/grub (GRUB configuration)
- /etc/fstab (file system table)
- /etc/systemd/system (systemd services)
## Service Management
- systemd 
- systemctl
- journalctl
- localectl
- datetimectl(revisar)
- networkctl
Legacy init systems: /etc/init.d/, /etc/inittab
## Package Management
- RPM-based: rpm, yum, dnf
- Configuration: /etc/yum.conf, /etc/yum.repos.d/
- DEB-based: dpkg, apt, apt-get
- Configuration: /etc/apt/sources.list, /etc/apt/apt.conf
## Kernel Management
- Kernel modules: lsmod, insmod, rmmod, modprobe
- Configuration: /etc/modprobe.d/, /boot/
## File System Management
- File system types: ext4, XFS, Btrfs
- Tools: mkfs, fsck, tune2fs, xfs_admin
- Mounting: mount, umount, /etc/fstab
## Storage Management
- LVM: pvcreate, vgcreate, lvcreate
- RAID: mdadm
- Network Storage: NFS, Samba, iSCSI
## Backup and Recovery
- Tools: tar, rsync, dd, dump/restore
- Configuration: /etc/rsyncd.conf, cron jobs for backups
##  Logging and Monitoring
- Logging: syslog, rsyslog, journalctl
- Configuration: /etc/rsyslog.conf, /etc/logrotate.conf
- Monitoring: top, htop, nmon, sar
#  Networking
#### 📡 Redes y conectividad ([[Paquete Sysstat]])
ip  → Herramienta compleja para redes
	options: a, r, l, 
ping → Prueba conectividad con una dirección
	-c
traceroute → Rastrea la ruta hasta un host
netstat -tulnp → Lista conexiones de red
ss -tulnp → Alternativa moderna a netstat
curl → Descarga archivos o datos desde la web
wget → Descarga archivos desde la web
scp → Copia archivos vía SSH
rsync → Sincroniza archivos de forma eficiente
nmap → Escanea puertos abiertos
whois → Muestra información de dominios
dig → Consulta registros DNS
nslookup → Consulta registros DNS
## Network Configuration
- Tools: ifconfig, ip, nmcli, nmtui
- Configuration files:
- /etc/network/interfaces (Debian-based)
- /etc/sysconfig/network-scripts/ifcfg-* (RHEL-based)
## Network Services
- DNS: BIND (named.conf, /etc/resolv.conf)
- DHCP: isc-dhcp-server (/etc/dhcp/dhcpd.conf)
- NTP: chrony (/etc/chrony.conf), ntpd (/etc/ntp.conf)
## Remote Access
- SSH: sshd (/etc/ssh/sshd_config)
- FTP: vsftpd (/etc/vsftpd.conf)
- VPN: OpenVPN (/etc/openvpn/), WireGuard (/etc/wireguard/)

## Firewall and Security
- iptables: /etc/sysconfig/iptables
- firewalld: /etc/firewalld/
- SELinux: /etc/selinux/config

## Troubleshooting
- Tools: ping, traceroute, netstat, ss, tcpdump
- Configuration: /etc/hosts, /etc/nsswitch.conf

# Security
##  User and Group Management
- Configuration Files:
- /etc/passwd, /etc/shadow, /etc/group, /etc/sudoers
- getent: Retrieve entries from system databases (getent passwd, getent group)
##  ACLs (Access Control ListsFile System Security)
- file
## File System Security
- Tools: chattr, lsattr, setfacl, getfacl
- Encryption: LUKS (cryptsetup), GPG
## Network Security
- SSH hardening: /etc/ssh/sshd_config
- Firewalls: iptables, firewalld
- Intrusion detection: fail2ban (/etc/fail2ban/)
## Security Auditing
- Tools: auditd (/etc/audit/auditd.conf), lynis, rkhunter
##  Encryption Tools
- Compression and encryption: xz, gzip, bzip2, zip, openssl

# Advanced Topics
## Virtualization
- KVM, QEMU, libvirt (/etc/libvirt/)
- Containers: Docker (/etc/docker/), Podman

## Cloud Integration
- AWS, Azure, Google Cloud
- Infrastructure as Code: Terraform, Ansible (/etc/ansible/) 
- Automation and Configuration Management
- Ansible, Puppet (/etc/puppet/), Chef, SaltStack

## High Availability and Load Balancing
- HAProxy (/etc/haproxy/), Keepalived (/etc/keepalived/)
- Clustering: Pacemaker, Corosync

# Resources and References
## Books
"Linux Command Line and Shell Scripting Bible"
"Linux Administration Handbook"
# Miscelanea
## Diccionario
- pruning ->  mantener limpio el sistema
- There are two files that an administrator can use to limit access to any daemon: /etc/hosts.allow and /etc/hosts.deny.
## Concepts to Add
- strace
- tracing
- gdb
- Apparmor
- grooff y formateo de documentos

## Inspeccion de Binarios
#### Herramientas
gdb
radare2
perf
#### Comandos
- readelf
- hexdump
- objdump
- nm
- strings
- ldd
- strace
- lstrace
- file
## Exercises to add
- Agregar binarios al path

- - - 
## ***Sources:***
- https://iximiuz.com/en/