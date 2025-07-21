**Tags:** #_Todo
#ToTag #ToLink 
- - -
puedes pipear cosas a  zathura.

manexplain.sh:
``` bash
man -k . | dmenu -l 30 | awk `{print $1}` | xargs -r man -Tpdf
``` 
para obtener los manuales en pdf

para editar:

https://www.sejda.com/compress-pdf
- - - 
## ***Sources:***