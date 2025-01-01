**Tags:** #_Todo
#ToTag #ToLink 
- - -
 ## Ejercicios Guiados
 ###### 1. Suppose an operating system is unable to boot after adding a second SATA disk to the system. Knowing that all parts are not defective, what could be the possible cause for this error?
- R:  Hay que ajustar el order de booteo en la BIOS ❌ 
###### 2. Suppose you want to make sure the external video card connected to the PCI bus of your newly acquired desktop computer really is the one advertised by the manufacturer, but opening the computer case will void the warranty. What command could be used to list the details of the video card, as they were detected by the operating system?
- R: lspci para comprobar el ID de la tarjeta de video y luego lspci -v -d ID ✅ 
###### 3. The following line is part of the output generated by command lspci:03:00.0 RAID bus controller: LSI Logic / Symbios Logic MegaRAID SAS 2208 [Thunderbolt] (rev 05) What command should you execute to identify the kernel module in use for this specific device?
- R:   lspci -s 03:00.0 -v or lspci -s 03:00.0 -k  ❌ 
###### 4. A system administrator wants to try different parameters for the bluetooth kernel module without rebooting the system. However, any attempt to unload the module with modprobe -r bluetooth results in the following error: modprobe: FATAL: Module bluetooth is in use. What is the possible cause for this error?
- R: un proceso lo esta usando, deberia buscar cual y mandarle un kill. ✅ 


## Ejercicios Exploracionales
##### 1. It is not uncommon to find legacy machines in production environments, like when some equipment uses an outdated connection to communicate with the controlling computer, making it necessary to pay special attention to some peculiarities of these older machines. Some x86 servers with older BIOS firmware, for example, will not boot if a keyboard is not detected. How can this particular issue be avoided?
- R:  hay que desactivar la opcion especifica de bloqueo de dispositivo cuando no se encuentra teclado.
##### 2. Operating systems built around the Linux kernel are also available for a wide variety of computer architectures other than x86, like in single board computers based on the ARM architecture. An attentive user will notice the absence of the lspci command on such machines, like the Raspberry Pi. What difference with x86 machines justifies that absence?
- R: No tienen ese centro de control de sensores, PCI bus, asi que no hay comando para dar la info sobre un componente que no tienen.
##### 3. Many network routers have a USB port allowing for the connections of an external device, like a USB hard drive. Since most of these are using a Linux based operating system, how will an external USB hard drive be named in the /dev/ directory, assuming no other conventional block device is present in the router?
- R: El kernel de linux identifica todos los almacenamientos usb como SATA /dev/sda.
##### 4. In 2018, the hardware vulnerability known as Meltdown was discovered. It affects almost all processors of many architectures. Recent versions of the Linux kernel can inform if the current system is vulnerable. How can this information be obtained?
- R:  la info del procesador se encuentra en /proc/cpuinfo , en ese arhivo hay una linea "bugs: cpu_meltdown"

- - - 
## ***Sources:***