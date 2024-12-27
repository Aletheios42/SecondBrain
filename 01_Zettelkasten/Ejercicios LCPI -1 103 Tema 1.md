**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson1
# Guided Exercises
##### 1. Use the man system to determine how to tell apropos to output a brief command so that it outputs only a brief usage message and then exits.
- R: apropos --usage
##### 2. Use the man system to determine which copyright license is assigned to the grep command.
- R: man grep | grep -i copyright
# Explorational Exercises
##### 1. Identify the hardware architecture and Linux kernel version being used on your computer in an easy-to-read output format. 
- R:  uname -iv
##### 2. Print out the last twenty lines of the dynamic history database and the .bash_history file to compare them.
- R: uno hace refenreca a la shell actual otro a la base de datos de bash, en mi caso todavia sin actualizar con la shell en uso.
##### 3. Use the apropos tool to identify the man page where you will find the command you will need to display the size of an attached physical block device in bytes rather than megabytes or gigabytes.
- R:  apropos -a list block; man lsblk, lsblk -b 
- - - 
# Lesson 2
# Guided Exercises
##### 1. Use the export command to add a new directory to your path (this will not survive a reboot).
- R:$ touch myfiles/myscript.sh
$ echo '#!/bin/bash' >> myfiles/myscript.sh
$ echo 'echo Hello' >> myfiles/myscript.sh
$ chmod +x myfiles/myscript.sh
$ myscript.sh
Hello
##### 2. Use the unset command to delete the PATH variable. Try running a command (like sudo cat /etc/shadow) using sudo. What happened? Why? (Exiting your shell will return you to your original state.)o
- R: unset PATH, no puedo acceder a ningun binario por su nombre
# Explorational Exercises
##### 1. Search the internet to find and explore the complete list of special characters.
- R: "   & ; | * ? " ' \[ ] ( ) $ < > { } # / \ ! ~."
##### 2. Try running commands using strings made up of special characters and using various methods to escape them. Are there differences between the way those methods behave?
- R:   $ echo "$mynewvar"
goodbye
$ echo '$mynewvar'
$mynewvar
- - - 
## ***Sources:***