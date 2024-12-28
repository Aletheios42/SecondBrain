**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. What is the parameter for chmod in symbolic mode to enable the sticky bit on a directory?
- R: +t
##### 2. Imagine there is a file named document.txt in the directory /home/carol/Documents. What is the command to create a symbolic link to it named text.txt on the current directory?
- R: ln -s /home/carol/Documents/text.txt text.txt
##### 3. Explain the difference between a hard link to a file and a copy of this file.
- R: una copia tiene su propoi inodo que apunta a su propio bloque que contiene los mismo bytes que otro bloque, un hard link es otra entrada al mismo inodo y al mismo bloque

# Explorational Exercises
##### 1. Imagine that inside a directory you create a file called recipes.txt. Inside this directory, you will also create a hard link to this file, called receitas.txt, and a symbolic (or soft) link to this called rezepte.txt.
```
$ touch recipes.txt
$ ln recipes.txt receitas.txt
$ ln -s recipes.txt rezepte.txt
The contents of the directory should be like so:
$ ls -lhi
total 160K
5388833 -rw-r--r-- 4 carol carol 77K jun 17 17:25 receitas.txt
5388833 -rw-r--r-- 4 carol carol
 0K jun 17 17:25 recipes.txt
5388837 lrwxrwxrwx 1 carol carol
 12 jun 17 17:25 rezepte.txt -> receitas.txt 
 ```
 Remember that, as a hard link, receitas.txt points to the same inode that recipes.txt is assigned. What would happen to the soft link rezepte.txt if the file receitas.txt is deleted? Why?
- R: dejaria de funcionar porque los soft links apunta al nombre en la tabla de directorio no al inodo, y como se habra borrado esa entrada pues el enlace simbolico seria un enlace muerto
##### 2. Imagine you have a flash drive plugged into your system, and mounted on /media/youruser/FlashA. You want to create a link called schematics.pdf in your home directory, pointing to the file esquema.pdf on the root of the flash drive. So, you type the command:
```
$ ln /media/youruser/FlashA/esquema.pdf ~/schematics.pdf
```
What would happen? Why?
-R: tendrias que crear un enlace simbolico los enlaces duros no pueden traspasar diferentes sistemas de archivo
##### 3. Consider the following output of ls -lah:
```
$ ls -lah
total 3,1M
drwxr-xr-x 2 carol carol 4,0K jun 17 17:27 .
drwxr-xr-x 5 carol carol 4,0K jun 17 17:29 ..
-rw-rw-r-- 1 carol carol 2,8M jun 17 15:45 compressed.zip
-rw-r--r-- 4 carol carol
 77K jun 17 17:25 document.txt
-rw-rw-r-- 1 carol carol 216K jun 17 17:25 image.png
-rw-r--r-- 4 carol carol
 77K jun 17 17:25 text.txt
 ```
◦ How many links point to the file document.txt?
R: 4 -1 = 3
◦ Are they soft or hard links?
R:  hardlinks, los enlaces simbolicos no se cuentan ahi
◦ Which parameter should you pass to ls to see which inode each file occupies?
 R: -i
##### 4. Imagine you have in your ~/Documents directory a file named clients.txt containing some client names, and a directory named somedir. Inside this there is a different file also named clients.txt with different names. To replicate this structure, use the following commands.
```
$ cd ~/Documents
$ echo "John, Michael, Bob" > clients.txt
$ mkdir somedir
$ echo "Bill, Luke, Karl" > somedir/clients.txt
```
You then create a link inside somedir named partners.txt pointing to this file, with the commands:
```
$ cd somedir/
$ ln -s clients.txt partners.txt
```
So, the directory structure is:
```
Documents
|-- clients.txt
`-- somedir
|-- clients.txt
`-- partners.txt -> clients.txt
```
Now, you move partners.txt from somedir to ~/Documents, and list its contents.
```
$ cd ~/Documents/
$ mv somedir/partners.txt .
$ less partners.txt
```
Will the link still work? If so, which file will have its contents listed? Why?
- R: apunta al otro client.txt
##### 5. Consider the following files:
``` 
-rw-r--r-- 1 carol carol 19 Jun 24 11:12 clients.txt
lrwxrwxrwx 1 carol carol 11 Jun 24 11:13 partners.txt -> clients.txt
```
What are the access permissions for partners.txt? Why?
- R: los permisos se heredan asi que -rw-r--r--

- - - 
## ***Sources:***