**Tags:** #_Todo
#ToTag #ToLink 
- - -
es un superset de javascript agrega una capa de tipado fuerte y  se transpila con el comando tsc.

# Instalar typescript
==Hacer de esto una nota==
por proyecto:
``` npx
npm install typescript
```
para correr el compilador
``` npx
npx tsc
```
en el sistema:

aunque falle la transpilacion te da output de javascript
typescript no corre en el navegador

# Tipos de variabes
Asignaciones una o 2 lineas
- ==No se si hay problemas con la declaracion del mismo nombre en la variable, falla o hace shadow==
- Base vs primitive types
- primitivos(pedirle al chatgpt un listado, con su sintaxis)
- Number vs number como tipos
- Asignar a null te hace const(mejorar esta linea)
- arrays
- Objetos - Hacer declarar nu array de objetos
- Type inference
- Uniones
- aliases type (nativo typescript)
- Generics
- \[value, ...array] que es estoy?
- \<T> Marcado de typescrip , typesafe yet flexible.. ==revisar==
- private vs public
 
# Funciones
- Se puede asignar tipos a los parametros hay tres tipos de declaracion de funciones
- Typescript es capaz de hacer inferencia en el tipo del return
- any
- Problemas con los conflictos de nombres
# Classes
- Herencia
- metodos
- scoopes
- contructor
- this
# Interfaces
nativas de typesscript
-  son alternativas a l \<T>
- fuerzan a las clases a tener cierto formato
# Compilador
archivo de configuracion tsconfig.json
- modo estricto
- - - 
## ***Sources:***
- [Typescript Oficial site](https://www.typescriptlang.org/docs/)