**MetaTags:** #_Investigar
**Tags:** #Linux #ToLink
- - -
Es el puente entre el firmware y el sistema operativo, es el responsable de cargar el kernel y el modo en el que se ejecuta, ademas  le pasa parametros al kernel como en que particion esta el sistema de archivos (intrafs) en memoria. 

Se aloca en el primer sector del Disco duro (MBR)
En la partición EFI en las versiones actuales.
==Parametros que le pasa al kernel==
acpi
Enables/disables ACPI support. acpi=off will disable support for ACPI.
init
Sets an alternative system initiator. For example, init=/bin/bash will set the Bash shell as the
initiator. This means that a shell session will start just after the kernel boot process.
systemd.unit
Sets the systemd target to be activated. For example, systemd.unit=graphical.target.
Systemd also accepts the numerical runlevels as defined for SysV. To activate the runlevel 1, for
example, it is only necessary to include the number 1 or the letter S (short for “single”) as a
kernel parameter.
mem:
Sets the amount of available RAM for the system. This parameter is useful for virtual machines
so as to limit how much RAM will be available to each guest. Using mem=512M will limit to 512
megabytes the amount of available RAM to a particular guest system.
maxcpus
Limits the number of processors (or processor cores) visible to the system in symmetric multi-
processor machines. It is also useful for virtual machines. A value of 0 turns off the support for
multi-processor machines and has the same effect as the kernel parameter nosmp. The
parameter maxcpus=2 will limit the number of processors available to the operating system to
two.
quiet
Hides most boot messages.
vga
Selects a video mode. The parameter vga=ask will show a list of the available modes to choose
from.
root
Sets the root partition, distinct from the one pre-configured in the bootloader. For example,
root=/dev/sda3.
rootflags
Mount options for the root filesystem.
ro
Makes the initial mount of the root filesystem read-only.
rw
Allows writing in the root filesystem during initial mount.
- - - 
## ***Sources:***
