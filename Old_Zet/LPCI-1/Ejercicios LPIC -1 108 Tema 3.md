**Tags:** #_Done 
#Linux #ToLink 
- - -
# Guided Exercises
##### 1. Without further options or arguments, the command mail henry\@lab3.campus enters the input mode so the user can type the message to henry\@lab3.campus. After finishing the message, which keystroke will close the input mode and dispatch the email?
- R: ctrl+D
##### 2. Which command can the root user execute to list the undelivered messages that originated on the local system?
- R: sendmail -bp
##### 3. How can an unprivileged user use the standard MTA method to automatically forward all of their incoming mail to the address dave\@lab2.campus?
- R: ~/.forwards
# Explorational Exercises
##### 1. Using the mail command provided by mailx, what command will send a message to emma\@lab1.campus with the file logs.tar.gz as an attachment and the output of the command uname -a as the email body?
- R: uname -a | mail -a logs.tar.tz emma\@lab1.campus
##### 2. An email service administrator wants to monitor email transfers through the network, but they don’t want to clutter their mailbox with test messages. How could this administrator configure a system-wide email alias to redirect all email sent to the user test to the file /dev/null?
- R: write line test: /dev/null in file: /etc/aliases
##### 3. What command, besides newaliases, could be used to update the aliases database after adding a new alias to /etc/aliases?
- R: sendmail -bi or sendmail -I

- - - 
## ***Sources:***