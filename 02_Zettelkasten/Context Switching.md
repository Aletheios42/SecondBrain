**MetaTags:** #_Todo
**Tags:** #Electronica #LowLevel #DiseñoDeSistemas
- - -

Es un mecanismo esencial del scheduler del kernel que permite guardar el estado de los registros de los procesos asi como volver a cargarlos en los registros del CPU,  permitiendo intercalar ejecuciones de los miles de procesos activos en un sistema. Dando asi la sensacion de concurrencia

Tipos de interrupciones:
- syscall en la pila del programa o software interrup
		 Ej: int ox00 en  x86)
- Señal por el componente de hardware
		ej: el reloj del procesador interno que evita loops infinitos

El funcionamiento de las interrupciones es el mismo, se termina de ejecutar la instruccion actual, se cambia inmediatamente el registro "program counter", y se ejecuta codigo para guardar un snapshot de los registros del programa interrumpido, tambien llamado "Contexto"

Cambiar el registro del programa y el stack pointer para poder cargar el snapshot, supone un problema, porque sea cual sea que hagas primero hace que no puedas interumpir y cargar exactamente los mismo datos pues uno de los 2 tiene que cambiar(Mejorar esta idea, no la entiendo bien)
Soluciones generales en el diseño de sistemas que soportan interrupciones
- Varios set de registros: cuando una señal te pide cambiar el contexto simplemente cambias de register set. En concreto con 2, uno para el user mode y otro para el kernel mode es suficiente, ya que la señal cambia el program counter del set de kernel.  Este registro puede hacer el snapshot del user registry, sin alterarlo ejecutar la syscall y devolver el control al registro del usuario
- Hardware assisted switching: un circuito aparte que se activa con las señales que pushea un registro especial los registros criticos. program counter y stack pointer. Asi se guardan puedes hacer el snapshot del resto e registros y esos guardados, por lo que sobre escribir los registros criticos ya no es un problema
- task registrer
- - - 
#### ***Sources:***