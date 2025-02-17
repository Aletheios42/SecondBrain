**Tags:** #_Todo
#ToTag #ToLink 
- - -
**Template HTML para Ejercicios**

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ejercicios DOM</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        .caja { width: 200px; height: 100px; background-color: lightgray; text-align: center; line-height: 100px; margin: 10px 0; }
        .destacada { background-color: yellow; font-weight: bold; }
    </style>
</head>
<body>

    <h1>Ejercicios de Manipulación del DOM</h1>
    <div id="miElemento" class="caja">Elemento de prueba</div>
    <div id="contenedor"></div>
    
</body>
</html>
```

**Enunciados de los Ejercicios**

1. **Modificar el texto de un elemento**: Cambia el texto del elemento con id `miElemento` a "Nuevo contenido" cuando se haga clic en un botón.

2. **Agregar un nuevo elemento al DOM**: Crea un nuevo `div` con el texto "Soy un nuevo div" y agrégalo dentro del `#contenedor` cuando se presione un botón.

3. **Cambiar el estilo de un elemento**: Alternar la clase `destacada` del elemento con id `miElemento` al hacer clic en un botón.

4. **Guardar y leer datos del LocalStorage**:
   - Al hacer clic en un botón, guarda la cadena "Hola, almacenado en LocalStorage" en `localStorage`.
   - Agregar otro botón para recuperar y mostrar ese valor en una alerta.

5. **Hacer una petición a una API**: Usa `fetch` para obtener datos de la API `https://jsonplaceholder.typicode.com/todos/1` y muestra el título en una alerta.

6. **Capturar la tecla presionada**: Mostrar en un `alert` la tecla presionada por el usuario en el documento.

7. **Mostrar información del navegador**: Muestra en una alerta el `userAgent` del usuario.

8. **Redireccionar a otra página**: Al hacer clic en un botón, redirigir a `https://ejemplo.com`.

9. **Usar geolocalización**: Obtener y mostrar la latitud y longitud del usuario en una alerta.

10. **Conectar con WebSocket**: Enviar un mensaje a un servidor WebSocket y mostrar en una alerta el mensaje recibido.

[[Soluciones - Interactividad con el Navegador(JS)]]
---
## ***Sources:***