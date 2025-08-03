# Introducción al Proyecto: Calculadora de Inversiones en Angular

Proyecto Completo en https://github.com/Aletheios42/Investment_Calculator_Web, paso a paso por commits, y con un archivo "instrucciones.txt" que te guia en cada uno de los pasos.

Este proyecto implementa una **calculadora de inversiones** en Angular que permite simular el crecimiento de una inversión a lo largo del tiempo mediante una arquitectura compuesta por 4 componentes fundamentales:

**Encabezado (Standalone)**  
Es el componente más sencillo, importa una imagen y muestra en un `<h1>` el título "Calculadora de Inversión", **centrado** mediante el atributo `class="center"`.

**Entrada-de-Usuario**  
Un formulario interactivo que recopila los datos de entrada:
```typescript
inversion = {
  inversionInicial: initialInvestment,    // Ej: 1000
  inversionAnual: annualInvestment,         // Ej: 500
  duracion: duration,                       // Ej: 10 (años)
  retornoEsperado: expectedReturn,          // Ej: 0.05 (5%)
};
```
Utiliza el decorador `@Output()` para emitir los valores introducidos hacia el componente padre.  

pista: https://v17.angular.io/guide/event-binding

**App Component**  
El componente central se encarga de recibir datos de Entrada de Usuario, procesar la inversión mediante el método `simularInversion` y hacerlos accesibles a su hijo Mostrar Balance a través de un array de la interfaz **Balance Anual**, definida de la siguiente manera:
```typescript
balanceAnual = { 
  año: year,
  interés: interestEarnedInYear,
  valorFinalDelAño: investmentValue,
  inversionAnual: annualInvestment,
  interésTotal: totalInterest,
  totalInvertido: initialInvestment + annualInvestment * year,
}
```
Recuerda que, como en el formulario pueden introducirse varios años, los datos se enviarán en forma de array `[]`.

**Mostrar Balance**  
Se encarga de renderizar condicionalmente mediante los decoradores de flujo 
`@If` 
- Muestra un párrafo centrado con el mensaje: "Introduzca los valores y presione 'calcular'" cuando no se han ingresado datos.
`@Else`
- Como su clase en .ts recibe la estructura a través del componente padre mediante el decorador `@Input()`, expande los datos procesados por el metodo de app component a traves de ** renderiza los resultados en una tabla utilizando interpolación y un bucle `*For`.
pista: https://angular.dev/guide/templates/control-flow

##### Arquitectura de Aplicación
```
          +-----------+
          | App Root  |
          +-----------+
                |
                v
       +------------------+
       | App-Component    |
       +------------------+
       | +--------------+ |
       | |  Encabezado  | |
       | +--------------+ |
       | +------------------------------+ |
       | | Entrada de Usuario           | |
       | | (@Output Event Emission)     | |
       | +------------------------------+ |
       | +------------------------------+ |
       | | Mostrar Balance              | |
       | | (Input Structure -> Table)   | |
       | +------------------------------+ |
       +------------------+
```