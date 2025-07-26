**MetaTags:** #_Completar
**Tags:** #Web #ToLink 
- - -

## Introducción
React es una librería de javascript creada por facebook, para generar el frontend de aplicaciones web basadas en componentes. React es principalmente una herramienta para el **Client-Side Rendering (CSR)**, aunque con frameworks como **Next.js** también es compatible con **Server-Side Rendering** (**SSR**)

## Componentes
Un **componente** es una clase instanciable de una parte de la interfaz de usuario y tiene 2 atributos principales:
- **Estado**: es un objeto mutable que guarda información interna de un componente, la cual puede cambiar con el tiempo. (instancia)
- **Props**: son datos inmutables que se pasan de un componente padre a un hijo para configurarlo o darle datos. (herencia)

El estado se gestiona a través del método `setState`, que actualiza el estado y provoca una nueva renderización del componente. Además, cuando varios componentes necesitan compartir el mismo estado, se puede **elevar el estado** (lifting state) al componente padre.

## Composición y Virtual DOM
La **composición** en React permite crear interfaces complejas a partir de componentes pequeños y reutilizables, pasando componentes como **props** o usando `children`. Este enfoque facilita la reutilización del código, permitiendo construir aplicaciones modulares, escalables y mantenibles.

React crea un **Virtual DOM**, una copia ligera del DOM real, donde los componentes son mapeados para detectar cambios. Cada vez que ocurre un **re-render**, React recalcula cómo debería lucir la UI tras un cambio en el estado o las props, actualizando el Virtual DOM. Luego, mediante el proceso de **diffing**, compara el árbol actual del Virtual DOM con el anterior para determinar los cambios mínimos necesarios.

Estos cambios se aplican al DOM real en la fase de **commit**, donde React ejecuta las modificaciones detectadas, actualiza el DOM y maneja efectos secundarios. Al evitar manipulaciones directas y agrupar actualizaciones (batching), React logra una actualización eficiente de la interfaz de usuario.

## Eventos y Arquitectura
Los eventos conllevan un nuevo re-renderizado, trigger, cambios de estado, llamadas a api. Su arquitectura es unidirectional data flow (One way data binding) donde los **controladores** (componentes padres) pasan datos y funciones como **props** a los **hijos** (vista). Los hijos muestran los datos y se comunican con los padres mediante callbacks.

Los **props** son de solo lectura, por lo que los componentes hijos no pueden modificarlos directamente, asegurando así la separación de responsabilidades y el control centralizado de los datos.

## Bundling y Herramientas
El **bundling** es el proceso de combinar múltiples archivos (JavaScript, CSS, imágenes, etc.) en uno o pocos archivos optimizados para el navegador, mejorando la carga y el rendimiento de las aplicaciones. Herramientas como **Webpack** y **Babel** son clave en React: Webpack gestiona el bundling y permite trabajar con módulos, mientras que Babel transpila el código moderno de JavaScript o TypeScript (como JSX) a una versión compatible con navegadores más antiguos.

## JSX
En React, las llaves `{}` se utilizan para **incrustar expresiones de JavaScript** dentro de JSX (JavaScript XML). JSX es una sintaxis que combina HTML y JavaScript, y las llaves permiten ejecutar código JavaScript dinámico en medio de la estructura declarativa.

- - - 
## ***Sources:***
- https://www.youtube.com/watch?v=GMnWXlJnbNo&list=LL&index=4
- https://medium.com/@livajorge7/understanding-react-architecture-a-comprehensive-guide-to-building-scalable-web-applications-ec32c8b1689e
