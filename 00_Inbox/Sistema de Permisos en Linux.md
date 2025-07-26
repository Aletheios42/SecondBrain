**MetaTags:** #_Todo
**Tags:** #Linux #ToLink 
- - -
==Enlazar con las notas de permisos==
User accounts are defined in the /etc/passwd.
Groups are defined in the /etc/group
 /etc/shadow which holds information about the user's
password. 
Reading, Writing, and Executing
Access rights to files and directories are defined in terms of read access, write access, and
execution access. 

Owner
 Group
 World
rwx
 rwx
 rwx
Table 9-2 describes the effect the r, w, and x mode attributes have on files and directo-
ries:
Table 9-2: Permission Attributes
Attribute
 Files
r
 Allows a file to be opened and
read.
w
x
Allows a file to be written to or
truncated, however this attribute
does not allow files to be
renamed or deleted. The ability
to delete or rename files is
determined by directory
attributes.
Allows a file to be treated as a
program and executed. Program
files written in scripting
languages must also be set as
readable to be executed.
Directories
Allows a directory's contents to
be listed if the execute attribute
is also set.
Allows files within a directory
to be created, deleted, and
renamed if the execute attribute
is also set.
Allows a directory to be
entered, e.g., cd directory.

## Changing Identities
mirar
- - - 
## ***Sources:***