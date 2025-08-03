**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. Create a directory named emptydir using the command mkdir emptydir. Now, using ls, list the permissions for the directory emptydir.
- R: ls -l -d emptydir
##### 2. Create an empty file named emptyfile with the command touch emptyfile. Now, using chmod in symbolic mode, add execute permissions for the owner of the file emptyfile, and remove write and execute permissions for everyone else. Do this using only one chmod command.
- R: chmod u+x,go-wx emptyfile
##### 3. What would the default permissions for a file be if the umask value is set to 027?
- R:  rw-r-----
##### 4. Let us assume a file named test.sh is a shell script with the following permissions and ownership:
```
-rwxr-sr-x 1 carol root
 33 Dec 11 10:36 test.sh
 ```
◦ What are the permissions for the owner of the file?
R: rwx
◦ Using the octal notation, what would the syntax of chmod be to “unset” the special permission granted to this file?
R: 0755
##### 5. Consider this file:
```
$ ls -l /dev/sdb1
brw-rw---- 1 root disk 8, 17 Dec 21 18:51 /dev/sdb1
```
Which type of file is sdb1? Who can write to it?
- R: block device, root.
##### 6. Consider the following 4 files:
```
drwxr-xr-t 2 carol carol 4,0K Dec 20 18:46 Another_Directory
----r--r-- 1 carol carol
 0 Dec 11 10:55 foo.bar
-rw-rw-r-- 1 carol carol 1,2G Dec 20 18:22 HugeFile.zip
drwxr-sr-x 2 carol users
 4,0K Jan 18 17:26 Sample_Directory
```
Write down the corresponding permissions for each file and directory using octal mode using the 4-digit notation.
Another_Directory ---> 1755
foo.bar ---> 0044
HugeFile.zip ---> 0664
Sample_Directory ---> 2755
# Explorational Exercises
##### 1. Try this on a terminal: create an empty file called emptyfile with the command touch emptyfile. Now “zero out” the permissions for the file with chmod 000 emptyfile. What will happen if you change the permissions for emptyfile by passing only one value for chmod in octal mode, like chmod 4 emptyfile? And if you use two, as in chmod 44 emptyfile? What can we learn about the way chmod reads the numerical value?
- R:  que parsea el numero completo y pone 0 si no se especifica el digito.
##### 2. Consider the permissions for the temporary directory on a Linux system, /tmp:
```
$ ls -l /tmp
drwxrwxrwt
 19 root root
 16K Dec 21 18:58 tmp
```
User, group and others have full permissions. But can a regular user delete any files inside this directory? Why is this the case?
- R: sticky bit is on so only the owner can delete
##### 3. A file called test.sh has the following permissions: -rwsr-xr-x, meaning the SUID bit is set. Now, run the following commands:
```
$ chmod u-x test.sh
$ ls -l test.sh
-rwSr-xr-x 1 carol carol 33 Dec 11 10:36 test.sh
```
What did we do? What does the uppercase S mean?
- R: que tiene permiso SUID pero no se puede ejecutar.
##### 4. How would you create a directory named Box where all the files are automatically owned by the group users, and can only be deleted by the user who created them?
- R: $ chown :users Box/
$ chmod g+wxs Box/
 chmod o+t Box/
 $ chmod g+wxs,o+t Box/

- - - 
## ***Sources:***