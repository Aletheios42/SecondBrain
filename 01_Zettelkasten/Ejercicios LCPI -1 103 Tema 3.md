**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson 1
# Guided Exercises
###### 1. Consider the listing below:
$ ls -lh
total 60K
drwxr-xr-x 2 ¡ 2  frank frank 4.0K Apr 1 2018 Desktop
drwxr-xr-x 2 frank frank 4.0K Apr 1 2018 Documents
drwxr-xr-x 2 frank frank 4.0K Apr 1 2018 Downloads
-rw-r--r-- 1 frank frank 21 Sep 7 12:59 emp_name
-rw-r--r-- 1 frank frank 20 Sep 7 13:03 emp_salary
-rw-r--r-- 1 frank frank 8.8K Apr 1 2018 examples.desktop
-rw-r--r-- 1 frank frank 10 Sep 1 2018 file1
I-rw-r--r-- 1 frank frank 10 Sep 1 2018 file2
drwxr-xr-x 2 frank frank 4.0K Apr 1 2018 Music
drwxr-xr-x 2 frank frank 4.0K Apr 1 2018 Pictures 
drwxr-xr-x 2 frank frank 4.0K Apr 1 2018 Public
drwxr-xr-x 2 frank frank 4.0K Apr 1 2018 Templates
drwxr-xr-x 2 frank frank 4.0K Apr 1 2018 Videos

◦ What does the character d represent in the output?
R: -d == --directory
◦ Why are the sizes given in human readable format?
R: -h == --human
◦ What would be the difference in the output if ls was used with no argument?
R: claro, solo habria nombres, sin la linea de espacio total, y se añadiria el directorio alcutal y su contenedor " ., .. "
##### 2. Consider the command below: $ cp /home/frank/emp_name /home/frank/backup
◦ What would happen to the file emp_name if this command is executed successfully?
R: nada
◦ If emp_name was a directory what option should be added to cp to execute the command?
R: -r == --recursive
◦ If cp is now changed to mv what results do you expect?
R: pues que lo moveria de carpeta y lo cambiaria de nombre.
##### 3. Consider the listing :
$ ls
file1.txt file2.txt file3.txt file4.txt
Which wildcard would help to delete all the contents of this directory?
- R: rm file\[1..4].txt
4. Based on the previous listing, what files would be displayed by the following command?
$ ls file*.txt
- R: todos 
5. Complete the command by adding the appropriate digits and characters in the square brackets
that would list all the content above:
$ ls file[1..4].txt
# Explorational Exercises
##### 1. In your home directory, create the files called dog and cat.
- R: touch ~/{dog,cat}
##### 2. Still in your home directory, create the directory called animal. Move dog and cat into animal.
- R:  mkdir ~/animal && mv ~/{dog,cat} ~/animal/
##### 3. Go to the Documents folder found in your home directory and inside, create the directory backup.
- R: (cd /Docmunets && mkdir backup)
##### 4. Copy animal and its contents into backup.
- R: cp -r animal /Document/backup/.
##### 5. Rename animal in backup to animal.bkup.
- R: mv /Document/backup /Document animal.bkup
##### 6. The /home/lpi/databases directory contains many files which includes: db-1.tar.gz, db- 2.tar.gz and db-3.tar.gz. Which single command can you use to list only the files mentioned above?
- R: ls /home/lpi/databases/db-\[1..3].tar.gz
###### 7. Consider the listing:
$ ls
cne1222223.pdf cne12349.txt cne1234.pdf
With the use of a single globbing character, what command would remove only the pdf files?
- R: rm *.pdf

# Lesson 2
# Guided Exercises
##### 1. Consider the following listing:
$ find /home/frank/Documents/ -type d
/home/frank/Documents/
/home/frank/Documents/animal
/home/frank/Documents/animal/domestic
/home/frank/Documents/animal/wild
◦ What kind of files would this command output?
- R: directory
◦ In which directory does the search begin?
- R: por orden asi que /home/frank/Documents
##### 2. A user wishes to compress his backup folder. He uses the following command:
$ tar cvf /home/frank/backup.tar.gz /home/frank/dir1 
Which option is lacking to compress the backup using the gzip algorithm?
- R: -z
# Explorational Exercises
##### 1. As system administrator, it is required to perform regular checks in order to remove
voluminous files. These voluminous files are located in /var and end with a .backup
extension.
◦ Write down the command, using find, to locate these files:
R:  find /var -name *.backup
◦ An analysis of the sizes of these files reveals that they range from 100M to 1000M. Complete the previous command with this new information, so that you may locate those backup files ranging from 100M to 1000M:
R:  find /var -name *.backup -size +100M -size -1000M
◦ Finally, complete this command, with the delete action so that these files will be removed:
- R: find /var -name *.backup -size +100M -size -1000M -delete
 ##### 2.In the /var directory, there exist four backup files:
db-jan-2018.backup
db-feb-2018.backup
db-march-2018.backup
db-apr-2018.backup
◦ Using tar, specify the command that would create an archive file with the name db-first-
quarter-2018.backup.tar:
R: $ tar -cvf db-first-quarter-2018.backup.tar db-jan-2018.backup db-feb-2018.backup db-march-2018.backup db-apr-2018.backup
◦ Using tar, specify the command that would create the archive and compress it using gzip. Take note that the resulting file name should end with .gz:
R:  tar -zcvf db-first-quarter-2018.backup.tar.gz db-jan-2018.backup db-feb-2018.backup
- - - 
## ***Sources:***