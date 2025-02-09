**Tags:** #_Todo
#ToTag #ToLink 
- - -
==MIrar en mi carperta de mis cursos porque tengo ejercicios de scripting hay y los tengo que pasar a obsidian==
# Ejercicios
Haz un script para copiar un mismo  archivo fuenta a varios archivos destino

sol:
Si tienes tres directorios destino con nombres diferentes, tienes varias opciones:

1. Usando un loop con un array:
```bash
destinos=("directorio1" "directorio2" "directorio3")
for destino in "${destinos[@]}"; do
    cp -r "Curso de Linux"/* "$destino"
done
```

1. También podrías usar xargs con nombres específicos:
==Linkear con el ejercicio de buscar archivos xargs para enriquecer el baul==
```bash
echo "directorio1 directorio2 directorio3" | xargs -n1 -I {} cp -r "Curso de Linux"/* {}
```
# Ejercicio 2 
crea un script que cambie el una palabra por otro en los archivos y directorios de un proyecto:
sol.
``` bash 
find . -depth -name "*Typescript*" | while read -r file; do
    newname=$(echo "$file" | sed 's/Typescript/Html/g')
    mv "$file" "$newname"
done
```
- - - 
## ***Sources:***