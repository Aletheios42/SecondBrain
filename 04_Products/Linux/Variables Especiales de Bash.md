**MetaTags:** #_Done 
**Tags:** #Linux #Bash 
- - -
Son variables integradas que Bash maneja para proporcionar información sobre el shell, los procesos y el estado de ejecución de comandos.  

- **Cómo listarlas**:  
  ```bash
  declare -p | grep -E '\$|@|\*'
  ```

| Variable                       | Descripción                                                                                                               |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| `$?`                           | Estado de salida del último comando ejecutado.                                                                            |
| `$$`                           | PID del shell actual.                                                                                                     |
| `$!`                           | PID del último proceso en segundo plano.                                                                                  |
| `$0`                           | Nombre del script o shell ejecutado.                                                                                      |
| `$#`                           | Número de argumentos pasados al script.                                                                                   |
| `$@` y `$*`                    | Lista de todos los argumentos pasados al script.                                                                          |
| `$1`, `$2`, `$3`, ...          | Primer, segundo, tercer, etc., argumento pasado al script.                                                                |
| `${parameter:-word}`           | Si `parameter` está vacío o no está definido, usa `word`.                                                                 |
| `${parameter:?word}`           | Muestra un error y termina si `parameter` no está definido o es vacío.                                                    |
| `${parameter:+word}`           | Usa `word` si `parameter` está definido.                                                                                  |
| `${!prefix*}`                  | Expande a los nombres de las variables que comienzan con `prefix`.                                                        |
| `${!prefix@}`                  | Expande a las claves de las variables que comienzan con `prefix` (similar a `${!prefix*}` pero en un contexto diferente). |
| `${#prefix}`                   | Longitud de la cadena en la variable `prefix`.                                                                            |
| `${parameter:offset}`          | Extrae una subcadena de `parameter` comenzando desde el índice `offset`.                                                  |
| `${parameter:offset:length}`   | Extrae una subcadena de `parameter` comenzando desde `offset` hasta `length`.                                             |
| `${parameter#pattern}`         | Elimina la parte más corta de `pattern` desde el inicio de `parameter`.                                                   |
| `${parameter##pattern}`        | Elimina la parte más larga de `pattern` desde el inicio de `parameter`.                                                   |
| `${parameter/pattern/string}`  | Sustituye la primera ocurrencia de `pattern` en `parameter` por `string`.                                                 |
| `${parameter//pattern/string}` | Sustituye todas las ocurrencias de `pattern` en `parameter` por `string`.                                                 |
| `${parameter/%pattern/string}` | Sustituye el patrón `pattern` al final de `parameter` por `string`.                                                       |
| `${parameter/#pattern/string}` | Sustituye el patrón `pattern` al inicio de `parameter` por `string`.                                                      |
| `${parameter,,pattern}`        | Convierte todos los caracteres de `parameter` a minúsculas.                                                               |
| `${parameter,pattern}`         | Convierte solo el primer carácter de `parameter` a minúsculas.                                                            |
| `${parameter^^pattern}`        | Convierte todos los caracteres de `parameter` a mayúsculas.                                                               |
| `${parameter^pattern}`         | Convierte solo el primer carácter de `parameter` a mayúsculas.                                                            |
| `base#number`                  | Convierte `number` de base `base` a su valor decimal.                                                                     |
- - - 
## ***Sources:***