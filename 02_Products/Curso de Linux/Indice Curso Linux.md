**Tags:** #_Todo
#ToTag #ToLink 
- - -

# **1. Linux Fundamentals**
- ## 1.1. Linux Architecture

- **1.1. Linux Architecture**
    - Kernel (monolithic vs microkernel)
    - Shell (Bash, Zsh, Fish) vs terminal
    - User Space (GNU tools, libraries)
    - **TTY**: Terminal types (`tty`, `pts`, `/dev/tty*`)
    - **uname**: Display system information (`uname -a`, `uname -r`, `uname -m`)

- **1.2. Linux Families**
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
            
- **1.3. Text Editors**
    - **vi/vim**: Modes (normal, insert, command), basic commands (`:wq`, `:q!`, `dd`, `yy`, `p`)
    - **nano**: Basic usage (save, exit, search)
    - **emacs**: Basic commands (Ctrl+X, Ctrl+S, Ctrl+C)

- 1.4 Multiplexores
	- screen 
	- tmux
- **1.5. File System Hierarchy**
    - Key directories (/bin, /etc, /var, /home, /usr, /tmp, /proc, /sys)
    - File types (regular, directory, symbolic links, device files, blocks)



# 2. Bash Interpreter

GNU Bash o simplemente Bash (Bourne-again shell) es una interfaz de usuario de línea de comandos popular, específicamente un shell de Unix; así como un lenguaje de scripting. 
### Atajos
### Archivos de configuracion bashrc y profile

### expansiones
pathname expansion:
Tilde Expansion:
Arithmetic Expansion: $()  --> Append: expr
Brace expansion: {a,b,c} {a..c}
Parameter Expansion: $ 

### Command susbtitution "<(), double qutes, $() "
### quoting 

### backlashing/scaping characters
Backslash
Escape	Se expande a...
\b	Un carácter de retroceso
\e	Un carácter de escape
\f	Un carácter de alimentación de línea (form feed)
\n	Un carácter de nueva línea
\r	Un carácter de retorno de carro
\t	Un tabulador horizontal
\v	Un tabulador vertical
\\	Un carácter contrabarra
\'	Un carácter de comilla simple
\nnn	El carácter de 8 bits cuyo valor es el número octal nnn (de uno a tres dígitos)
\xHH	El carácter de 8 bits cuyo valor es el número hexadecimal HH (uno o dos dígitos hexadecimales)
\cx	Un carácter control-X

## manejar mi enviroment
 - [[]]
 [[Variables de entorno Bash]] (pegar viñeta) 63. Understanding Environment Variables. se pueden ver en env.
 
 bash files:  .bash_profile .bashrc .bash_logout .bash_history
## Comandos  y buildtins (Programas del sistema)
####  Documentation Access
- [[Buildtin vs Command]]

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
- Absolute vs Relative Paths:
- Ejercicio para listar las rutas de los manuales

ls → Lista archivos y directorios
	-R, -l , -i, -a, -d, t
cd → Cambia de directorio
	- "- , ~, /"
pwd → Muestra la ruta del directorio actual
mkdir → Crea un directorio
	-p
rmdir → Elimina un directorio vacío
rm → Elimina un directorio con contenido
	-f, -r
cp → Copia archivos o directorios
	-r
mv → Mueve o renombra archivos
touch -> Change file timestamps
stat -> Muestra el estado del archivo

#### 📝 Visualización y edición de archivos
- lab:  leer archivos del sistema
- Globbing:  Filename expansion and pattern matching
		clases de caracteres \[:upper\]
		recursividad: ls -R

cat → Muestra el contenido de un archivo
	-E
tac → Muestra el contenido de un archivo en orden inverso
tee → Redirige salida a un archivo y a la vez la muestra en pantalla
less → Visualiza archivos de texto
head → Muestra las primeras líneas de un archivo
	-n
tail → Muestra las últimas líneas de un archivo
	-n

#### 🔍 Exploración del Sistema
- lab hacer file a unas cuantas cosas

file → Determina el tipo de archivo
diff → Compara archivos línea por línea
diff3 → Compara tres archivos y muestra diferencias
patch → Aplica diferencias a archivos

#### bash_History
archivo d econfiguracion: bash_history
history: View command history
!n: Execute nth command from history
!-n: 
!!: Repeat the last command
!string: Execute the most recent command starting with string
Ctrl+R: Search command history interactively
#### Edición de Texto
- buscar los ejercicios del sepe

tr → Sustituye o elimina caracteres
	-d, -s, -t
paste → Une líneas de archivos
join → Une líneas de archivos basadas en un campo común
split → Divide archivos en partes más pequeñas
cut → Extrae secciones de líneas en archivos
	-d, -f
column → Formatea texto en columnas
strings → Extrae cadenas imprimibles de archivos binarios
#### Procesamiento y filtrado de texto
- Regular Expressions (Regex)
	Tools: grep, sed, awk, find(en algunas distros, ademas en algunas se puede poner la flag -regex)
	Common regex patterns:
		. (any character), * (zero or more), + (one or more), ? (zero or one)
		^ (start of line), $ (end of line), [] (character set), () (grouping).
- How Sentences Are Made
		Commands: Basic units of execution(<infile cmd1 operador cmd2 > outfile) Binary Operators: Combine commands (&&, ||, ;, |)
		[[Redirecciones en Unix-Linux]]
- [[REGEX]] y buscar mas ejercicios del sepe

sort → Ordena líneas de un archivo
	-n
uniq → Filtra líneas duplicadas
wc → Cuenta líneas, palabras y caracteres en un archivo
	-c, -w, -l
grep -> filtrado
	-E, -i, -n, v, -f
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
#### Variable managment
env: Display environment variables
set: Set or display shell options and positional parameters
unset: unset or display shell enviroments
export: Set environment variables
source: Execute commands from a file
alias: Create command aliases
unalias: Remove command aliases
exit: Exit the shell

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

#### 🔒 Gestión de usuarios 
[[Lab - Gestión de Usuarios y Permisos]]
- root # vs regular user  $
- Archivos: /etc/passwd /etc/shadow /etc/skel
- sudoer
- privilegios del usuario instalador
- User and Group ID Numbering Conventions 

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
- [[Procesos en Linux]]
- & para el background
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
nice  -> priority
- nice level, priority on linux, ranges 
- ejercicios en 64.Maniging process priority
renice: Change process priority

w: Show who is logged in and what they are doing
uptime: Show system uptime
sleep: Delay for a specified time
at: Schedule a command to run at a specific time
nohup: Run a command immune to hangups
#### ⏳ Gestión de memoria y rendimiento
free  → Muestra uso de memoria
vmstat → Información sobre CPU, memoria, swap
iostat → Estadísticas de CPU y discos
uptime → Muestra tiempo encendido del sistema
dstat → Alternativa a vmstat
sar → Registra uso de CPU y memoria
#### Miscellaneous
date: Display or set the system date and time
cal: Display a calendar
script: Make a typescript of a terminal session
bc -> calculadora
history ->
tty ->
shutdown: Shutdown or reboot the system
reboot:





# Bash Scripting

2.5.1. Shell Scripting Basics


Shebang: #!/bin/bash, #!/usr/bin/env bash
Variables: Declaration, usage, scope
Local vs Global Variables:
Local: Defined within a function
Global: Accessible throughout the script
Arguments: $1, $2, $@, $#, $*, $_
Placeholders: $?, \$\$, \$!

2.5.2. Conditionals

Test: test, [ ], [[ ]]

File tests (-f, -d, -r)

String comparisons (=, !=, -z, -n)

Numeric comparisons (-eq, -ne, -gt, -lt)

if-else: Syntax and examples

case: Syntax and examples

2.5.3. Loops

for: Syntax and examples

while: Syntax and examples

until: Syntax and examples

2.5.4. Functions

Definition and usage
Arguments and return values
.bashrc

2.6.5. Advanced Scripting

Arrays: Declaration, iteration, manipulation
Input/Output: read, echo, printf
Error Handling: set -e, trap, exit codes
	
bash-Macros: EJ: IFS

# Miscelanea
- pruning . mantenere limio el sistema

- There are two files that an administrator can use to limit access to any
daemon: /etc/hosts.allow and /etc/hosts.deny.

- /etc/ssh/sshd_config

- - - 
## ***Sources:***