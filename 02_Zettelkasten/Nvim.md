**MetaTags:** #_Todo
**Tags:** #Desarrollo  #Editor #Nvim
- - -
### Opciones
:opt te permite seleccionar las opciones de manera manual

vim.opt.tabstop solo formatea al guardar el archivo
vim.opt.shiftwidth controla la identacion y la deidentacion, y si lo seteas a 0 se sincroniza con tabstop

virtualedit es muy interesante tiene varios modos, puede operar cada celda de la pantalla incluso aunque este vacia

stdpath("") , te dice el path de lo que le pongas,

// entender la diferencia entre variables y opciones

metatablas y metadata , makeprg

la funcion   vim.fn.system({ }) ejecuta comandos en una subshell

r lee archivos
r! lee salidas de comandos
:r!cmd | Read shell output: inserta la salida de cmd debajo de la línea actual
:.!cmd | Filter line through cmd: reemplaza la línea actual con la salida de cmd

%s es para todo el archivo
//mirar como se ponen rangos de lineas con subtitute


noh / nohlsearch para apagar el highlight

las funciones que vienes de vim son en minuscula
las que vienen de lua o de los plugins pueden usar cualquier estilo, suelen usar PascalCase o camelCase
para invocar funciones de lua, :lua  //revisa esto
#### Fn vs cmd
Usa vim.fn para obtener información o evaluar funciones que retornan datos.
Usa vim.cmd para emitir comandos y modificar el estado del editor.


##### Insertar texto
- put
- read
- yank
##### Modificar opciones
- set  ?para consultar
- unlet
- let
- echo   y su atajo :=
- :options
## Errores frecuentes
https://www.youtube.com/watch?v=U0TqE__vSno&list=PLx2ksyallYzW4WNYHD9xOFrPRYGlntAft&index=3

cache
rtp --> mira en tu repositorio actual, 


#### tipos de scopes

//poner nombre completos de las tablas
Tipos:
g: global

b: por buffer

w: por ventana

t: por tab

l: local a función

s: local a script

## Arbol lexico
:lua vim.print(vim.treesitter), para ver el arbol lexico del nucleo de treesitter el cual esta instalado por defecto.


por eso el C-n autocompleta sin plugins, porque ya hay un arbol lexico
:TSinstall lenguaje

:Inspecttree

:highlight @decorador     (el decorador tiene que ser un grupo de tu .csm del parser instalado)
## LSP
:lua print(vim.lsp)
para exponer la api nativa de nvim para los LSP
para que funcione correctamente el lsp tiene que iniarse con un autocomand, sino esta cargado el  buffer, no funciona

el plugin lo hace por nosotros solo tenemos que añadir a la funcion  lspconfig.
lspconfig.lenguaje.setup{()} y obviamente tener el cliente instalado con mason

### NeovimEvents y autocomands
### Identacion
se identa con < >
una de las opciones solo vale cunado se guarda el buffer,
-- convierte los espacios en tabs
vim.opt.expandtab = true
vim.opt.tabstop = 4
vim.opt.shiftwidth = 4

#### Habilidadees
insertar la ruta absoluta de un  archivo:
-   :r!find / -name 'clangd' -type f 2>/dev/null


- - - 
#### ***Sources:***
- https://www.youtube.com/watch?v=87AXw9Quy9U&list=PLx2ksyallYzW4WNYHD9xOFrPRYGlntAft