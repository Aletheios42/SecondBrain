---
Modificaciones: 2025-08-09T10:34:39+02:00
Creación: 2025-04-03T18:45:38+02:00
---
**MetaTags:** #_Done 
**Tags:** #Productividad  #LenguajesDeMarcado #SegundoCerebro #Notas
- - -
[[Obsidian Callouts]]

# Texto y Formateo
- **Encabezados (#, ##, ###, etc.)**
    - Ejemplo: 
        # Encabezado de Nivel 1
        ## Encabezado de Nivel 2
        ### Encabezado de Nivel 3
        #### Encabezado de Nivel 4
        ##### Encabezado de Nivel 5
        ###### Encabezado de Nivel 6
- **Negrita**
- *Cursiva*
- ***Negrita y cursiva***
- ~~Tachado~~
# Listas
- **Lista ordenada**
        1. Primer ítem
        2. Segundo ítem
        3. Tercer ítem
- **Lista desordenada**
        - Primer ítem
        - Segundo ítem
        - Tercer ítem ^9f1d73
- **Lista anidada**
    - Ejemplo:
        - Primer ítem
            - Sub-ítem 1
            - Sub-ítem 2
# Enlaces
- **Enlace simple**
	[Google](https://www.google.com)
- **Enlace simple con alias**
	[Google|esto es un alias](https://www.google.com)
- **Referencia interna (Obsidian: [[Nota]])**
	[[Mi Nota]]
- **Referencia interna con alias**
	[[Mi Nota| esto es un alias]]
- **Referencia a un encabezado de una nota**
	[[Guía Rápida Markdown#Texto y Formateo]]
- **Referencia a un bloque de texto una nota**
	[[Guía Rápida Markdown#^9f1d73]]
# Imágenes
- **Imagen simple**
    - Ejemplo: ![Imagen](https://via.placeholder.com/150)
- **Imagen de referencia** para incrustar !
    - Ejemplo: ![[Imagen_referencia.png]]
# Tablas

header 1 | header 2
- - - | - - - 
queso | jamon 

# Bloques
- **Bloques de citas**

> Este es un bloque de cita.

- **Bloques de código**
    - Ejemplo:
        ```python
        print("Hola Mundo")
        ```
# Divisores
- **Línea horizontal (---, ***, ___)**
- - - 
    - Ejemplo:
        ---
        ***
        ___
# Pie de pagina
En 2 partes:
Esto es texto con una nota al pie[^1].

[^1]: Este es el contenido de la nota al pie, que aparecerá al final. necesita estar separado por un salto de linea.

En linea
Esto es otro pie de nota ^[es mas sencillo asi]

Con notas embedidas
Esto es otro pie de nota ^[[[Guía Rápida Markdown#Pie de pagina | Pie de pagina]]]
 
# Checkboxes
- **Tareas o listas de verificación (- [ ], - [x])**
    - Ejemplo:
        - [ ] Tarea 1
        - [x] Tarea completada
# Citas
> se ponen con ">"
# Elementos Extendidos
- **Encabezados con IDs (# Título {#id})**
    - Ejemplo: # Título {#titulo-id}
- **Códigos de Inline (\Código inline\`\`)**
    - Ejemplo: `Código inline`
- **Matemáticas si está habilitado: 
 $$E = mc^2$$ 
 o 
$$...$$
- **Resaltado de texto (si está habilitado: ==Texto==)**
    - Ejemplo: ==Texto resaltado==
# Diagramas
- **Diagramas y gráficos (si el visor lo soporta, como Mermaid en Obsidian o GitHub)**
    - Ejemplo:
        ```mermaid
        graph TD;
          A-->B;
          B-->C;
          C-->A;
        ```
- - - 

## ***Sources:***
- https://www.markdownguide./
- https://www.youtube.com/watch?v=d8fXEhWy_rY