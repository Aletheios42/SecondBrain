**Tags:** #_Done 
 #Linux  #ToLink 
- - -
# Guided Exercises
##### 1. What is the default location for the GRUB 2 configuration file?
- R: /boot/grub/grub.cfg
##### 2. What are the steps needed to change the settings for GRUB 2?
- R: actualizas los campos de  /etc/default/grub, y luego ejecutas update-grub
##### 3. Into which file should custom GRUB 2 menu entries be added?
- R: /etc/grub.d/40_custom
##### 4. Where are the menu entries for GRUB Legacy stored?
- R: /boot/grub/menu.lst 
##### 5. From a GRUB 2 or GRUB Legacy menu, how can you enter the GRUB Shell?o
- R: En el menu, pulsa 'c'
# Explorational Exercises
##### 1. Imagine a user configuring GRUB Legacy to boot from the second partition of the first disk. He writes the following custom menu entry: title My Linux Distro root (hd0,2) kernel /vmlinuz root=/dev/hda1 initrd /initrd.img However, the system will not boot. What is wrong?
- R:  tendrias que escribir: (hd0,1) ya que legacy empieza en 0, no en 1 como GRUB2
##### 2. Imagine you have a disk identified as /dev/sda with multiple partitions. Which command can be used to find out which is the boot partition on a system?
- R: fdisk -l /dev/sda y tendra un '*' en sistemas MBR, y en GPT tendra una etiqueta EFI partition.
##### 3. Which command can be used to find out the UUID of a partition?
- R:   ls -la /dev/disk/by-uuid/ 
##### 4. Consider the following entry for GRUB 2 menuentry "Default OS" { set root=(hd0,1) linux /vmlinuz root=/dev/sda1 ro quiet splash initrd /initrd.img } Change it so the system will boot from a disk with the UUID 5dda0af3-c995-481a-a6f3- 46dcd3b6998d
- R:  utlitiza la forma moderna: menuentry "Default OS" { search --set=root --fs-uuid 5dda0af3-c995-481a-a6f3-46dcd3b6998 dlinux /vmlinuz root=/dev/sda1 ro quiet splash initrd /initrd.img }
##### 5. How can you set GRUB 2 to wait for 10 seconds before booting the default menu entry?
- R: cambiar el parametro,  GRUB_TIMEOUT=10  en /etc/default/grub.
##### 6. From a GRUB Legacy shell, what are the commands to install GRUB to the first partition of the second disk?
- R:  grub> root (hd1,0)
grub> setup (hd1)

- - - 
## ***Sources:***