**Tags:** #_Todo
#Redes #IP #ToLink 
- - -
nmcli (NetworkManager CLI, para distros con NetworkManager)

Para configurar una IP estática:
```bash
sudo nmcli con mod "Wired connection 1" ipv4.addresses 192.168.1.100/24 ipv4.gateway 192.168.1.1 ipv4.dns "8.8.8.8" ipv4.method manual
sudo nmcli con up "Wired connection 1"
```
- - - 
## ***Sources:***