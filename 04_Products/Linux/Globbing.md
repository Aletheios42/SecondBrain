**MetaTags:** #_Done
**Tags:** #Linux   #Bash  
- - -
 Es un lenguaje de marcado simple. Especificar grupos de nombres de archivo de forma rápida y eficiente. . Los **wildcards**  permiten seleccionar archivos o directorios basados en patrones de caracteres.
 
  Estos patrones se pueden usar con cualquier comando que acepte nombres de archivo como argumentos, permitiendo construir criterios de selección sofisticados.
 los wildcards se expanden en order "sort" 
 
  ![[Chuleta_Globbing_Apuntes.jpg]]

El patrón `**/` o `**` es conocido como "globstar" y es un patrón de coincidencia recursiva,
- `**` coincide con todos los directorios y subdirectorios recursivamente
- `**/` coincide específicamente con directorios de forma recursiva


 Por defecto NO está activado en Bash. Hay que habilitarlo con:
```bash
shopt -s globstar
```


table of all POSIX character classes:

| Character Class | Description                          | Example Matches         |
| --------------- | ------------------------------------ | ----------------------- |
| `[[:upper:]]`   | Uppercase letters A-Z                | A, B, C, Z              |
| `[[:lower:]]`   | Lowercase letters a-z                | a, b, c, z              |
| `[[:alpha:]]`   | Alphabetic characters [a-zA-Z]       | a, B, c, Z              |
| `[[:digit:]]`   | Digits 0-9                           | 0, 1, 2, 9              |
| `[[:alnum:]]`   | Alphanumeric characters [a-zA-Z0-9]  | a, B, 1, 5              |
| `[[:space:]]`   | Whitespace (space, tab, newline)     | ' ', '\t', '\n'         |
| `[[:blank:]]`   | Space and tab characters only        | ' ', '\t'               |
| `[[:punct:]]`   | Punctuation characters               | !, @, #, $, %, etc.     |
| `[[:graph:]]`   | Visible characters (no space)        | Any visible char        |
| `[[:print:]]`   | Visible characters (including space) | Any printable char      |
| `[[:cntrl:]]`   | Control characters                   | \n, \r, \t, etc.        |
| `[[:xdigit:]]`  | Hexadecimal digits                   | 0-9, a-f, A-F           |
| `[[:ascii:]]`   | ASCII characters                     | All ASCII chars (0-127) |
- - - 
## ***Sources:***