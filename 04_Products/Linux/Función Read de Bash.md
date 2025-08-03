**MetaTags:** #_Done
**Tags:** #Bash #ToLink
- - -
La función read lee desde la entrada estándar (stdin) y asigna el resultado a una o más variables en el entorno actual del shell.

``` bash
echo "hola" | read var
```

No se puede pipear un comando a read, por como funcionan las pipes, estas crean subshells que son procesos hijos de la shell donde se ejecuta la pipe, asi que read no podra cambiar el estado de la shell original pues el hijo no puede cambiar el estado del padre.

Asi que para mandar info a read desde la line ade comandos "<<<" o "here_doc"
``` bash 
read var <<< "hola"
```

o procces substituion.
``` bash
while read var; do
  echo "$var"
done < <(echo "hola")
```

##### Explicacion:
Cuando usas read en una tubería, la asignación ocurre en un subshell, es decir, en otro espacio de procesos (namespace) diferente al del shell padre. Por lo que, **si que se asigno var, pero no en el userespace en el que se encuentra tu proceso bash**

- - - 
## ***Sources:***