**MetaTags:** #_Todo
**Tags:** #CSS #ToLink 
- - -
Las **transiciones** permiten que los cambios en las propiedades de un elemento ocurran de manera suave en un tiempo determinado.
**Consejo**: Usa transiciones para mejorar la experiencia de usuario sin afectar el rendimiento.
## Sintaxis
```css
.elemento {
    transition: propiedad duración función-de-aceleración retraso;
}
```
## Propiedades clave
- **`transition-property`** → Especifica qué propiedad cambiará.
- **`transition-duration`** → Define la duración de la transición.
- **`transition-timing-function`** → Controla la aceleración de la transición.
- **`transition-delay`** → Define un retraso antes de iniciar.
## Ejemplo
```css
.elemento {
    width: 100px;
    height: 100px;
    background-color: red;
    transition: background-color 0.3s ease-in-out;
}

.elemento:hover {
    background-color: blue;
}
```
## Funciones de aceleración
- **`ease`** → Comienza lento, acelera y luego desacelera.
- **`linear`** → Cambio uniforme sin aceleración.
- **`ease-in`** → Comienza lento y luego acelera.
- **`ease-out`** → Comienza rápido y desacelera.
- **`ease-in-out`** → Comienza y termina lento.
## Transiciones múltiples
Se pueden aplicar varias transiciones separadas por comas:
```css
.elemento {
    transition: background-color 0.3s ease, transform 0.5s ease-in-out;
}
```


- - - 
## ***Sources:***