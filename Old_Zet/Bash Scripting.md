**MetaTags:** #_Todo
**Tags:** #Desarrollo  #Bash
- - -

## el shebang
#!/usr/bin/env interprete
el interprete puede ser bash python perl node...
en general cualquier lenguaje de scripting

## buenas practicas 

Se puede ejecutar un script de las siguientes maneras
probar con este script para demostrarlo
``` bash
#!/usr/bin/env bash

echo $SHLVL
```
### corren en una subshell (aislan el entorno)
1 por su ruta absoluta
2 añadiendo al path y llamandolo
3 bash "script"

### Corren en la misma shell (ahorran recursos)
4 source "script"
5 . "script"
6 exec "script"

test
seq comands
for in

contorl de flujo:
if, then, elif, else, fi,
for , for in, while, until


read 
parametros posicionales y especiales
 hay 3 tipos de expansiones

- $(sentencia_bash)
- `sentencia_bash`
- <()


ideas para scripts.
calcular el tiempo que falta para el epochalipse(32bits -2038)

### Funcion Shell
hay 2 formas de declarar:
- function exmaple() {code}
- functioname() {code}


diferenciar entres variables locales(set, o simplemente declarar) vs variables de entorno(export)


- - - 
#### ***Sources:***