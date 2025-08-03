**Tags:** #_Done 
#Git #ToLink 
- - -
# Crea una nueva rama temporal sin historial
git checkout --orphan temp_branch
# Añade todos los archivos actuales (excepto los ignorados)
git add .
# Crea un nuevo commit inicial
git commit -m "Inicio limpio del repositorio"
# Borra la rama master
git branch -D master
# Renombra la rama temporal a master
git branch -m master
# Fuerza el push al repositorio remoto
git push -f origin master
# Volver a establecer la rama remota
git branch --set-upstream-to=origin/master master

- - - 
## ***Sources:***