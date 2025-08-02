**MetaTags:** #_done 
 **Tags:** #linux #bash #tolink 
- - -
Son variables accesibles desde cualquier proceso en la sesión del usuario y pueden heredarse a procesos hijos.

Para ver todas las variables de entorno actuales, usan:
```bash
printenv
env
```

🔹 **Todas las variables de entorno también son globales, pero no todas las globales son de entorno** (si no han sido exportadas).  
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

- - - 
## ***Sources:***