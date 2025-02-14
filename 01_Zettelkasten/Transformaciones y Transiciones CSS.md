**Tags:** #_Todo
#ToTag #ToLink 
- - -
Las **transformaciones** y **transiciones** en CSS permiten modificar y animar los elementos de una página web, creando efectos visuales fluidos e interactivos.

### Transformaciones

- **`transform: translate(50px, 100px);`**  
  Desplaza el elemento en el eje X e Y. En este caso, el elemento se moverá **50px** hacia la derecha y **100px** hacia abajo.

- **`transform: rotate(45deg);`**  
  Rota el elemento **45 grados** en el sentido de las agujas del reloj.

- **`transform: scale(1.5);`**  
  Aumenta el tamaño del elemento en un **1.5 veces** su tamaño original. Puedes usar valores menores a 1 para reducir el tamaño.

### Transiciones

Las **transiciones** permiten que un cambio en una propiedad de un elemento ocurra de forma suave durante un período de tiempo.

- **`transition: all 0.3s ease;`**  
  Esta transición aplica a **todas** las propiedades del elemento y toma **0.3 segundos** para completarse, utilizando una curva de aceleración **"ease"**, que comienza lento, acelera y luego desacelera.

- **`transition: background-color 0.3s ease-in-out;`**  
  Esta transición afecta solo al cambio de color de fondo (**`background-color`**) y dura **0.3 segundos**. La curva de aceleración **"ease-in-out"** hace que el cambio comience y termine de forma suave.

### Animaciones

Las **animaciones** en CSS permiten realizar movimientos y transformaciones más complejas y controladas a lo largo del tiempo.

- **`@keyframes slide`**  
  Define una animación llamada **`slide`**.  
  - **`from { transform: translateX(0); }`**: El elemento comienza en su posición original (sin desplazarse).
  - **`to { transform: translateX(100px); }`**: El elemento se mueve **100px** hacia la derecha.

- **`animation: slide 2s infinite;`**  
  Aplica la animación **`slide`** al elemento, durando **2 segundos** por ciclo. La animación se repite **infinitamente**.

### Ejemplo Visual

Imagina un cuadro que se desplaza de izquierda a derecha y cambia de color al hacer hover:

```css
.elemento {
    width: 100px;
    height: 100px;
    background-color: red;
    transition: background-color 0.3s ease;
}

.elemento:hover {
    background-color: blue;
    transform: translate(50px, 0); /* Desplaza el cuadro 50px hacia la derecha */
}
```

- - - 
## ***Sources:***