**MetaTags:** #_Todo
**Tags:** #Programación  #ToLink
- - -
- como se cargar los argumentos en los puntero  a funcion
- macros condicionales para chunks de codigo
- array a funciones
- macros con argumentos

Aquí tienes un listado consolidado de todas las opciones avanzadas y exóticas para experimentar en C:

1. **Metaprogramación con el preprocesador**  
   - Macros Turing-completas: Utiliza recursión macro y concatenación de tokens para realizar cálculos en tiempo de compilación.  
   - Macros con argumentos complejos: Expande macros que acepten argumentos sofisticados, incluyendo recursión y generación de código.

2. **Manipulación avanzada de punteros a función**  
   - Arrays de punteros a función: Implementa tablas de despacho dinámico o callbacks que contengan funciones de diversas firmas.  
   - Carga dinámica de argumentos en punteros a función: Diseña mecanismos para adaptar llamadas a funciones con número y tipo de argumentos variables en tiempo de ejecución.

3. **Extensiones del compilador y construcciones no estándar**  
   - Computed goto: Emplea etiquetas como valores (disponible en GCC) para saltos dinámicos, útil en intérpretes o máquinas virtuales.  
   - Emulación de closures y trampolines: Utiliza técnicas como trampolines y manipulación de memoria (por ejemplo, con `mmap`) para crear funciones con estado encapsulado.

4. **Polimorfismo y sobrecarga en C**  
   - Uso de _Generic (C11): Implementa polimorfismo estático que permite seleccionar implementaciones de funciones basadas en el tipo de sus argumentos, simulando sobrecarga.

5. **Código auto-modificante y compilación Just-In-Time (JIT)**  
   - Auto-modificación: Emplea funciones como `mprotect` para marcar regiones de memoria como ejecutables y reescribir código en tiempo de ejecución.  
   - JIT Embebido: Implementa un compilador JIT rudimentario dentro de una aplicación C, generando y ejecutando código binario en función de datos de entrada.

6. **Intérpretes auto-contenidos y metacompiladores**  
   - Mini-interprete en C: Crea un intérprete capaz de ejecutar un subconjunto del lenguaje C o un DSL embebido, involucrando parseo y análisis sintáctico en tiempo real.  
   - Meta-compilación: Genera código C a partir de descripciones de alto nivel, combinando generación de código y técnicas avanzadas del preprocesador.

7. **Obfuscación extrema y “arte” en C**  
   - Código ofuscado: Participa en concursos como el IOCCC para escribir código deliberadamente críptico, usando construcciones inusuales y recursión macro.  
   - Arte con macros: Genera patrones o "dibujos" en ASCII mediante la manipulación avanzada del preprocesador.

8. **Explotación de extensiones y trucos de compilador**  
   - Extensiones GNU: Aprovecha `typeof`, atributos como `__attribute__((cleanup))`, y otros trucos para emular comportamientos de lenguajes de alto nivel.  
   - Inline assembly: Incorpora código ensamblador embebido para optimizar secciones críticas o realizar operaciones a nivel de hardware.

9. **Técnicas de manipulación de memoria y tipado**  
   - Uniones multiuso y puntero punning: Emplea uniones para reinterpretar bloques de memoria de múltiples formas, útil en contextos de compresión, criptografía o procesamiento de señales.  
   - Sistemas de tipos "dinámicos" en C: Emula características de lenguajes dinámicos mediante estructuras y tablas de función que gestionen la información de tipos en tiempo de ejecución.

10. **Arrays de funciones con tipos diferentes mediante uniones**  
    - Combina uniones y estructuras (con un indicador de tipo, por ejemplo, un `enum`) para almacenar punteros a funciones con distintas firmas en un mismo array, gestionando la invocación mediante conversiones controladas.

Este listado recoge técnicas avanzadas que permiten explorar los límites y la flexibilidad del lenguaje C. Cada opción implica desafíos en legibilidad, portabilidad y mantenimiento, por lo que se recomienda experimentar con cuidado y documentar adecuadamente cada implementación.  

¿Necesitas información adicional o ejemplos de alguna de estas técnicas en particular?

- - - 
## ***Sources:***