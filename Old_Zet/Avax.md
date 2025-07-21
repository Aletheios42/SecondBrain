**Tags:** #_Todo
#ToTag #ToLink 
- - -

chainid: 55511

Avax es una multichain, orientada a gaming con buena performance y barata. aunque necesita muchos recursos para montar nodos.

su mecanismo de consenso es el snowman. //mirarlo

// TODO hay que completar esto
sus cadenas principales son:
x  
p
c

las cadenas "personales" se comunicas a traves de ICM y la interoperabilidad es lock-mint
se programa en solidity y las L1 tambien son compatibles con Go

hay 3 interacciones basicas,
-generar las keys,
-firmar
-vericar

tiene capacidad para deployear l1, estas con su propio token, y hasta mecanismo de consenso, estas son compatibles con go bytecode.


ejercicios, deployear y comunicar l1 entre los compis de la bootcmap


Temas para la bootcamp:
	-bridges (burn/ lock --> mint)
	-wrapping (into Erc20) / unwrapping (into Native token)
	-crosschain comunication (it s more complex)

comunicacion:
- **AWM** proporciona la infraestructura de mensajería rápida y eficiente dentro de Avalanche.
- **Teleporter** utiliza AWM para habilitar la interacción y la transferencia de datos entre las subredes de Avalanche.
- **ICM** es un concepto que podría extenderse a través de tecnologías como Teleporter, permitiendo la comunicación entre cadenas diferentes, aunque el enfoque actual de Teleporter se limita principalmente a la interoperabilidad dentro de Avalanche.
ICTT bridges deployed through [**AvaCloud**](https://avacloud.io/) will automatically integrate into the [**Core Bridge**](https://core.app/en/bridge)
¿Relayer?

Precompilados: son las librerias de la blockchain, se almacenan como binarios en el entorno de ejecucion(el cliente); tu nodo, y se llaman con interfaces.

![[Chuleta_EVM_Firmware.png]]

- - - 
## ***Sources:***