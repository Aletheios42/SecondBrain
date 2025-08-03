**MetaTags:** #_Done 
**Tags:** #Linux #Bash #ToLink 
- - -
Método de bash que permite usar la salida de un comando como si fuera un archivo temporal es especialmente útil cuando trabajamos con comandos que esperan archivos como argumentos.
### Métodos
\`comando\` - Sustitución de comando secuencial en shell actual (legacy)
$(comando) - Sustitución de comando secuencial en shell actual
${variable} - Expansión de parámetros/variables (no ejecuta comandos)
<(comando) - Sustitución de proceso en subshell paralela con descriptor de archivo
#### Ejemplos:
``` bash
# Sin sustitución de procesos, necesitaríamos varios pasos:
ssh servidor1 'ls -la /etc/nginx/' > config1.txt
ssh servidor2 'ls -la /etc/nginx/' > config2.txt
diff config1.txt config2.txt
rm config1.txt config2.txt

# Con sustitución de procesos, en una sola línea:
diff <(ssh servidor1 'ls -la /etc/nginx/') <(ssh servidor2 'ls -la /etc/nginx/')

# Monitorizar cambios en procesos en tiempo real
watch -d "diff <(ps aux) <(sleep 1; ps aux)"
```

- - - 
## ***Sources:***