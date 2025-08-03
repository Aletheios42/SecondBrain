**MetaTags:** #_Done 
**Tags:** #Linux #Asci #ToLink
- - -
`\r` es un carácter de control que mueve el cursor al inicio de la línea sin avanzar hacia abajo.

El carácter de **retorno de carro** (`\r`) proviene de las antiguas máquinas de escribir y terminales.  

En sistemas modernos:  
- En Windows, se usa junto con `\n` (`\r\n`) para indicar una nueva línea.  
- En Unix/Linux, solo se usa `\n` para representar un salto de línea, por lo que `\r` rara vez es necesario.  
- En algunos protocolos, como HTTP y ciertos formatos de archivos, `\r\n` se usa como separador de líneas.

#### Convertir un archivo de Windows (\r\n) a Linux (\n):
```bash
tr -d '\r' < archivo_windows.txt > archivo_linux.txt
```
#### Convertir un archivo de Linux (\n) a Windows (\r\n):
```bash
tr '\n' '\r\n' < archivo_linux.txt > archivo_windows.txt
```
- - - 
## ***Sources:***