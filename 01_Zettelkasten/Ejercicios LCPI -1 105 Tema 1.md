**Tags:** #_Todo
#ToTag #ToLink 
- - -
# Guided Exercises
##### 1. Study how the shells have been started under the column “Shell Started with…” and complete with the required information:

- R:

| Shell Started with...                                      | Interactive? | Login? | Result of echo $0 |
| ---------------------------------------------------------- | ------------ | ------ | ----------------- |
| sudo ssh user2@machine2                                    | Yes          | Yes    | -bash             |
| Ctrl + Alt + F2                                            | Yes          | Yes    | -bash             |
| su - user2                                                 | Yes          | Yes    | -bash             |
| gnome-terminal                                             | Yes          | No     | bash              |
| A regular user uses konsole to start an instance of sakura | Yes          | No     | bash              |
| A script named test.sh containing the command echo $0      | No           | No     | test.sh           |
2. Write the su and sudo commands to launch the specified shell:
Interactive-login shell as user2
su:  su - user2, su -l user2 or su --login user2
sudo: sudo su - user2,sudo su -l user2 or sudo su --login user2
Interactive login shell as root
su: su -root or su -
sudo:  sudo su - root,sudo su - or sudo -i
Interactive non-login shell as root
su: sudo root or su
sudo: sudo su root, sudo su, sudo -s or sudo -u root -s
Interactive non-login shell as user2
su: su user2
sudo: sudo su user2 or sudo -u user2 -s

3. What startup file gets read when the shell under “Shell Type” is started?

- R:

| Shell Type       | Interactive-login shell as user2 | Interactive login shell as root | Interactive non-login shell as root | Interactive non-login shell as user2 |
| ---------------- | -------------------------------- | ------------------------------- | ----------------------------------- | ------------------------------------ |
| /etc/profile     | Yes                              | Yes                             | No                                  | No                                   |
| /etc/bash.bashrc | Yes                              | Yes                             | Yes                                 | Yes                                  |
| ~/.profile       | Yes                              | Yes                             | No                                  | No                                   |
| ~/.bashrc        | Yes                              | Yes                             | Yes                                 | Yes                                  |
# Explorational Exercises
##### 1. In Bash we can write a simple Hello world! function by including the following code in an empty file:
```
function hello() {
echo "Hello world!"
}
```
◦ What should we do next to make the function available to the shell?
R: source file
◦ Once it is available to the current shell, how would you invoke it?
R:  calling function name
◦ To automate things, in what file would you put the function and its invocation so that it gets executed when user2 opens a terminal from an X Window session? What type of shell is it?
R: /home/user2/.bashrc
◦ In what file would you put the function and its invocation so that it is run when root launches a new interactive shell irrespective of whether it is login or not?
R: /etc/bash.bashrc
##### 2. Have a look at the following basic, Hello world! bash script:
```
#!/bin/bash #hello_world: a simple bash script to discuss interaction in scripts. echo "Hello world!"
```
◦ Suppose we make the script executable and run it. Would that be an interactive script? Why?
R:  No , el usuario no tiene que pulsar ninguna tecla ni nada.
◦ What makes a script interactive?
R: que necesite de un input enviado por el usuario
##### 3. Imagine you have changed the values of some variables in ~/.bashrc and want those changes to take effect without a reboot. From your home directory, how could you achieve that in two different ways?
- R: source/. .bashrc
##### 4. John has just started an X Window session on a Linux server. He opens a terminal emulator to carry out some administrative tasks but, surprisingly, the session freezes and he needs to open a text shell.
◦ How can he open that tty shell?
R: ctrl+atl+f1..6
◦ What startup files will get sourced?
 R: /etc/profile y /home/john/.profile
##### 5. Linda is a user of a Linux server. She kindly asks the administrator to have a ~/.bash_login file so she can have the time and date printed on the screen when she logs in. Other users like the idea and follow suit. The administrator has a hard time creating the file for all other users on the server so he decides to add a new policy and have ~/.bash_login created for all potential new users. How can the administrator accomplish that task?
 - R:  puede poner en etc/skel el .bash_login
- - - 
## ***Sources:***