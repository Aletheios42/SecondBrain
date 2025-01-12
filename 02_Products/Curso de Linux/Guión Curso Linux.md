**Tags:** #_Todo
#Udemy #Linux  
- - -
 - recompilar los  pdf de las secciones para hacer el mio propio
 - copiar los quizz para hacer anki notes
# Secion 0 Instalacion
## Paso 1: virtual box
Instalar ubuntu 18 y centos 7,
aprender a usar control right, 
enseñar la diferencia entre save y snapshot
# Seccion 1. Explorar el entornor Linux
## Paso 0: Explicar que es un kernel y que es una distribucion
- explicar las familias de linux, las 3 principales y tocar arch
- uname (flags como -r, -s, - v, -a)
## Paso 1: tty
- navegamos por las tty y enseño los comandos tty , whoiam y 
## Paso 2:  comandos para navegacion por el sistema de archivos y algunos cmd
 - pwd ,ls(-a, -F, -d, -l,-R,-h,-s, -o, ls-i), cd( 4 formas de ir a /home, rutas relativas y absolutas,  algunos place holders como:  ".." "." "- " "~ "))
- Miscelanea: bc, date, cal
## Paso 3 Sistema de archivos de linux
- explicar que es un sistema de archivos virtual,
- el Filesystem Herraky standr (FHS) y navegar por elllas mientras se explica

# Seccion 2 CLI 
## Paso 1  Que es un CLI, bash y sus atajos 
- explicar que es un CLI, introducir bash
- env y exit
## paso 2 Informacion
 - type(comadno externo, builting alias... investigar clasificacion), which, man, info,  help whereis
 - enseñar que como se presentan las opciones de los comando en los manueales por ejemplo si viene con ountos susppensivos etc
  ## Paso 3:  atajos de bash
- [[Atajos de Bash| explicar los shortcouts de bash]]
- shell globbins \*(al principio que empieze, al final que acabe y envuelto que contenga) , ?(cualquier letra, pero tiene que haber algo), \[char1, char2...], \[a-Z] toadas las letras, \[1..4], \*\* recursive, \[ ! or ^\] que no aparezcan esos patrones.
## paso 4 consifguracion de bash
- bashrc
- source
- alias, unalias
## Paso 5 historial 
- .bash_history y diferencia con  cmd history (flag -w, -c) 
- navegar con las flechas
- uso de ! y !!
# Seccion 3 archivos y texto

## Paso 0 creacion, manipulacion y eliminacion
- mkdir(-p), touch(-m), echo, rm(-i, -r/R, -f), cp(-i, -r), mv(-i), file, stat
## paso 1 Enseñar por pantalla
- cat head , tail, less(h to see all options), 
## Paso 2: extraer informacion de los archivos 
- wc,  uniq(-c, -d, -D),  nl(interaccion con las lineas en blanco), tee, diff, grep
## Paso 3 hashear files
- explicar que es un [[Hash]]  (tener en cuenta que no diferencia mayusculas y minusculas)
-  md5sum (legacy)
- sha2 family y   sha256sum (modern standard) y sha12sum
## paso 4 manipular y buscar texto
- sort(-n para numeros) , paste,  join, split, cut
- tr, odd
- sed
## ejercicios
- hacer laboratorio 
# Seccion 4 Variables , Regular expresions y busqueda de archivos
## paso 0 variables y expansiones
- variables en bash, export
- expansiones ,  
- comillas dobles, simple, y acento invertido
## paso 1 sustitucion y subshell
- sustitucion $((expresion))
- susbshell \[expresion] , \`expresion\`
## paso 2 Regex
- caracteres especiales, \
- cheatcheet  con todo la pesca
## paso 3 ejercicios
- regular expresions exersices
## paso 4 encontrar archivos
- locate, updatedb, mlocate.db
- find 
## Ejercicios
- hacer laboratiorio

# Seccion 5 comandos y operadores y fd
 ## paso 0 que es un comando 
 - que es un comando su sintaxis, infile < cmd -options arguments > outfile
 - PATH
 ## paso 1 filedescriptors and its types
- filedescriptors(explicar los tipos de objectos, enlace , bloque, directorio etc..), stdin, out err, /dev/null
- ln (-s) enclace duro/simbolico
## paso 2 redicrecciones y pipe
- redirecciones con todo
## paso 3 operadores binarios
- operadores
- xargs
## ejercicos 
- Ejercicos para practicar

# Seccion 6 Compresion, archivacion  y sincronizacion
## paso1  Compresion , descompresion y lectura
- para comprimir por ratio de compresion ascendete, gzip, bizp2, xz
- para descomprimir gunzip, bunzip2, unxz
- hacer ejercicio comprimiendo el mism archivo con esto y comprobar el size
- se puede revisar el tipo de compresion con el comando file
- zcat,bzcat, xzcat 
-  listar las extensiones
## paso 2 Empaquetacion / archivador
- tar(-c, -u,-v,-f, -d,-t,-w, -x, -O)
- tarball, compresion de paquetes tar con (-j /--bizp2, -J / --xz, -z / gzip)
- cpio(-o, -v, -i, -t, -I, --no-obsolute-filename)
- listar las extensiones
## paso 3 formater
- dd , lsblk

# Seccion 7 edicion de texto: VIM

## Paso0 modo normar o modo comando
- w, q, a, :!
## Paso1 modo insertar
- i, I, a, A, o, O
## Paso 2 modo visual
- v, V, ctrl+v
- momements:  hjkl,
- ^, 0 , $, w, e, b, d, x, . ,  numeros
- r
## Paso 3 avanzado
- macros 
- registros
- buffers
- marks
# Seccion 8 Permisos
## Paso 0 superuser
- cambiar a root , # vs $ en el promt
- sudo, su, sudoer
- cambiar el archivo de configuracion para que no te pida el sudo cuando have apt
## paso 1 consultar permisios
- explicar la filosofia de unix de multiser system,  se crea un grupo con el mismo nombre que tu usuario el cual se convierte en tu grupo primario
-  id(-G, -g,-n),groups
- default-group-owner, rwx como octal, (simbolic, u-g-o-a)
## paso 2 Cambiar los permisos
- chmod, chown , chgrp, 
- id, mask umask
- permisos especiales SUID(u+s), SGID(g+s), sticky bit(o+t) revisar el octal de todos
## paso 3 agregar usuarios y grupos
- addusr
## paso 4 ejercicios
- explicar ligeramente os scripts para hacer estos ejercicios
- - - 
diseñar un canvas de unix/linux.
[[Ejercicios de Bash Scripting]]
- - - 
## ***Sources:***
