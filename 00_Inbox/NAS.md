**MetaTags:** #_Todo
**Tags:** #ToTag #ToLink 
- - -

Es un protocolo que asigna a un dispositivo local [[Direcciones no Roteables]]

Se le conoce como "IPV6 killer"Contribuyo enormemete a la manutencion de la arquitectura IPV4.

hay varios tipos:

| Criterio        | SNAT                                     | DNAT                                        | PAT (NAT sobrecargado)                                    |
| --------------- | ---------------------------------------- | ------------------------------------------- | --------------------------------------------------------- |
| Modifica        | Dirección IP de **origen**               | Dirección IP de **destino**                 | Dirección IP y número de **puerto de origen**             |
| Dirección       | Tráfico **saliente**                     | Tráfico **entrante**                        | Tráfico **saliente**, multiplexa puertos                  |
| Uso común       | Compartir IP pública                     | Redirigir puertos (port forwarding)         | Compartir una IP pública para múltiples hosts             |
| A nivel técnico | `POSTROUTING` (`iptables`)               | `PREROUTING` (`iptables`)                   | Variante de SNAT que traduce puertos en `POSTROUTING`     |
| Ejemplo         | 10.0.0.2 → 203.0.113.1 (origen cambiado) | 203.0.113.1 → 10.0.0.100 (destino cambiado) | 10.0.0.2:1234 → 203.0.113.1:10001 (IP y puerto cambiados) |

terminologia nat:(revisar)
- inside local address: es una ip privada en la red local
- inside global address: es la ip publica con la que los dispositivos locales se presentan en internet
- Outside local address: es la ip privada que referencia un dispositivo privado fuera de la red
- Outside global address:  es la ip publica que referencia una red fuera de nuestra red
- - - 
#### ***Sources:***