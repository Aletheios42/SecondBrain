**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. How can the previously locked account emma be unlocked?
- R: The superuser can run passwd -u emma to unlock the account.
##### 2. Previously the account emma had an expiration date set. How can the expiration date get set to never?
- R:  The superuser may use chage -E -1 emma to set the expiration date to never. This setting may be checked with chage -l emma.
##### 3. Imagine the CUPS printing service handling print jobs is not needed on your server. How can you disable the service permanently? How can you check the appropriate port is not active anymore?
- R:
```
As superuser issue
systemctl disable cups.service --now
Now you can check
netstat -l | grep ":ipp "` or `ss -l | grep ":ipp "
```
##### 4. You have installed the nginx web server. How can you check whether nginx supports TCP wrappers?
- R: ldd /usr/sbin/nginx | grep "libwrap"
# Explorational Exercises
##### 1. Check out whether the existence of the /etc/nologin file prevents the login of the user root?
- R: User root is still able to login.
##### 2. Does the existence of the /etc/nologin file prevent passwordless logins with SSH keys?
- R: Yes, also passwordless logins are prevented.
##### 3. What happens on login, when the file /etc/nologin contains this line of text login currently is not possible only?
- R: The message login currently is not possible will be shown, and a login is prevented.
##### 4. May an ordinary user emma obtain information about the user root contained in the file /etc/passwd e.g. with the command grep root /etc/passwd?
- R: Yes, because all users have read permission for this file.
##### 5. May an ordinary user emma retrieve information about her own hashed password contained in the file /etc/shadow e.g. with the command grep emma /etc/shadow?
- R: No, because ordinary users have no read permission for this file.
##### 6. What steps have to be taken to enable and check the ancient daytime service to be handled by xinetd? Note this is just an explorational excercise don’t do this in a production environment.
- R: First change the file /etc/xinetd.d/daytime and set the directive disable = no. Second restart the xinetd service systemctl restart xinetd.service (or service xinetd restart on systems with SyS-V-Init). Now you can check whether it works nc localhost daytime. Instead of nc you may also use netca

- - - 
## ***Sources:***