**Tags:** #_Todo
#Redes #IP #ToLink 
- - -
Con ip y ip route (Método temporal hasta reinicio)
Si solo quieres una configuración temporal sin modificar archivos:

``` bash
sudo ip addr add 192.168.1.100/24 dev eth0
sudo ip route add default via 192.168.1.1
```
Para agregar DNS:
```bash
echo "nameserver 8.8.8.8" | sudo tee /etc/resolv.conf
```
⚠️ Este método se pierde al reiniciar.
- - - 
## ***Sources:***