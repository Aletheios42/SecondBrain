**MetaTags:** #_Done
**Tags:** #Programación  #ToLink 
- - -

Es un programa cuya salida es el codigo fuente del propio programa. es decir programas autoreplicables.  Tomando el entorno como una funcion, los programas Quine son un   punto invariante y son la materializacion del teorema de recursion de kleene


``` C
#include <stdio.h>

int main() {
    char *s = "#include <stdio.h>%c%cint main() {%c    char *s = %c%s%c;%c    printf(s,10,10,10,34,s,34,10,10);%c    return 0;%c}%c";
    printf(s,10,10,10,34,s,34,10,10);
    return 0;
}
```


- - - 
#### ***Sources:***
-  https://en.wikipedia.org/wiki/Quine_(computing)