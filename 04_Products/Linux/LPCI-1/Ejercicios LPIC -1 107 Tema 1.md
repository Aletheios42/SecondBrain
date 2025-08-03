**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson 1
# Guided Exercises
##### 1. For each of the following commands, identify the corresponding purpose:
- R:

| Command     | Purpose                              |
| ----------- | ------------------------------------ |
| usermod -L  | Lock user account                    |
| passwd -u   | Unlock user password                 |
| chage -E    | Set account expiration date          |
| groupdel    | Delete a group                       |
| useradd -s  | Set user's login shell               |
| groupadd -g | Create group with specific GID       |
| userdel -r  | Delete user and their home directory |
| usermod -l  | Change username (login name)         |
| groupmod -n | Rename a group                       |
| useradd -m  | Create user with home directory      |
##### 2. For each of the following passwd commands, identify the corresponding chage command:
- R:

| passwd Command | Equivalent chage Command | Purpose                   |
| -------------- | ------------------------ | ------------------------- |
| passwd -n      | chage -m                 | Set minimum password age  |
| passwd -x      | chage -M                 | Set maximum password age  |
| passwd -w      | chage -W                 | Set password warning days |
| passwd -i      | chage -I                 | Set password inactivity   |
| passwd -S      | chage -l                 | Display password status   |
##### 3. Explain in detail the purpose of the commands in the previous question:
- R:  Done in the table colum purpose
##### 4. What commands can you use to lock a user account? And which commands to unlock it?
To lock: usermod -L, usermod --lock and passwd -l.
To unlock: usermod -U, usermod --unlock and passwd -u.

# Explorational Exercises
##### 1. Using the groupadd command, create the administrators and developers groups. Assume you are working as root.
- R:   groupadd administrators; groupadd developers
##### 2. Now that you have created these groups, run the following command: useradd -G administrators,developers kevin. What operations does this command perform? Assume that CREATE_HOME and USERGROUPS_ENAB in /etc/login.defs are set to yes.
- R:  creates a new group, named kevin, as the primary group of this user ,  files and folders contained in the skeleton directory are copied to the home dir of kevin.
##### 3. Create a new group named designers, rename it to web-designers and add this new group to the secondary groups of the kevin user account. Identify all the groups kevin belongs to and their IDs.
- R: 
``` bash
groupadd designers
 groupmod -n web-designers designers
 usermod -a -G web-designers kevin
 id kevin
uid=1010(kevin) gid=1030(kevin)
groups=1030(kevin),1028(administrators),1029(developers),1031(web-designers)
```
##### 4. Remove only the developers group from the secondary groups of kevin.
- R:   usermod -G administrators,web-designers kevin
##### 5. Set the password for the kevin user account.
- R:   passwd kevin
##### 6. Using the chage command, first check the expiry date of the kevin user account and then change it to December 31st 2022. What other command can you use to change the expiration date of a user account?
- R:
 ``` bash
 chage -l kevin | grep "Account expires"
Account expires
: never
chage -E 2022-12-31 kevin
chage -l kevin | grep "Account expires"
Account expires
 : dec 31, 2022#
 ```
##### 7. Add a new user account named emma with UID 1050 and set administrators as its primary group and developers and web-designers as its secondary groups.
 - R:
 ``` bash
useradd -u 1050 -g administrators -G developers,web-designers emma
id emma
uid=1050(emma) gid=1028(administrators)
groups=1028(administrators),1029(developers),1031(web-designers)
 ```
##### 8. Change the login shell of emma to /bin/sh.
- R:  usermod -s /bin/sh emma
##### 9. Delete the emma and kevin user accounts and the administrators, developers and web- designers groups.
- R:  userdel -r emma kevin; groupdel administrators developers web-designers
# Lesson2 
# Guided Exercises
##### 1. Observe the following output and answer the following questions:
```
# cat /etc/passwd | grep '\(root\|mail\|catherine\|kevin\)'
root:x:0:0:root:/root:/bin/bash
mail:x:8:8:mail:/var/spool/mail:/sbin/nologin
catherine:x:1030:1025:User Chaterine:/home/catherine:/bin/bash
kevin:x:1040:1015:User Kevin:/home/kevin:/bin/bash

# cat /etc/group | grep '\(root\|mail\|db-admin\|app-developer\)'
root:x:0:
mail:x:8:
db-admin:x:1015:emma,grace
app-developer:x:1016:catherine,dave,christian

# cat /etc/shadow | grep '\(root\|mail\|catherine\|kevin\)'
root:$6$1u36Ipok$ljt8ooPMLewAhkQPf.lYgGopAB.jClTO6ljsdczxvkLPkpi/amgp.zyfAN680zrLLp2avvpd
KA0llpssdfcPppOp:18015:0:99999:7:::
mail:*:18015:0:99999:7:::
catherine:$6$ABCD25jlld14hpPthEFGnnssEWw1234yioMpliABCdef1f3478kAfhhAfgbAMjY1/BAeeAsl/FeE
dddKd12345g6kPACcik:18015:20:90:5:::
kevin:$6$DEFGabc123WrLp223fsvp0ddx3dbA7pPPc4LMaa123u6Lp02Lpvm123456pyphhh5ps012vbArL245.P
R1345kkA3Gas12P:18015:0:60:7:2::

# cat /etc/gshadow | grep '\(root\|mail\|db-admin\|app-developer\)'
root:*::
mail:*::
db-admin:!:emma:emma,grace
app-developer:!::catherine,dave,christian
```
◦ What is the User ID (UID) and the Group ID (GID) of root and catherine?
R:  root--> 0:0  catherine-->1030:1025 
◦ What is the name of the primary group of kevin? Are there other members in this group?
R: 1015->db-admin
◦ Which shell is set for mail? What does it mean?
R: Nologin , it means it s not meant ot be use by humans but programs  or scripts
◦ Who are the members of the app-developer group? Which of these members are group administrators and which are ordinary members?
R:  catherine dave cristian
◦ What is the minimum password lifetime for catherine? And what is the maximum password lifetime?
R: 20
◦ What is the password inactivity period for kevin?
R: 2
##### 2. By convention, which IDs are assigned to system accounts and which to ordinary users?
 -R: >1000
##### 3. How do you find out if a user account, which was previously able to access the system, is now locked? Assume your system uses shadow passwords.
- R: in /etc/passwd second field with  a !
# Explorational Exercises
##### 1. Create a user account named christian using the useradd -m command and identify its User ID (UID), Group ID (GID) and shell.
- R:
```
useradd -m christian
# cat /etc/passwd | grep christian
christian:x:UID:GID::/home/christian:/bin/bash
```
##### 2. Identify the name of the primary group of christian. What can you deduce?
 - R: The name of the primary group of christian is christian (the first field in /etc/group).
Therefore, USERGROUPS_ENAB in /etc/login.defs is set to yes so that useradd creates by
default a group with the same name of the user account.
##### 3. Using the getent command, review password aging information for the christian user account.
- R: 
```
# getent shadow christian
christian:!:18015:0:99999:7:::
```
The christian user account does not have the password set and is now locked (the second
field in /etc/shadow contains an exclamation mark). There is no minimum and maximum
password age for this user account (the fourth and fifth fields in /etc/shadow are set to 0 and
99999 days), while the password warning period is set to 7 days (the sixth field in
/etc/shadow). Finally, there is no inactivity period (the seventh field in /etc/shadow) and the
account never expires (the eighth field in /etc/shadow).
##### 4. Add the editor group to the secondary groups of christian. Assume that this group already contains emma, dave and frank as ordinary members. How can you verify that there are no administrators for this group?
- R:
```
# cat /etc/group | grep editor
editor:x:1100:emma,dave,frank
# usermod -a -G editor christian
# cat /etc/group | grep editor
editor:x:1100:emma,dave,frank,christian
# cat /etc/gshadow | grep editor
editor:!::emma,dave,frank,christian
```
The third and fourth fields in /etc/ghadow contain administrators and ordinary members for
the specified group. Therefore, since the third field is empty for editor, there are no
administrators for this group (emma, dave, frank and christian are all ordinary members).
##### 5. Run the ls -l /etc/passwd /etc/group /etc/shadow /etc/gshadow command and describe the output that it gives you in terms of file permissions. Which of these four files are shadowed for security reasons? Assume your system uses shadow passwords.
- R: 
The /etc/passwd and /etc/group files are world readable and are shadowed for security
reasons. When shadow passwords are used, you can see an x in the second field of these files,
because the encrypted passwords for users and groups are stored in /etc/shadow and
/etc/gshadow, which are readable only by root and, in my system, even by members
belonging to the shadow group.

- - - 
## ***Sources:***