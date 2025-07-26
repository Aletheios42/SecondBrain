**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. Complete the following table regarding special permissions:
- R:

| Special Permission | Numeric Rep | Symbolic Rep | Find Command to Locate Files |
| ------------------ | ----------- | ------------ | ---------------------------- |
| SUID               | 4000        | u+s          | `find / -perm -4000`         |
| SGID               | 2000        | g+s          | `find / -perm -2000`         |
##### 2. Displaying files with only the SUID or SGID bit set is normally not very practical. Perform the following tasks to prove that your searches can be more productive:
◦ Find all files with the SUID (and other permissions) set in /usr/bin:
R: find /usr/bin -perm -4000 or find /usr/bin -perm -u+s
◦ Find all files with the SGID (and other permissions) set in /usr/bin:
R: find /usr/bin -perm -2000 or find /usr/bin -perm -g+s
◦ Find all files with either the SUID or the SGID set in /usr/bin:
R:  find /usr/bin -perm /6000
##### 3. chage lets you change a user’s password expiry information. As root, complete the following table by providing the correct commands on user mary:
- R:

| Meaning                                                         | chage Command                       |
| --------------------------------------------------------------- | ----------------------------------- |
| Make password valid for 365 days                                | `chage -M 365 username`             |
| Make user change password on next login                         | `chage -d 0 username`               |
| Set minimum days between password changes to 1                  | `chage -m 1 username`               |
| Disable password expiration                                     | `chage -M -1 username`              |
| Enable user to change password anytime                          | `chage -m 0 username`               |
| Set warning period to 7 days and account expiry to Aug 20, 2050 | `chage -W 7 -E 2050-08-20 username` |
| Print user's password expiry info                               | `chage -l username`                 |

##### 4. Complete the following table with the appropriate network utility:
- R:

| Action                                                         | Command                       |
| -------------------------------------------------------------- | ----------------------------- |
| Show network files for host 192.168.1.55 on port 22 using lsof | `lsof -i @192.168.1.55:22`    |
| Show processes accessing the default port of Apache web server | `fuser -n tcp 80`             |
| List all listening UDP sockets                                 | `netstat -lu`                 |
| Scan ports 80-443 on host 192.168.1.55                         | `nmap -p 80-443 192.168.1.55` |
##### 5. Perform the following tasks concerning resident set size (RSS) and ulimit as a regular user:
◦ Display soft limits on the maximum RSS:
R: ulimit -m, ulimit -Sm
◦ Display hard limits on the maximum RSS:
R:  ulimit -Hm
◦ Set the soft limits on the maximum RSS to 5,000 kilobytes:
R:  ulimit -Sm 5000
◦ Set the hard limits on the maximum RSS to 10,000 kilobytes:
R:  ulimit -Hm 10000
◦ Finally, try to increase the hard limit on the maximum RSS up to 15,000 kilobytes. Can you do it? Why?
R:  No. Once set, regular users cannot increase hard limits.
##### 6. Consider the following last command output line and answer the questions:
```
carol
 pts/0
 192.168.1.4
 Sun May 31 14:16 - 14:22
 (00:06)
 ```
◦ Was carol connected from a remote host? Why?
R:  Yes, the IP address of the remote host is in the third column.
◦ How long did carol's session last?
R: Six minutes (as shown in the last column).
◦ Was carol connected through a true classic text-based terminal? Why?
R:  No, pts/0 in the second column indicates the connection was made through a graphical terminal emulator (aka Pseudo Terminal Slave).
##### 7. Consider the following excerpt from /etc/sudoers and answer the question below.
```
# Host alias specification
Host_Alias SERVERS = 192.168.1.7, server1, server2
# User alias specification
User_Alias REGULAR_USERS = john, mary, alex
User_Alias PRIVILEGED_USERS = mimi
User_Alias ADMINS = carol, %sudo, PRIVILEGED_USERS, !REGULAR_USERS
# Cmnd alias specification
Cmnd_Alias WEB_SERVER_STATUS = /usr/bin/systemctl status apache2
# User privilege specification
root
 ALL=(ALL:ALL) ALL
ADMINS
 SERVERS=WEB_SERVER_STATUS
# Allow members of group sudo to execute any command
%sudo
 ALL=(ALL:ALL) ALL
```
Can alex check the status of the Apache Web Server on any host? Why?
- R: No, as he is a member of REGULAR_USERS and that group of users is excluded from ADMINS; the only users (apart from carol, members of the sudo group and root) that can run systemctl status apache2 on the SERVERS.

# Explorational Exercises
##### 1. Apart from the SUID and SGID, there is a third special permission: the sticky bit. At present it is mostly used on directories such as /tmp to prevent regular users from deleting or moving files other than their own. Do the following tasks:
◦ Set the sticky bit on ~/temporal:
R: chmod +t temporal, chmod 1755 temporal
◦ Find directories with the sticky bit (and any other permissions) set on your home directory:
R:  find ~ -perm -1000, find ~ -perm /1000
◦ Unset the sticky bit on ~/temporal:
R:  chmod -t temporal, chmod 0755 temporal
##### 2. When a user’s password is locked via passwd -l username or usermod -L username, how can you tell by looking into /etc/shadow?
- R: An exclamation mark will appear in the second field, right after the login name of the affected user (e.g.: mary:!$6$gOg9xJgv…). 
##### 3. What is the usermod command counterpart to chage -E date  username or chage --expiredate date username?
- R:  usermod -e date username, usermod --expiredate date username
##### 4. Provide two different nmap commands to scan all 65535 ports on localhost:
- R:  nmap -p 1-65535 localhost and nmap -p- localhost
- - - 
## ***Sources:***