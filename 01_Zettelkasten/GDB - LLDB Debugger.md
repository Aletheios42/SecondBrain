**Tags:** #_Todo
#ToTag #ToLink 
- - -
==corefiles== https://www.youtube.com/watch?v=3T3ZDquDDVg
## Breakpoints
archivos
(lldb) breakpoint set -f miArchivo.c -l 42
o su abreviacion
b archivo.c:42

funciones
(lldb) breakpoint set -n miFuncion
o su abreviacion:
(lldb) b miFuncion

breakpoint o su abreviacion br
- listas: list / -l
- para poner el br.

(lldb) br delete \<id>
(lldb) br disable \<id>
(lldb) breakpoint enable \<id>

navegacion,
continue
step in 
step over
s ,  n , c

## Print y frame
lo de /x para las instrucciones
frame
libreria tuple de c++ problematica pero util

## Disasemble 
por nombre(facil)
con puntero y size(lioso)
- - - 
## ***Sources:***
- https://lldb.llvm.org/use/tutorial.html
- https://firexfly.com/lldb-cheatsheet/
- https://stackoverflow.com/questions/9707883/gdb-vs-lldb-debuggers
- https://www.youtube.com/watch?v=3T3ZDquDDVg
- https://www.youtube.com/watch?v=MTkDTjdDP3c