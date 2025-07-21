**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. How could the telinit command be used to reboot the system?
R: telinit 6, que el el runlevel de reboot
##### 2. What will happen to the services related to the file /etc/rc1.d/K90network when the system enters runlevel 1?
R: se les mandara un SIGTERM/SIGINT, ya que no hay modo red en el nivel 1.
##### 3. Using command systemctl, how could a user verify if the unit sshd.service is running?
R: systemctl status sshd
##### 4. In a systemd based system, what command must be executed to enable activation of the unit sshd.service during system initialization?
R: systemctl enable sshd

# Explorational Exercises
##### 1. In a SysV based system, suppose the default runlevel defined in /etc/inittab is 3, but the system always starts in runlevel 1. What is the probable cause for that?
R: se le estan pasando como parametros al kernel durante el boot.
##### 2. Although the file /sbin/init can be found in systemd based systems, it is only a symbolic link to another executable file. In such systems, what is the file pointed by /sbin/init?
R: al binario original /lib/systemd/systemd.
##### 3. How can the default system target be verified in a systemd based system?
R: systemctl get-default  o en el arcivo:  /etc/systemd/system/default.target 
##### 4. How can a system reboot scheduled with the shutdown command be canceled?
R: shutdown -c
- - - 
## ***Sources:***