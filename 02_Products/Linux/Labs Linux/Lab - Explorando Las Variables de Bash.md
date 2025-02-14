**Tags:** #Linux 
#Linux #Bash  #ToLink 
- - -
## **Parte 1: Variables de Entorno vs. Variables Locales**  
### 🔍 **Ejercicio 1: Listar las variables de entorno**  

Ejecuta el siguiente comando en tu terminal y responde:  
```bash
env | less
```
**Preguntas:**  
1. ¿Cuántas variables aproximadamente se muestran?  
2. ¿Aparecen variables como `PATH`, `HOME`, `USER`?  
3. ¿Ves alguna variable con tu nombre de usuario o configuración del sistema?  

Ahora, ejecuta:  
```bash
printenv | less
```
4. ¿Las salidas de `env` y `printenv` son iguales?  
5. ¿Qué tipo de variables aparecen aquí?  
## **Parte 2: Diferencia entre Variables de Bash y de Entorno**  
### 🔍 **Ejercicio 2: Usando `declare` y `set`**  

Ejecuta estos comandos:  
```bash
declare -p | less
set | less
```
 **Preguntas:**  
1. ¿Cuál de los dos (`declare -p` o `set`) muestra más información?  
2. ¿Encuentras variables que no estaban en `env` o `printenv`?  
3. ¿Se muestran funciones, alias u otras configuraciones en `set`?  

Ahora ejecuta este comando para **ver solo las variables exportadas (de entorno):**  
```bash
export -p | less
```
4. ¿Esta salida se parece más a `env` o a `declare -p`?  
5. ¿Qué significa el prefijo `declare -x` en algunas líneas?  
## ** Parte 3: Explorando Variables de Localización**  
### 🔍 **Ejercicio 3: Usando `locale`**  

Ejecuta:  
```bash
locale
```
 **Preguntas:**  
1. ¿Qué tipo de información muestran estas variables?  
2. ¿Cómo se diferencian de las que viste en `env`?  
3. ¿Cómo crees que afecta `LANG` o `LC_TIME` a tu sistema?  
## **Parte 4: Comparación Avanzada**  
### 🔍 **Ejercicio 4: Usando `diff` para encontrar diferencias**  

Ejecuta:  
```bash
diff <(export -p) <(printenv)
```
**Preguntas:**  
1. ¿Qué variables aparecen en `export -p` pero no en `printenv`?  
2. ¿Por qué crees que existen estas diferencias?  
3. ¿Cómo podrías comprobar si estas variables son específicas de Bash?  

## **Ejercicio Extra**  

Crea una variable local y de entorno para comprobar su visibilidad en diferentes comandos:  
```bash
var_local="Hola Local"
export var_global="Hola Entorno"
```

Ahora ejecuta estos comandos:  
```bash
env | grep var_
printenv | grep var_
declare -p | grep var_
set | grep var_
```
¿En qué comandos aparece cada variable? ¿Qué diferencias encuentras?  

## **Reflexión Final**  
- ¿Qué diferencia hay entre `env`, `printenv`, `declare`, `set` y `locale`?  
- ¿Cómo se relacionan las variables locales con las de entorno?  
- ¿Cómo influye Bash en la gestión de variables?  
- - - 
## ***Sources:***