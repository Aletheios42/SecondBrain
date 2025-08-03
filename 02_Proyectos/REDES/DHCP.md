**MetaTags:** #_Todo
**Tags:** #Redes #ToLink 
- - -

Es un protocolo cliente-servidor, entre el router y el host que trasfiere la configuracion de red a un dispositivo, da una ip e informa cual es default gateway, ademas proveede de un servidor DNS, 
la asignacion de ip puede ser:
- estatica /manual
- dinamica
- automatica

DHCP workflow, 
	1) el ordenador bootea y el lciente DHCP manda un "discovery packet" al servidor DHCP del router a traves de  255.255.255.255:67 UDP port 67
	2) el servidor responde con un "oferr packet" a la mac address del cliente por el puerto 68
	3) entonces el cliente le manda al servidor un "request packet", pidiendo una ip,
	4) entonces el servidor manda un "aknowledgement packet", proveyendo de una ip al cliente
	5) el cleinte cambia su configuracion de ip por la recibida por el servidor


componente de un proceso DHCP:
- puertos
- rango de dirrecciones ip
- direccioones reservadas
- leaeses
- opciones: como defualt gateway location, DNs server address, timer ,
- configuracoin de red preferida,

- - - 
#### ***Sources:***