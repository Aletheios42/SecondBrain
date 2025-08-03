**Tags:** #_Todo
**MetaTags:** #CSS #ToLink
- - -
 color rgba legacy |  rgb(n1 n2 n3 / opacidad(opcional)) moderno | trasparent palabra clave | oklch(mas moderno) && hsl |  ==Encontrar hoja de colores==

```css
.selector {
    /* Colores */
    color: #ff0000;                      /* Color en hexadecimal */
    color: rgb(255, 0, 0);               /* Color en RGB */
    color: rgba(255, 0, 0, 0.5);         /* Color en RGBA con transparencia */
    color: hsl(0, 100%, 50%);            /* Color en HSL */
    -webkit-text-fill-color: transparent; /* Texto transparente (para usar con background-clip) */
    text-stroke: 1px yellow;              /* Borde del texto */
    text-emphasis-color: red;             /* Color de énfasis en el texto */

    /* Fondos */
    background-color: #fff;               /* Color de fondo en hexadecimal */
    background-image: url('imagen.jpg');  /* Imagen de fondo */
    background-repeat: no-repeat;         /* Evita la repetición del fondo */
    background-position: center;          /* Posición del fondo */
    background-size: cover;               /* Ajusta el tamaño del fondo */
    background-attachment: fixed;         /* Fija el fondo en su lugar (efecto parallax) */
    background-blend-mode: multiply;      /* Modo de mezcla del fondo */

    /* Gradientes */
    background: linear-gradient(to right, #fff, #000); /* Degradado lineal */
    background: radial-gradient(circle, #fff, #000);   /* Degradado radial */

    /* Colores de bordes y contornos */
    border-color: black;                  /* Color del borde */
    outline-color: blue;                  /* Color del contorno externo */

    /* Sombras */
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5); /* Sombra en el texto */
    box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.3); /* Sombra en el contenedor */

    /* Filtros de color */
    filter: hue-rotate(90deg) saturate(1.5); /* Rotación de tono y saturación */
    backdrop-filter: blur(5px) brightness(0.8); /* Filtro de fondo (efecto de desenfoque y brillo) */

    /* Nuevos atributos específicos */
    accent-color: purple;                 /* Color de acento para elementos de formulario */
    caret-color: red;                     /* Color del cursor en inputs y áreas de texto */
    scrollbar-color: blue orange;         /* Color de la barra de desplazamiento */
}
```

- - - 
## ***Sources:***