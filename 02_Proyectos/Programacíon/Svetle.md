**MetaTags:** #_Todo
**Tags:** #Svelte #Programación #ToLink 
- - -

svelte usa html, css y javascipt/ts en el mismo arhcivo.

tiene palabras reservadas llamadas runas, que conectan una api que transpila en codigo 
a javascript optimizado y lo incrusta directamente en el DOM original.  

las runas solo pueden ser contenidos en archivos con extension .svelte

==REACTIVIDAD==
- puedes incrustar variables en el html con 
<p>{variable_a_expandir}</p>

- $state(variable_reactiva), runa para valores reactivos cuando "variable_reactiva" es reasignada o mutada,
se vuelve a actualizar el DOM, ergo se rederizara la pagina.

- $derived(), runa que permite crear valores reactivos de otros valores reactivos(recuerda al 2way-databinding)

- Debuggin los valores reactivos no puedes ser serializados directamnte por el navegador, aqui 3 metodos para debugearlos
  1) $state.snapshot(variable_reactiva), hace una copia en un string "plano", e imprimes este string
  2) $inspect(variable_reactiva), runa que imprime por consola el valor de la variable **cuando cambia**,
  ademas a esta ruan se le pueden añadir metodos, como .with(console.trace)
==Efectos==
la runa $effect es un disparador ante un cambio de estado de la app, se pueden crear funciones personalizadas,
aunque "event_handler" es mas optimo

==Propiedades==
es el mecanismo para pasar datos de un componente padre a un un  componente hijo, se utiliza la runa $props
ejemplo:
componente_Hijo:
let {var} = $props();  si quisieramos darle un valor por defecto( en el caso de que no se invoque ningun valor en el padre,
let {var = 42 } = $props();
en el padre:
<Componente_Hijo var={queso} />
<Componente_Hijo  />
asi padre le pasa el valor queso, y el hijo lo recibe el la variable entre parentesis asignada a la runa
==Spreading==
cuando quieres pasar un objeto a un componente hijo puedes hacerlo con esta sintaxis:
<PackageInfo {...pkg} />


- - - 
#### ***Sources:***
