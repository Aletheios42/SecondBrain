**Tags:** #_Todo
#ToTag #ToLink 
- - -
# Ejercicio 1
Explicar la diferenca entre:
 ``` bash
 diff <(ls *) <(ls )
 diff $(ls *) $(ls )
 diff "\$(ls *)" "\$(ls )"
 ```
# Ejercicio 2
Explicar 
 ``` bash
 diff3 \ 
 $(diff <(ls *) <(ls))  $(diff $(ls *) $(ls))  $(diff "\$(ls *)" "$(ls )") \
"$(diff <(ls *) <(ls))"  "$(diff $(ls *) $(ls))"  "$(diff "\$(ls *)" "$(ls )")" \
<(diff <(ls *) <(ls))  <(diff $(ls *) $(ls))  <(diff "\$(ls *)" "$(ls )")
 ```
- - - 
## ***Sources:***