**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. Someone just donated a laptop to your school and now you wish to install Linux on it. There is no manual and you were forced to boot it from a USB thumb drive with no graphics whatsoever. You do get a shell terminal and you know, for every processor you have there will be a line for it in the /proc/cpuinfo file: processor : 0 vendor_id : GenuineIntel cpu family : 6 model : 158 (lines skipped) processor : 1 vendor_id : GenuineIntel cpu family : 6 model : 158 (more lines skipped)
◦ Using the commands grep and wc display how many processors you have.
◦ Do the same thing with sed instead of grep.
- R: 
1) cat /proc/cpuinfo | grep processor | wc -l 
2) sed -n '/processor/p' /proc/cpuinfo | wc -l

##### 2. Explore your local /etc/passwd file with the grep, sed, head and tail commands per the tasks below:
◦ Which users have access to a Bash shell?
R: </etc/passwd grep :1000: | wc -l
◦ Your system has various users that exist to handle specific programs or for administrative
purposes. They do not have access to a shell. How many of those exist in your system?
 R:  grep ":/bin/bash$" /etc/passwd
◦ How many users and groups exist in your system (remember: use only the /etc/passwd file)?
R  cut -d: -f3 /etc/passwd | wc -l   -- cut -d: -f4 /etc/passwd | sort -u | wc -l
◦ List only the first line, the last line and the tenth line of your /etc/passwd file.
R  cut -d: -f3 /etc/passwd | wc -l   -- cut -d: -f4 /etc/passwd | sort -u | wc -l
##### 3. Consider this /etc/passwd file example. Copy the lines below to a local file named mypasswd for this exercise. root:x:0:0:root:/root:/bin/bash daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin bin:x:2:2:bin:/bin:/usr/sbin/nologin sys:x:3:3:sys:/dev:/usr/sbin/nologin sync:x:4:65534:sync:/bin:/bin/sync nvidia-persistenced:x:121:128:NVIDIA Persistence Daemon,,,:/nonexistent:/sbin/nologin libvirt-qemu:x:64055:130:Libvirt Qemu,,,:/var/lib/libvirt:/usr/sbin/nologin libvirt-dnsmasq:x:122:133:Libvirt Dnsmasq,,,:/var/lib/libvirt/dnsmasq:/usr/sbin/nologin carol:x:1000:2000:Carol Smith,Finance,,,Main Office:/home/carol:/bin/bash dave:x:1001:1000:Dave Edwards,Finance,,,Main Office:/home/dave:/bin/ksh emma:x:1002:1000:Emma Jones,Finance,,,Main Office:/home/emma:/bin/bash frank:x:1003:1000:Frank Cassidy,Finance,,,Main Office:/home/frank:/bin/bash grace:x:1004:1000:Grace Kearns,Engineering,,,Main Office:/home/grace:/bin/ksh henry:x:1005:1000:Henry Adams,Sales,,,Main Office:/home/henry:/bin/bash john:x:1006:1000:John Chapel,Sales,,,Main Office:/home/john:/bin/bash
◦ List all users in group 1000 (use sed to select only the appropriate field) from your
mypasswd file.
R: sed -n /:1000:[A-Z]/p mypasswd 
◦ List only the full names of all the users for this group (use sed and cut).
 R: sed -n /:1000:[A-Z]/p mypasswd | cut -d: -f5 | cut -d, -f1
# Explorational Exercises
##### 1. Once more using the mypasswd file from the previous exercises, devise a Bash command that will select one individual from the Main Office to win a raffle contest. Use the sed command to only print out the lines for the Main Office, and then a cut command sequence to retrieve the first name of each user from these lines. Next you will want to randomly sort these names and only print out the top name from the list.
- R: sed -n /'Main Office'/p mypasswd | cut -d: -f5 | cut -d, -f1 | sort -R | head -1
##### 2. How many people work in Finance, Engineering and Sales? (Consider exploring the uniq command.)
- R: sed -n /'Main Office'/p mypasswd | cut -d, -f2 | uniq -c
##### 3. Now you want to prepare a CSV (comma separated values) file so you can easily import, from the mypasswd file in the previous example, the file names.csv into LibreOffice. The file contents will have the following format: First Name,Last Name,Position Carol,Smith,Finance ... John,Chapel,Sales Tip: Use the sed, cut, and paste commands to achieve the desired results. Note that the comma (,) will be the delimiter for this file.
- R: 
``` bash
# Obtener nombres
sed -n '/Main Office/p' mypasswd | cut -d: -f5 | cut -d" " -f1 > firstname

# Obtener apellidos
sed -n '/Main Office/p' mypasswd | cut -d: -f5 | cut -d" " -f2 | cut -d, -f1 > lastname

# Obtener departamentos
sed -n '/Main Office/p' mypasswd | cut -d: -f5 | cut -d, -f2 > department

# Ver contenido
cat firstname lastname department
paste firstname lastname department

# Crear CSV
paste firstname lastname department | tr '\t' ,
paste firstname lastname department | tr '\t' , > names.csv
paste -d, firstname lastname department

# Solución en un comando
sed -n '/Main Office/p' mypasswd | cut -d: -f5 | cut -d, -f1,2 | tr ' ' , > names.csv
```
##### 4. Suppose that the names.csv spreadsheet created in the previous exercise is an important file and we want to make sure nobody will tamper with it from the moment we send it to someone and the moment our recipient receives it. How can we insure the integrity of this file using md5sum?
- R: md5sum file , y publicando el hash, para que la persona que lo descarga pueda comprobar que efectivamente no ha sido modificado
##### 5. You promised yourself that you would read a classic book 100 lines per day and you decided to start with Mariner and Mystic by Herman Melville. Devise a command using split that will separate this book into sections of 100 lines each. In order to get the book in plain text format, search for it at https://www.gutenberg.org.
- R:  split -l 100 -d 50461-0.txt melville
##### 6. Using ls -l on the /etc directory, what kind of listing do you get? Using the cut command on the output of the given ls command how would you display only the file names? What about the filename and the owner of the files? Along with the ls -l and cut commands, utilize the tr command to squeeze multiple occurrences of a space into a single space to aid in formatting the output with a cut command.
- R:  ls -l /etc | tr -s ' ' ,:
##### 7. This exercise assumes you are on a real machine (not a virtual machine). You must also have a USB stick with you. Review the manual pages for the tail command and find out how to follow a file as text is appended to it. While monitoring the output of a tail command on the /var/log/syslog file, insert a USB stick. Write out the full command that you would use to get the Product, Manufacturer and the total amount of memory of your USB stick.
- R:  no tengo usb no lo he hecho.
- - - 
## ***Sources:***