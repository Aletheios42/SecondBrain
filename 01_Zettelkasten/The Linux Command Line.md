**Tags:** #_Investigar
#Linux #LibroLeido #CLI
- - -
notas para hacer de aqui:
[[Comandos Linux]]
[[Redes]]
[[Terminal]]
[[Expresiones Regulares]]
[[Vim]]
[[Expansión de Llaves{}]]
[[Sustitución de Procesos en Bash]]
[[Arquitectura de Enlaces en Linux]]
[[Bash]]
[[Redirecciones en Unix-Linux]]
[[SSH]]
[[POSIX]]
[[Scripting]]
[[Historial de bash]]
# COMMAND LINE
Terminal:
Es la interfaz (ventana o aplicación) donde se escriben los comandos que la shell ejecuta.

Shell:
Es un programa que interpreta y ejecuta comandos del usuario en el sistema operativo.
El promt del interprete de comandos suele tener las estructura "username@machinename" seguido de pwd y o "\#" en el caso de un superuser priviñedge o "\$" en el caso de un user [me@linuxbox ~]$ 

Command History
If we press the up-arrow key, we will see that the previous command 
reappears after the prompt. This is called command history. Most Linux distributions re-
member the last 1000 commands by default. Press the down-arrow key and the previous
command disappears.

trap-> señales
wait-> asincron
makefifo-makenod, para usar pipes en scripts
# COMMANDS
command -optionsFlag/--fullnameOption arguments

group comands, subshells
{cmd1, cmd2, [cmd3 ....]}
(cmd1, cmd2, [cmd3 ....])
<(cmd)  o >(cmd)
	
	//TODO Buscarles categoria
	date, cal, free, exit, who, whoami, script .

	1. usuarios y permisios: useradd/del,groupadd/del,groupmod.  sudo, su, chmod, chown, chgrp,id  chmod umask passwd,   sed, awk. 
	2. Navigation pwd, cd, ls.
	3. Exploring the System: file, less, diff, comm, diff3, patch, head, tail, sort uniq, psate, join, split, cut,  tr, strings, tee, wc	
	4. Manipulating files and directories: cp,rsync, mv, mkdir, rm, ln, bzip2, (g)zip, tar 
	5. Working with Commands: type, which, help, man, apropos, info, whatis, alias
	6. Processes ps(este se merece una nota), renice, w, top , uptime, fg, bg(&), jobs, sleep, at, kill(este se merece una nota), shutdown.
	7. Particiones y disco. gparted, df, mount.
	8. historial y entorno. history env, set,  export, (un)alias, source.
	9. comandos de red: curl, wget, ping, traceroute, ip, netstat,ftp, ssh.
	10. comandoos de almacenamiento: (u)mount, fsck, fdisk, mkfs, dd, genisoimage, whodim , md5sum.
	11. Busqueda de archivos: locate, find, xargs, touch stat
	12. Formmating output: nl, foldfmt, pr, printf, groff.
# Network Opereation.
es el canal por el que se da la comunicaicon entre ordenadores.
se transfieren paquetes que son datos con headers en los que se especifica quien y aquien se envia la info.
ipaddress, tu dni.
ipv4 32bits into 4 octels, clases, netid hostid.
vs ipv6.
ssh.
# [[Sistema de Permisos en Linux]]
# [[Atajos de Bash]]

![[Shourtcouts_Bash.jpg]]
# Rutas en Linux
Las rutas en Linux se pueden expresar de dos formas: absolutas y relativas.

Ruta absoluta: Comienza desde la raíz (/), por ejemplo: /usr/bin.
Ruta relativa: Comienza desde el directorio actual y utiliza símbolos especiales como . y ...
Nota: En la mayoría de los casos, el ./ puede ser omitido. Por ejemplo, cd bin tiene el mismo efecto que cd ./bin, ya que el sistema asume que estamos refiriéndonos al directorio actual.
Leyenda de símbolos:
/: Directorio raíz (root).
.: Directorio actual.
..: Directorio superior (padre).
~: Directorio home del usuario actual.

Comandos útiles para cambiar de directorio

cd	Cambia al directorio home del usuario actual.
cd -	Cambia al directorio anterior.
cd ~user_name	Cambia al directorio home del usuario user_name. Ejemplo: cd ~bob.
# Nombrar Archivos
En Linux, los archivos tienen algunas particularidades importantes. Los archivos que comienzan con un punto (.) son ocultos y no se muestran con el comando ls a menos que se use ls -a. Los nombres de archivos son sensibles a mayúsculas y minúsculas, lo que significa que "File1" y "file1" son archivos diferentes. A diferencia de otros sistemas, Linux no utiliza extensiones de archivo para determinar su tipo o propósito; esto se basa en otros factores. Aunque Linux permite nombres largos con espacios y puntuación, se recomienda evitar espacios en los nombres de archivos y usar guiones bajos (_) en su lugar. También es mejor limitar los caracteres de puntuación a puntos, guiones y guiones bajos.
// hacer nota sobre expansiones en bash
# quoting
double quote
ej: bash hace split por defecto para evitarlo dobles comillas
``` bash
echo $(cal)
February 2019 Su Mo Tu We Th Fr Sa 1 2 3 4 5 6 7 8 9 10 11 12 13 14
15 16 17 18 19 20 21 22 23 24 25 26 27 28 29
echo "$(cal)"
February 2019
Su Mo Tu We Th Fr Sa
1 2
3 4 5 6 7 8 9
10 11 12 13 14 15 16
17 18 19 20 21 22 23
24 25 26 27 28 29
```

Single Quotes
If we need to suppress all expansions, we use single quotes. Here is a comparison of un-
quoted, double quotes, and single quotes:
[me@linuxbox ~]$ echo text ~/*.txt {a,b} $(echo foo) $((2+2)) $USER
text /home/me/ls-output.txt a b foo 4 me
[me@linuxbox ~]$ echo "text ~/*.txt {a,b} $(echo foo) $((2+2)) $USER"
text ~/*.txt {a,b} foo 4 me
[me@linuxbox ~]$ echo 'text ~/*.txt {a,b} $(echo foo) $((2+2)) $USER'
text ~/*.txt {a,b} $(echo foo) $((2+2)) $USER
As we can see, with each succeeding level of quoting, more and more of the expansions
are suppressed.

Escaping Characters
Sometimes we want to quote only a single character. To do this, we can precede a charac-
ter with a backslash, which in this context is called the escape character. Often this is
done inside double quotes to selectively prevent an expansion.
[me@linuxbox ~]$ echo "The balance for user $USER is: \$5.00"
The balance for user me is: $5.00
para hacer pitar el ordenador:
echo -e "\a"    # El flag -e es necesario para interpretar caracteres especiales
# Linux FILESYSTEM
particiones investigar.
mount y fstab
fat, ext4, brfs, NFS(investigar)
en /boot hay vmlinuz, initramfs, config, system.map

| **Directorio**    | **Descripción**                                                                                                                       |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| **`/dev`**        | Contiene los nodos de dispositivos; "Todo es un archivo", incluyendo dispositivos del sistema.                                        |
| **`/etc`**        | Archivos de configuración del sistema y scripts de inicio. Algunos archivos importantes: `/etc/crontab`, `/etc/fstab`, `/etc/passwd`. |
| **`/home`**       | Directorios personales de los usuarios. Los usuarios solo pueden escribir en su propio directorio.                                    |
| **`/lib`**        | Contiene bibliotecas compartidas necesarias para los programas del sistema. Similar a los archivos DLL en Windows.                    |
| **`/lost+found`** | Usado para la recuperación parcial de archivos tras una corrupción del sistema de archivos. Suele estar vacío.                        |
| **`/media`**      | Contiene puntos de montaje para medios extraíbles, como USBs o CD-ROMs. Se montan automáticamente.                                    |
| **`/mnt`**        | Directorios para montar dispositivos manualmente (en sistemas más antiguos).                                                          |
| **`/opt`**        | Contiene software opcional, generalmente software comercial.                                                                          |
| **`/proc`**       | Sistema de archivos virtual mantenido por el kernel de Linux; proporciona información sobre el sistema.                               |
| **`/root`**       | Directorio home del superusuario (root).                                                                                              |
| **`/sbin`**       | Archivos binarios esenciales para la administración del sistema, generalmente solo accesibles para el root.                           |
| **`/tmp`**        | Directorio para archivos temporales, que se puede limpiar al reiniciar el sistema.                                                    |
| **`/usr`**        | Contiene los programas y archivos de soporte para usuarios regulares.                                                                 |
| **`/usr/bin`**    | Programas ejecutables instalados por la distribución de Linux.                                                                        |
| **`/usr/lib`**    | Bibliotecas compartidas necesarias para los programas en `/usr/bin`.                                                                  |
| **`/usr/local`**  | Directorio para programas no incluidos en la distribución pero instalados por el administrador del sistema.                           |
| **`/usr/sbin`**   | Programas de administración del sistema no esenciales, pero utilizados por el administrador del sistema.                              |
| **`/usr/share`**  | Archivos de datos compartidos como iconos, fondos de pantalla, configuraciones predeterminadas, etc.                                  |
| **`/var`**        | Contiene archivos que cambian frecuentemente como bases de datos, correos de usuarios y archivos de spool.                            |
| **`/var/log`**    | Archivos de registro (logs) que registran la actividad del sistema, importantes para el diagnóstico y seguridad.                      |


# Entorno
Son los datos de configuracion del sistema que pueden ser usados por los programas.
tambien hay variables de terminal, que escribe bash. Al bootear se cargan los startfile(man bash) del sistema y del usuario, las shells heredan las variables de entorno de sus padres. 

# Editores de texto
- [Vim manual](ftp://ftp.vim.org/pub/vim/doc/book/vimbook-OPL.pdf)
- [Tutorial de vim de The Linux Command Linue](http://linuxcommand.org/lc3_adv_vimvigor.php)

# [[Expresiones Regulares]]
Es una notación para reconocer patrones de texto. su estandard se describe en POSIX
Set de carcteres {^ , $, . \[ , \] , \{, \}, -, ?, +, *, (, ), \|, \\}

## Wildcards en la Shell
Los **wildcards** (o comodines) son caracteres especiales que permiten especificar grupos de nombres de archivo de forma rápida y eficiente. Este proceso también se conoce como **globbing**. Los wildcards son herramientas esenciales para trabajar con archivos y directorios en la terminal. los wildcards se expanden en order "sort" 

---
## ¿Qué son los Wildcards? Hacer Nota sobre expresiones regulares

Los wildcards permiten seleccionar archivos o directorios basados en patrones de caracteres. Estos patrones se pueden usar con cualquier comando que acepte nombres de archivo como argumentos, permitiendo construir criterios de selección sofisticados.

---
## Scripting
Se puede cambiar el separador por defecto " " a otro utilizando IFS, tambien existe el OLD_IFS, hacer un programa rollo grademe , para practicar los scripts.
http://tldp.org/LDP/Bash-Beginners-Guide/html/sect_09_02.html
shift, stat
Los argumentos posicionales en bash son:
$0 - Es el nombre del script o shell que se está ejecutando
$1 - Primer argumento
$2 - Segundo argumento
$3 - Tercer argumento
...y así sucesivamente
También hay otros especiales:
$# - Número total de argumentos
$@ - Todos los argumentos como palabras separadas
$* - Todos los argumentos como una sola cadena
${parameter:-word} 
${parameter:?word} 
${parameter:+word} 
${!prefix*}
${!prefix@}
${#prefix}
${parameter:offset}
${parameter:offset:length}
${parameter#pattern}
${parameter##pattern}
${parameter/pattern/string}
${parameter//pattern/string}
${parameter/%pattern/string}
${parameter/#pattern/string}
${parameter,,pattern}
${parameter,pattern}
${parameter^^pattern}
${parameter^pattern}
base#number
bc program
mirar los arrays en bash

## Notas

- Los wildcards son especialmente útiles en comandos como `ls`, `cp`, `mv` y `rm`, entre otros.
- El uso de clases de caracteres (`[[:class:]]`) proporciona una forma avanzada y más precisa de especificar patrones.
- Experimenta con diferentes combinaciones de wildcards para manejar archivos y directorios de manera más eficiente.
## Tabla de wildcards

| **Wildcard**    | **Significado**                                                              |
| --------------- | ---------------------------------------------------------------------------- |
| `*`             | Coincide con **cualquier número de caracteres**.                             |
| `?`             | Coincide con **cualquier carácter individual**.                              |
| `[characters]`  | Coincide con **cualquier carácter dentro del conjunto especificado**.        |
| `[!characters]` | Coincide con **cualquier carácter que no esté en el conjunto especificado**. |
| `[[:class:]]`   | Coincide con **cualquier carácter que pertenezca a la clase especificada**.  |
## Clases de Caracteres Comunes

| **Clase de Caracteres** | **Significado**                                   |
| ----------------------- | ------------------------------------------------- |
| `[:alnum:]`             | Coincide con **cualquier carácter alfanumérico**. |
| `[:alpha:]`             | Coincide con **cualquier carácter alfabético**.   |
| `[:digit:]`             | Coincide con **cualquier dígito** (0-9).          |
| `[:lower:]`             | Coincide con **cualquier letra minúscula**.       |
| `[:upper:]`             | Coincide con **cualquier letra mayúscula**.       |
## Ejemplos de Patrones y Coincidencias

| **Patrón**               | **Coincidencias**                                                                    |
| ------------------------ | ------------------------------------------------------------------------------------ |
| `*`                      | Todos los archivos.                                                                  |
| `g*`                     | Archivos que comienzan con "g".                                                      |
| `b*.txt`                 | Archivos que comienzan con "b", seguidos de cualquier carácter y terminan en ".txt". |
| `Data???`                | Archivos que comienzan con "Data" y tienen exactamente tres caracteres adicionales.  |
| `[abc]*`                 | Archivos que comienzan con "a", "b" o "c".                                           |
| `BACKUP.[0-9][0-9][0-9]` | Archivos que comienzan con "BACKUP." y terminan en exactamente tres números.         |
| `[[:upper:]]*`           | Archivos que comienzan con una letra mayúscula.                                      |
| `[![:digit:]]*`          | Archivos que no comienzan con un número.                                             |
| `*[[:lower:]123]`        | Archivos que terminan con una letra minúscula o con los números "1", "2" o "3".      |

# Datos curiosos
	- GNU (GNU Not Unix) es un acronimo recursivo
	- C compilers eran de pago antes de GNU sacar gcc
	- Sh es la terminal de unix, su creador (Bourne Shell)
	- Bash es una masterizado (Bourne Again SHell)
	- mkdir directory...When three periods follow an argument in the description, it means that the argument can be repeated.
	-man bash displays more than 80 pages
	- La terminal era un aparato fisico. investigar y hacer nota de esto.

/playground en el libro para encontrar los ejercicios.
- - - 
## ***Sources:***
- https://en.wikipedia.org/wiki/Shell_(computing)
- [Curso para Principiantes de Linux](]https://www.youtube.com/watch?v=sWbUDq4S6Y8)
- Shotts, W. (2019). The Linux Command Line: A Complete Introduction. No Starch Press. Chapter 8: Advanced Keyboard Tricks.
- [Artículo sobre Terminales](https://en.wikipedia.org/wiki/Computer_terminal)