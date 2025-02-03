**Tags:** #_Todo
#ToTag #ToLink 
- - -
Prequisitos: 
- Curso de VirtualBox (Virtualizacion 0)
- Curso de  Vim (opcional pero vendria genial hacerlo antes)
- un ordenador en condiciones
# Linux Fundamentals
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
     - Arch Linux, Manjaro, Slackware, Gentoo
 
 ## File System Hierarchy**
- Key directories (/bin, /etc, /var, /home, /usr, /tmp, /proc, /sys)
- File types (regular, directory, symbolic links, device files, blocks)

# Bash Interpreter
GNU Bash o simplemente Bash (Bourne-again shell) es una interfaz de usuario de línea de comandos popular, específicamente un shell de Unix; así como un lenguaje de scripting. 
## Text Editors
- **vi/vim**: Modes (normal, insert, command), basic commands (`:wq`, `:q!`, `dd`, `yy`, `p`) 
	- --help, -set, sintax, tabs, buffers, registers, macros, marcas y marcas de archivo " m, \` " colorscheme, tutor
 - **nano**: Basic usage (save, exit, search)
 - **emacs**: Basic commands (Ctrl+X, Ctrl+S, Ctrl+C

## [[Atajos de Bash]]
## Programas del sistema I
#### Miscellaneous
tty ->
isthistty ->
date: Display or set the system date and time
cal: Display a calendar
bc -> calculadora
reboot:
shutdown: Shutdown or reboot the system
####  Documentation Access
- [[Buildtin vs Command]]
- Ejercicio de usar el man y explicar que significan los ... y mas detalles

**man**: Manual pages
        Sections: 1 (commands), 2 (system calls), 3 (library functions)
	     man -k keyword: Search manual pages
	     man -f command: Show all available pages
            
**info**: GNU documentation
	More detailed than man pages
    Hypertext format
    Navigation: n (next), p (previous), u (up)
            
**--help**: Quick reference for commands
    Available for most GNU utilities
    Shows common options and usage
            
#### 📂 Manipulación de archivos y directorios
- [[Rutas en Linux]]
- Ejercicio para listar las rutas de los manuales
- [[Globbing]]:  

ls → Lista archivos y directorios
	options: -R, -l , -i, -a, -d, t
cd → Cambia de directorio
	options:  "- , ~, /"
pwd → Muestra la ruta del directorio actual
mkdir → Crea un directorio
	-p
rmdir → Elimina un directorio vacío
rm → Elimina un directorio con contenido
	-f, -r, -i
cp → Copia archivos o directorios
	-r
mv → Mueve o renombra archivos
ln  -> thace enlaces
	options: -s ,
#### 📝 Visualización y 🔍 Analisis de archivos
- [[Curso Linux - Lab - Examen exhaustivo de archivos de sistema]]
- Ejercicio con printf sobre el ascci hexadecimanl octal binario etc..

cat → Muestra el contenido de un archivo
	-E
tac → Muestra el contenido de un archivo en orden inverso
tee → Redirige salida a un archivo y a la vez la muestra en pantalla
less → Visualiza archivos de texto
head → Muestra las primeras líneas de un archivo
	-n
tail → Muestra las últimas líneas de un archivo
	-n
echo -> 
printf -> 
touch -> Change file timestamps
stat -> Muestra el estado del archivo
file → Determina el tipo de archivo
diff → Compara archivos línea por línea
diff3 → Compara tres archivos y muestra diferencias
patch → Aplica diferencias a archivos

#### Historial de comandos
- bash_history

 history -> display cmd hisotry
	!n: Execute nth command from history
	!-n: 
	!!: Repeat the last command
	!string: Execute the most recent command starting with string
	Ctrl+R: Search command history interactively
- - -
## How Sentences Are Made
#### [[Secuencias de Escape en Caracteres]]
#### Sentences: Basic units of execution
- <infile cmd1 operador cmd2 > outfile
- Binary Operators "&&, ||, ;, |"
- [[Redirecciones en Unix-Linux]]
#### Expansiones
Pathname expansion:
Tilde Expansion: \`date\`
Arithmetic Expansion: $()  --> Append: expr
[[Expansión de Llaves]]: {a,b,c} {a..c}
Parameter Expansion: $var 
#### Command susbtitution "<(), double qutes, $() "
- ejercicio con variables de entorno y env -i para demostras esto
- ejecucion de comandos exec y eval
#### quoting 
- single quote
- double quote
- invertida quote (deprecated)

### Muchisimos ejercicios sobre lo visto hasta ahora
- - - 
## Programas del sistema II
#### Variable managment
env: Display environment variables
printenv ->
locale ->
set: Set or display shell options and positional parameters
unset: unset or display shell enviroments
export: Set environment variables
	option: -p
source: Execute commands from a file
alias: Create command aliases
unalias: Remove command aliases
exit: Exit the shell
#### Selección y Sustituciónde Texto
- Buscar los ejercicios del sepe

tr → Sustituye o elimina caracteres
	-d, -s, -t
paste → Une líneas de archivos
join → Une líneas de archivos basadas en un campo común
split → Divide archivos en partes más pequeñas
cut → Extrae secciones de líneas en archivos
	-d, -f
column → Formatea texto en columnas
strings → Extrae cadenas imprimibles de archivos binarios
#### Filtrado de texto
- [[Chuleta_Regex_apuntes.jpg]]
	Tools: grep, sed, awk, find(en algunas distros, ademas en algunas se puede poner la flag -regex)
- [[Curso de Linux - Ejercicio - Regex]] y buscar mas ejercicios del sepe

sort → Ordena líneas de un archivo
	-n
uniq → Filtra líneas duplicadas
wc → Cuenta líneas, palabras y caracteres en un archivo
	-c, -w, -l
grep -> filtrado
	-E, -i, -n, v, -f, -r
sed → Procesamiento y edición de texto.
	s/OldPattern/NewPattern/(g)   / puede ser cambiado por otro caracter, necesario si en el patron aparece el delimitador.
awk → Procesamiento de texto avanzado.
#### Searching Files
- Lab: buscar muchos archivos del sistema

locate / updatedb  → Find files by name / Actualiza la base de datos de locate
find: Search for files in a directory hierarchy
	exec "+ , /"
	lots of flags
xargs: Build and execute command lines from standard input
#### Compression and Sync
- mirar el ejercicio de christine

gzip -> Compress files
bzip2  -> Compress files
xz -> Compress files
tar -> Archive files
cpio -> Copy files to and from archives
rsync: Sync files/directories
shasum

- - - 

==Espacio para explicar cosas del sistema desde demonios hasta probablemente conectarse al wifi o yo que se.==
## manejar mi enviroment
 - [[Curso Linux - Lab - Explorando Las Variables de Bash]]
 
[[Variables de Bash]] 
 Archivos de configuracion bashrc y profile
	 - .bash_profile 
	 - .bashrc 
	 - .bash_logout 
	 - .bash_history
- - -
## Programas del sistema III
#### 🔒 Gestión de usuarios 
[[Curso Linux - Lab - Gestión de Usuarios y Permisos]]
- root # vs regular user $
- Archivos: /etc/passwd /etc/shadow /etc/skel
- sudoer
- privilegios del usuario instalador
- User and Group ID Numbering Conventions 

su → Cambia de usuario pero no de enviroment
	-l/ --login, - : para ejecutar una shell como root, es decir con su enviroment
sudo → Ejecuta comandos como root
	-u
whoami → Muestra el usuario actual
who → Muestra usuarios conectados
id → Muestra UID y GID del usuario actual
	options: -u, -n
groups → Muestra grupos de un usuario
	options: -u, -n
(add/del)user → Crea/Elimina  un nuevo usuario (diferencia con useradd)
usermod→ 
	-a, -G
(add/del)group→ Crea/Elimina un nuevo usuario (diferencia con useradd)
groupmod → 
chage ->
mask -> restar
umask → Configura permisos por defecto
#### 🔒 Gestión de permisos 
mirar laboratorio del sepe
- permisos Linux - Unix
- [[Permisos Especiales Unix-Linix]]
- “a(all), u(user), g(group), o(other)”
-  symbolic   vs octal  0xxxx

su → Cambia de usuario pero no de enviroment
	- : para el enviroment del argumento
sudo → Ejecuta comandos como root
	-u
whoami → Muestra el usuario actual
who → Muestra usuarios conectados
id → Muestra UID y GID del usuario actual
groups → Muestra grupos de un usuario
(add/del)user → Crea/Elimina  un nuevo usuario (diferencia con useradd)
usermod→ 
	-a, -G
(add/del)group→ Crea/Elimina un nuevo usuario (diferencia con useradd)
groupmod → 
passwd → Cambia contraseña de usuario
chmod → Cambia permisos de archivos
	 06777 , -w ,  u:x  
chown → Cambia propietario de un archivo
chgrp → Cambia grupo de un archivo
#### 🛠 Gestión de procesos y señales

- ejercicios en 64.Maniging process priority
- Multiplexores
	- screen 
	- tmux
- [[Procesos en Linux]]
- cmd **&** para el background
- zombies
ps → Lista procesos activos
	a, u, x, e, l , f
	si la tty= ? es un proceso de red
	las 3 sintaxis , unix, bekerley, GNU
pgrep
	-u, -a, -t
bg → Envía un proceso en segundo plano
fg → Devuelve un proceso a primer plano
jobs → Lista procesos en segundo plano
	options -->  -l
	ejercicio con sleep y moverlo del frnt al back y al front otra vez.
	y luego ejecutas un sleep en el background y lo pasas al fore
top → Muestra procesos en tiempo real
	en la parte de arriba se muestran las medias
kill → Termina un proceso por PID
	options: -s, %
	- tabla de señales
	- ejercicios de cristine 63. sending signals to process
killall → Termina procesos por nombre(sigterm)
pkill → Termina procesos por coincidencia de nombre
	options -a, -g
nice  -> Run process priority
- nice level, priority on linux, ranges 
renice: Change process priority
w -> Show who is logged in and what they are doing
uptime: Show system uptime
sleep: Delay for a specified time
at: Schedule a command to run at a specific time
nohup: Run a command immune to hangups
#### ⏳ Gestión de memoria y rendimiento
- [[Paquete - Sysstat]]
- ejercicio de usar cut y grep en archivos del sistema para imitar comandos de esta paquete (hacerlo antes de ver los comandos) ejemp imitar sar con cut grep y top
free  → Muestra uso de memoria
vmstat → Información sobre CPU, memoria, swap
iostat → Estadísticas de CPU y discos
uptime → Muestra tiempo encendido del sistema
dstat → Alternativa a vmstat
sar → Registra uso de CPU y memoria
####  Partitions and Disks
dd: Convert and copy files
df: Display disk space usage
gparted: Partition editor
mount: Mount a filesystem
umount: Unmount a filesystem
fsck: Check and repair a filesystem
fdisk: Partition table manipulator
mkfs: Create a filesystem
genisoimage: Create ISO files
whodid: Check file ownership
md5sum: Compute and check MD5 message digest
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
- Networkctl
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
#### 📡 Redes y conectividad ([[Paquete - Sysstat]])
ip  → Herramienta compleja para redes
	-a, -r
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
## Exercises to add
- Agregar binarios al path

- - - 
## ***Sources:***