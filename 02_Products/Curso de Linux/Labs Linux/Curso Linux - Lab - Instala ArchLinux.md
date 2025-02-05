**Tags:** #_Todo
#ToTag #ToLink 
- - -
Si cambias propiedades de red. como reglas de firewall o nat into bridge... tienes que apagar la maquina y volverla a encerder para hacer efectivos los cambios
==Entender como hacer la instalacion desde ssh, todos los problemas con las redes puertos tipos de conexion etc==
# Hacer la maquina en Virtual Box
``` bash
# en tu host para permitir la conexion ssh
VBoxManage modifyvm "NombreDeTuVM" --natpf1 "ssh,tcp,,2222,,22"
```
Si prefieres hacerlo por GUI:

Abre VirtualBox
Selecciona tu VM
Ve a Configuración > Red > Avanzado > Reenvío de Puertos
Agrega una regla:
Nombre: SSH
Protocolo: TCP
Puerto Anfitrión: 2222
Dirección Anfitrión: (dejar vacío)
Puerto Huésped: 22
Dirección Huésped: (dejar vacío)

- - - 
``` bash
# Para poder tener el teclado en espñol
loadkeys es
```
- - - 
# Internet
 SI lo haces desde maquina virtual con NAT ya tienes internet 
Sino.... 
``` bash
iwctl show address
```
# Conectarte por ssh
En el medio de instalacion:
``` bash
# Mirar  si la red enp0s3 o eth0 estan UP
ip a
```
==Ver como se resuelve no tener la tarjate de red activa(probable systemctl)==

Activamos ssh. El medio de instalación de Arch trae sshd, pero no siempre está habilitado. Actívalo manualmente:
```bash
systemctl start sshd
```
Verifica que está corriendo:
```bash
systemctl status sshd
```
Configura una contraseña para el root
```bash
passwd
```




- - - 


- - - 
``` bash

```
- - - 
``` bash

```



- - - 
## ***Sources:***
- [Descargar la Imagen](https://mirror.23m.com/archlinux/iso/latest/)