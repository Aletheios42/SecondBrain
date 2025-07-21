**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson 1
# Guided Exercises
##### 1. In addition to text files, the command cat can also work with binary data, like sending the contents of a block device to a file. Using redirection, how can cat send the contents of device /dev/sdc to the file sdc.img in the current directory?
- R: </dev/sdc cat >sdc.img
##### 2. What’s the name of the standard channel redirected by the command date 1> now.txt?
- R: stdout
##### 3. After trying to overwrite a file using redirection, a user gets an error informing that option noclobber is enabled. How can the option noclobber be deactivated for the current session?
- R: set +C or set +o noclobber
##### 4. What will be the result of command cat <<.>/dev/stdout?
- R: un here_doc a la consola estandar con . como delimitador
# Explorational Exercises
##### 1. The command cat /proc/cpu_info displays an error message because /proc/cpu_info is nonexistent. The command cat /proc/cpu_info 2>1 redirects the error message to where?
 - R: a un archivo llamado 1 en el directorio actual
##### 2. Will it still be possible to discard content sent to /dev/null if the noclobber option is enabled for the current shell session?
- R: yes
##### 3. Without using echo, how could the contents of the variable $USER be redirected to the stdin of command sha1sum?
- R: sha1sum <<<$USER
##### 4. The Linux kernel keeps symbolic links in /proc/PID/fd/ to every file opened by a process, where PID is the identification number of the corresponding process. How could the system administrator use that directory to verify the location of log files opened by nginx, supposing its PID is 1234?
- R: ls -l /proc/1234/fd
##### 5. It’s possible to do arithmetic calculations using only shell builtin commands, but floating point calculations require specific programs, like bc (basic calculator). With bc it’s even possible to specify the number of decimal places, with parameter scale. However, bc accepts operations only through its standard input, usually entered in interactive mode. Using a Here string, how can the floating point operation scale=6; 1/3 be sent to the standard input of bc?
- R:  bc <<<"scale=6; 1/3"

# Lesson 2
# Guided Exercises
##### 1. It’s convenient to save the execution date of actions performed by automated scripts. Command date +%Y-%m-%d shows the current date in year-month-day format. How can the output of such a command be stored in a shell variable called TODAY using command substitution?
- R: today='date +%Y-%m-%d'
##### 2. Using command echo, how can the contents of variable TODAY be sent to the standard input of command sed s/-/./g?
- R: echo $TODAY | sed s/-/./g
##### 3. How could the output of command date +%Y-%m-%d be used as a Here string to command sed s/-/./g?
- R: sed s/-/./g <<<$(date +%Y-%m-%d)
##### 4. Command convert image.jpeg -resize 25% small/image.jpeg creates a smaller version of image.jpeg and places the resulting image in a likewise named file inside subdirectory small. Using xargs, how is it possible to perform the same command for every image listed in file filelist.txt?
- R:   xargs -I IMG convert IMG -resize 25% small/IMG < filelist.txt
# Explorational Exercises
##### 1. A simple backup routine periodically creates an image of partition /dev/sda1 with dd < /dev/sda1 > sda1.img. To perform future data integrity checks, the routine also generates a SHA1 hash of the file with sha1sum < sda1.img > sda1.sha1. By adding pipes and command tee, how would these two commands be combined into one?
- R:  dd < /dev/sda1 | tee sda1.img | sha1sum > sda1.sha1
##### 2. Command tar is used to archive many files into a single file, preserving directory structure.Option -T allows to specify a file containing the paths to be archived. For example, find /etc -type f | tar -cJ -f /srv/backup/etc.tar.xz -T - creates a compressed tar fileetc.tar.xz from the list provided by command find (option -T - indicates the standard input as the path list). In order to avoid possible parsing errors due to paths containing spaces, what command options should be present for find and tar?
- R:  find /etc -type f -print0 | tar -cJ -f /srv/backup/etc.tar.xz --null -T -
##### 3. Instead of opening a new remote shell session, command ssh can just execute a command indicated as its argument: ssh user@storage "remote command". Given that ssh also allows to redirect the standard output of a local program to the standard input of the remote program, how would the cat command pipe a local file named etc.tar.gz to /srv/backup/etc.tar.gz at user@storage through ssh?
- R:  cat etc.tar.gz | ssh user@storage "cat > /srv/backup/etc.tar.gz"

- - - 
## ***Sources:***