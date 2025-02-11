**Tags:** #_Done 
#Linux  #ToLink 
- - -
### 📌 **Definir una Variable Local en una Función**
```bash
mi_funcion() {
    local MI_VAR="Soy local"
    echo "$MI_VAR"
}
mi_funcion
echo "$MI_VAR"  # No mostrará nada, porque MI_VAR es local a la función
```

### 📌 **Definir una Variable Global (de entorno)**
```bash
MI_VAR="Soy global"
export MI_VAR
echo "$MI_VAR"  # Esto mostrará "Soy global"
# Después de exportarla, estará disponible en otros procesos:
bash -c 'echo $MI_VAR'  # Sigue accesible en procesos hijos
```
### 📌 **Eliminar una Variable**
```bash
unset MI_VAR
```
## 🔹 **Ejemplo Práctico de Variables Locales y Globales**
```bash
#!/bin/bash

GLOBAL_VAR="Soy una variable global"
mi_funcion() {
    local LOCAL_VAR="Soy una variable local"
    echo "Dentro de la función: GLOBAL_VAR=$GLOBAL_VAR, LOCAL_VAR=$LOCAL_VAR"
}

mi_funcion
echo "Fuera de la función: GLOBAL_VAR=$GLOBAL_VAR"
echo "Fuera de la función: LOCAL_VAR=$LOCAL_VAR"  # No se mostrará nada porque es local
```
📌 **Salida esperada:**
```
Dentro de la función: GLOBAL_VAR=Soy una variable global, LOCAL_VAR=Soy una variable local
Fuera de la función: GLOBAL_VAR=Soy una variable global
Fuera de la función: LOCAL_VAR=
```
### 🔹 **Resumen**
| **Comando**          | **Función**                                                          |
| -------------------- | -------------------------------------------------------------------- |
| `export VAR="valor"` | Define una variable global (de entorno) accesible en procesos hijos. |
| `local VAR="valor"`  | Define una variable local dentro de una función.                     |
| `unset VAR`          | Elimina una variable del entorno.                                    |
| `env` o `printenv`   | Lista las variables de entorno (globales).                           |
| `set`                | Lista todas las variables (locales y globales).                      |
- **Variables locales** se crean con `local` dentro de funciones y no afectan el entorno global.
- **Variables globales** (de entorno) se crean con `export` y están disponibles en otros procesos.
- **Las variables sin `local` pero sin `export` son globales solo dentro de la sesión del script.**
- - - 
## ***Sources:***