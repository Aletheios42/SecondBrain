**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. Based on the following output of the command date, what is the time zone of the system in GMT notation? $ date Mon Oct 21 18:45:21 +05 2019
 - R: Etc/GMT+5 
##### 2. To what file should the symbolic link /etc/localtime point to in order to make Europe/Brussels the system’s default local time?
 - R: The link /etc/localtime should point to /usr/share/zoneinfo/Europe/Brussels.
##### 3. Characters in text files may not be rendered correctly in a system with a character encoding different from that used in the text document. How could iconv be used to convert the WINDOWS-1252 encoded file old.txt to the file new.txt using UTF-8 encoding?
- R:  Command iconv -f WINDOWS-1252 -t UTF-8 -o new.txt old.txt will perform the
desired conversion.

# Explorational Exercises
##### 1. What command will make Pacific/Auckland the default time zone for the current shell session?
- R:  export TZ=Pacific/Auckland
##### 2. Command uptime shows, among other things, the load average of the system in fractional numbers. It uses the current locale settings to decide if the decimal place separator should be a dot or a comma. If, for example, the current locale is set to de_DE.UTF-8 (the standard locale of Germany), uptime will use a comma as the separator. Knowing that in the American English language the dot is used as the separator, what command will make uptime display the fractions using a dot instead of a comma for the rest of the current session?
 - R:   export LC_NUMERIC=en_US.UTF-8 or export LC_ALL=en_US.UTF-8.
##### 3. Command iconv will replace all characters outside the target character set with a question mark. If //TRANSLIT is appended to the target encoding, characters not represented in the target character set will be replaced (transliterated) by one or more similar looking characters. How could this method be used to convert a UTF-8 text file named readme.txt to a plain ASCII file named ascii.txt?
- R:   iconv -f UTF-8 -t ASCII//TRANSLIT -o ascii.txt  readme.txt

- - - 
## ***Sources:***