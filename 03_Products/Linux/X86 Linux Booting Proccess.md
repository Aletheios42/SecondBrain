**MetaTags:** #_Completar
**Tags:** #Linux #ToLink
- - -

Es el proceso de inicio del sistema desde que recibe energia hasta que la interfaz de usuario es completamente funcional. el kernel inicia un programa llamado init.

El sistema operativo se inicia cuando el [[Kernel]] carga en la RAM el [[Bootloader]] despues el kernel carga el archivo initramfs, que le permite despues arcceder al  sistema de archivos de la raiz,  y este ya le permite cargar todos los sistemas de archivos accediendo a /etc/fstab, tras esto por fin se llama al programa init, el cuan inicializa todos los [[Daemon]]s, dejando todo listo para el usuario.

==Hacer un diagrama con mermaid==
power on -> [[Bios]] -> [[Bootloader]]->[[Sistema Operativo]]

// copiado del libro
Generally speaking, the pre-operating steps to boot a system equipped with BIOS are:
1. The POST (power-on self-test) process is executed to identify simple hardware failures as soon
as the machine is powered on.
2. The BIOS activates the basic components to load the system, like video output, keyboard and
storage media.
3. The BIOS loads the first stage of the bootloader from the MBR (the first 440 bytes of the first
device, as defined in the BIOS configuration utility).
4. The first stage of the bootloader calls the second stage of the bootloader, responsible for
presenting boot options and loading the kernel.

- - - 
## ***Sources:***
- [Curso de Linux de FreeCodeAcademy](https://www.youtube.com/watch?v=sWbUDq4S6Y8)
- libro de lcpi1 seccion system initialization