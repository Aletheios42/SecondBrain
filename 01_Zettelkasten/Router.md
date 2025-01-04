**Tags:** #_Todo
#Redes #ToLink 
- - -
Un router es un dispositivo de capa 3 (nivel de red) que opera como intermediario para el encaminamiento de paquetes entre diferentes redes IP. Su función principal es determinar la ruta óptima para el tráfico de red mediante el análisis de las direcciones IP origen y destino de cada paquete.
El router mantiene una tabla de enrutamiento que contiene: (1) rutas estáticas configuradas manualmente, (2) rutas dinámicas aprendidas mediante protocolos de enrutamiento como OSPF o BGP, y (3) rutas conectadas directamente. Esta tabla permite al router tomar decisiones de reenvío (forwarding) basadas en el prefijo de red más específico que coincida con la dirección IP destino.
Para realizar el encaminamiento, el router:

Examina la dirección IP destino del paquete entrante
Consulta su tabla de enrutamiento para determinar la interfaz de salida óptima
Decrementa el TTL y actualiza el checksum
Reenvía el paquete hacia el siguiente salto

Además, implementa funciones como NAT, ACLs, QoS, y puede participar en protocolos de redundancia como VRRP o HSRP para garantizar alta disponibilidad,.

son accesibles y tienen su propia hoja de configuracion
- - - 
## ***Sources:***
- [Modem vs Router - What's the difference?](https://www.youtube.com/watch?v=Mad4kQ5835Y&list=PL7zRJGi6nMRzg0LdsR7F3olyLGoBcIvvg)
- [Hub, Switch, & Router Explained - What's the difference?](https://www.youtube.com/watch?v=1z0ULvg_pW8&list=PL7zRJGi6nMRzg0LdsR7F3olyLGoBcIvvg&index=2)
- [Wireless Access Point vs Wi-Fi Router](https://www.youtube.com/watch?v=OxiY4yf6GGg&list=PL7zRJGi6nMRzg0LdsR7F3olyLGoBcIvvg&index=4)