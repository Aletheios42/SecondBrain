**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson1
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

# Lesson2 
# Guide Exercises
##### 1. Observe the variable assignment under the "Command(s)" column and indicate if the resulting variable is "Local" or "Global":

| Command(s)                     | Local | Global |
| ------------------------------ | ----- | ------ |
| debian=mother                  | X     |        |
| ubuntu=deb-based               | X     |        |
| mint=ubuntu-based; export mint |       | X      |
| export suse=rpm-based          |       | X      |
| zorin=ubuntu-based             | X     |        |

##### 2. Study the "Command" and the "Output" and explain the meaning:

| Command           | Output                    | Meaning                                                                                  |
| ----------------- | ------------------------- | ---------------------------------------------------------------------------------------- |
| echo $HISTCONTROL | ignoreboth                | Both duplicate commands and<br>those starting with a space will not be saved in history. |
| echo ~            | /home/carol               | Thats HOME                                                                               |
| echo $DISPLAY     | reptilium:0:2             | reptilium hostanem, is on first monitor third screen                                     |
| echo $MAILCHECK   | 60                        | el correo se comprueba cada hora.                                                        |
| echo $HISTFILE    | /home/carol/.bash_history | la ruta del historial                                                                    |

##### 3. Variables are being set incorrectly under the "Wrong Command" column. Provide the missing information under "Right Command" and "Variable Reference" so that we get the "Expected Output":

| Wrong Command              | Right Command                  | Variable Reference | Expected Output    |
| -------------------------- | ------------------------------ | ------------------ | ------------------ |
| lizard =chameleon          | lizard=chameleon               | echo $lizard       | chameleon          |
| lizard=cha\|me\|leon       | lizard='cha\|me\|leon          | echo '$lizard'     | cha\|me\|leon      |
| lizard=/\** chameleon \**/ | lizard="/ \** chameleon \** /" | echo $lizard       | /\** chamelon \**/ |
| win_path=C:\path\to\dir\   | win_path='C:\\path\\to\\dir\\' | echo $win_path     | C:\path\to\dir\    |

##### 4. Consider the purpose and write the appropriate command:

| Purpose                                                                                  | Command                        |
| ---------------------------------------------------------------------------------------- | ------------------------------ |
| Set the language of the current shell to Spanish UTF-8 (es_ES.UTF-8).                    | LANG=es_ES.UTF-8               |
| Print the name of the current working directory.                                         | echo $PWD                      |
| Reference the environment variable which stores the information about ssh connections.   | echo $SSH_CONNECTION           |
| Set PATH to include /home/carol/scripts as the last directory to search for executables. | PATH=$PATH:/home/carol/scripts |
| Set the value of my_path to PATH.                                                        | my_path=PATH                   |
| Set the value of my_path to that of PATH.                                                | my_path=$PATH                  |
	
##### 5. Create a local variable named mammal and assign it the value gnu:
- R: mammal=gnu
##### 6. Using variable substitution, create another local variable named var_sub with the appropriate value so that when referenced via echo $var_sub we obtain: The value of mammal is gnu:
- R:  var_sub="the value of mammal is $mammal
##### 7. Turn mammal into an environment variable:
- R: export mammal
##### 8. Search for it with set and grep:
- R: set | grep mammal
##### 9. Search for it with env and grep:
- R: env | grep mammal
##### 10. Create, in two consecutive commands, an environment variable named BIRD whose value is penguin:
- R: BIRD=penguin; export BIRD
##### 11. Create, in a single command, an environment variable named NEW_BIRD whose value is yellow-eyed penguin:
- R: export NEW_BIRD="yellow-eyed penguin"
##### 12. Assuming you are user2, create a folder named bin in your home directory:
- R: mkdir $HOME/bin
##### 13. Type the command to add the ~/bin folder to your PATH so that it is the first directory bash searches for binaries:
- R: PATH=~/bin$PATH
##### 14. To guarantee the value of PATH remains unaltered across reboots, what piece of code — in the form of an if statement — would you put into ~/.profile?
- R: if [ -d "$HOME/bin" ] ; then
PATH="$HOME/bin:$PATH"
fi
# Explorational Exercises

##### 1. let: more than arithmetic expression evaluation:
   - Do a manpage or web search for let and its implications when setting variables and create a new local variable named my_val whose value is 10 — as a result of adding 5 and 5:
	R: my_val=$((5 + 5)) / let  "val = 5 + 5"
   - Now create another variable named your_val whose value is 5 — as a result of dividing the value of my_val into 2:
	R: let "your_val=$my_val / 2"
##### 2. The result of a command in a variable? Of course, that is possible; it is called command substitution. Investigate it and study the following function named music_info:

```bash
music_info(){
    latest_music=`ls -l1t ~/Music | head -n 6`
    echo -e "Your latest 5 music files:\n$latest_music"
}
```

The result of the command ls -l1t ~/Music | head -n 6 becomes the value of the variable latest_music. Then the variable latest_music is referenced in the echo command (which outputs the total number of bytes occupied by the Music folder and the latest five music files stored in the Music folder — one per line).

Which of the following is a valid synonym for latest_music=`ls -l1t ~/Music | head -n 6`
Option A:
latest_music=$(ls -l1t ~/Music| head -n 6)
Option B:
latest_music="(ls -l1t ~/Music| head -n 6)"
Option C:
latest_music=((ls -l1t ~/Music| head -n 6))
- R: A


# Lesson 3
##### 1. Complete the table with "Yes" or "No" considering the capabilities of aliases and functions:
- R:

| Feature                                              | Aliases? | Functions? |
| ---------------------------------------------------- | -------- | ---------- |
| Local variables can be used                          | X        | X          |
| Environment variables can be used                    | X        | X          |
| Can be escaped with \                                | X        |            |
| Can be recursive                                     | X        | X          |
| Very productive when used with positional parameters |          | X          |

##### 2. Enter the command that list all aliases in your system:
- R: alias
##### 3. Write an alias named logg that lists all ogg files in ~/Music — one per line:
- R: alias logg="ls ~/Music/*.ogg"
##### 4. Invoke the alias to prove it works:
- R:  logg
##### 5. Now, modify the alias so that it echoes out the session's user and a colon before the listing:
- R: alias logg='echo $USER:; ls -1 ~/Music/*ogg'
##### 6. Invoke it again to prove this new version also works:
- R: logg
##### 7. List all aliases again and check your logg alias appears in the listing:
- R: alias
##### 8. Remove the alias:
- R: unalias logg
##### 9. Study the columns "Alias Name" and "Aliased Command(s)" and assign the aliases to their values correctly:
- R:

| Alias Name  | Aliased Command(s)                      | Alias Assignment                                          |
| ----------- | --------------------------------------- | --------------------------------------------------------- |
| b           | bash                                    | alias b=bash                                              |
| bash_info   | which bash + echo "$BASH_VERSION"       | alias bash_info='which<br>bash; echo<br>"$BASH_VERSION"'  |
| kernel_info | uname -r                                | alias kernel_info='uname -r'                              |
| greet       | echo Hi, $USER!                         | alias greet='echo Hi, $USER!'                             |
| computer    | pc=slimbook + echo My computer is a $pc | alias computer='pc=slimbook; echo "My Computer is a $pc"' |

##### 10. As root, write a function called my_fun in /etc/bash.bashrc. The function must say hello to the user and tell them what their path is. Invoke it so that the user gets both messages every time they log in:
- R: my_fun() {
echo Hello, $USER!
echo Your path is: $PATH
}
my_fun
##### 11. Login as user2 to check it works:
- R: su - user2
##### 12. Write the same function in just one line:
- R: my_fun() { echo Hello, $USER\! echo Your path is: $PATH } 
##### 13. Invoke the function:
- R:  my_fun
##### 14. Unset the function:
- R: unset my_fun
##### 15. This is a modified version of the special_vars function:
```bash
$ special_vars2() {
> echo $#
> echo $_
> echo $1
> echo $4
> echo $6
> echo $7
> echo $_
> echo $@
> echo $?
> }
```

This is the command we use to invoke it:
```bash
$ special_vars2 crying cockles and mussels alive alive oh
```

Guess the outputs:

| Reference | Value                                     |
| --------- | ----------------------------------------- |
| echo $#   | 7                                         |
| echo $_   | 7                                         |
| echo $1   | crying                                    |
| echo $4   | mussels                                   |
| echo $6   | alive                                     |
| echo $7   | oh                                        |
| echo $_   | oh                                        |
| echo $@   | crying cockles and mussels alive alive oh |
| echo $?   | 0                                         |

##### 16. Based on the sample function (check_vids) in the section "A Function within a Function", write a function named check_music to include into a bash startup script that accepts positional parameters so that we can modify easily: the type of file being checked: ogg , the directory in which files are saved: ~/Music ,the type of file being kept: music, the number of files being saved: 7 
- R:  check_music() {
ls -1 ~/$1/*.$2 > ~/.mkv.log 2>&1
if [ "$?" = "0" ];then
echo -e "Remember, you must not keep more than $3 $4 files in your $1
folder.\nThanks."
else
echo -e "You do not have any $4 files in the $1 folder. You can keep up to
$3.\nThanks."
fi
}
check_music Music ogg 7 music
# Explorational Exercises

##### 1. Read-only functions are those whose contents we cannot modify. Do a research on readonly functions and complete the following table:

- R:

| Function Name | Make it readonly  | List all readonly Functions |
| ------------- | ----------------- | --------------------------- |
| my_fun        | readonly - my_fun | readonly -f                 |
##### 2. Search the web for how to modify PS1 and anything else you may need to write a function called fyi (to be placed in a startup script) which gives the user the following information:
◦ name of the user
◦ home directory
◦ name of the host
◦ operating system type
◦ search path for executables
◦ mail directory
◦ how often mail is checked
◦ how many shells deep the current session is
◦ prompt (you should modify it so that it shows \<user>@\<host-date>)
- R:
fyi() {
echo -e "For your Information:\n
Username: $USER
Home directory: $HOME
Host: $HOSTNAME
Operating System: $OSTYPE
Path for executable files: $PATH
Your mail directory is $MAIL and is searched every $MAILCHECK seconds.
The current level of your shell is: $SHLVL"
PS1="\u@\h-\d "
}
 fyi
- - - 

## ***Sources:***