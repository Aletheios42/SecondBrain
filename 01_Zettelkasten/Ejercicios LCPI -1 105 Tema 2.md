**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson1
# Guided Exercises
##### 1. The -s option for the read command is useful for entering passwords, as it will not show the content being typed on the screen. How could the read command be used to store the user’s input in the variable PASSWORD while hiding the typed content?
- R:  read -s PASSWORD
##### 2. The only purpose of the command whoami is to display the username of the user who called it, so it is mostly used inside scripts to identify the user who is running it. Inside a Bash script, how could the output of the whoami command be stored in the variable named WHO?
- R: who='whoami' or who=$(whoami)
##### 3. What Bash operator should be between the commands apt-get dist-upgrade and systemctl reboot if the root user wants to execute systemctl reboot only if apt-get dist-upgrade finished successfully?
- R:  apt-get dist-upgrade && systemctl reboot

# Explorational Exercises
##### 1. After trying to run a newly created Bash script, a user receives the following error message\:bash: ./script.sh: Permission denied Considering that the file ./script.sh was created by the same user, what would be the probable cause of this error?
- R: chmod +x script.sh
##### 2. Suppose a script file named do.sh is executable and the symbolic link named undo.sh points to it. From within the script, how could you identify if the calling filename was do.sh or undo.sh?
- R: special variable $0
##### 3. In a system with a properly configured email service, the command mail -s "Maintenance Error" root <<<"Scheduled task error" sends the notice email message to the root user. Such a command could be used in unattended tasks, like cronjobs, to inform the system administrator about an unexpected issue. Write an if construct that will execute the aforementioned mail command if the exit status of the previous command — whatever it was — is unsuccessful.
- R:  if [ "$?" -ne 0 ]; then mail -s "Maintenance Error" root <<<"Scheduled task
error"; fi

# Lesson2
# Guided Exercises
##### 1. How could command test be used to verify if the file path stored in the variable FROM is newer than a file whose path is stored in the variable TO?
- R:  test "\$FROM" -nt "$TO"
##### 2. The following script should print a number sequence from 0 to 9, but instead it indefinitely prints 0. What should be done in order to get the expected output?
```
#!/bin/bash
COUNTER=0
while [ $COUNTER -lt 10 ]
do
echo $COUNTER
done
```
- R:   \$COUNTER=\$((\$COUNTER + 1))
##### 3. Suppose a user wrote a script that requires a sorted list of usernames. The resulting sorted list is presented as the following on his computer:
```
carol
Dave
emma
Frank
Grace
henry
```
However, the same list is sorted as the following on his colleague’s computer:
```
Dave
Frank
Grace
carol
emma
henry
```
What could explain the differences between the two sorted lists?
- R: sorting depends on LANG selected, however this error could be avoided by using sort -f

# Explorational Exercises
##### 1. How could all of the script’s command line arguments be used to initialize a Bash array?
- R: PARAMS=( $* ) or PARAMS=( "\$@" )
##### 2. Why is it that, counter intuitively, the command test 1 > 2 evaluates as true?
- R: you cant use > with numbers
##### 3. How would a user temporarily change the default field separator to the newline character only, while still being able to revert it to its original content?
- R: with IFS=$'\n' and the IFS variable can be reverted back with
IFS=$OLDIFS.
- - - 
## ***Sources:***