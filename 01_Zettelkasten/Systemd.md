**Tags:** #_Todo
#ToTag #ToLink 
- - -
Es el gestor mas popular de linux de recursos y sevicios, se compone de unidades, que constan de un nombre, un tipo y un archivo de configuracion propio.
los tipos:
service
The most common unit type, for active system resources that can be initiated, interrupted and reloaded.
socket
The socket unit type can be a filesystem socket or a network socket. All socket units have a
corresponding service unit, loaded when the socket receives a request.
device
A device unit is associated with a hardware device identified by the kernel. A device will only be taken as a systemd unit if a udev rule for this purpose exists. A device unit can be used to resolve configuration dependencies when certain hardware is detected, given that properties from the udev rule can be used as parameters for the device unit.
mount
A mount unit is a mount point definition in the filesystem, similar to an entry in /etc/fstab.
automount An automount unit is also a mount point definition in the filesystem, but mounted automatically. Every automount unit has a corresponding mount unit, which is initiated when the automount mount point is accessed.
target
A target unit is a grouping of other units, managed as a single unit.
snapshot
A snapshot unit is a saved state of the systemd manager (not available on every Linux distribution).

utiliza el comnado systemctl, con las siguientes opciones start, stop, reestar, status, is-active, enable, disable, is-enabled, isolate, defualt, get-default, list-unit-files \[--type\]

Es el primer programa lanzado por el kernel, PID=1

- - - 
## ***Sources:***