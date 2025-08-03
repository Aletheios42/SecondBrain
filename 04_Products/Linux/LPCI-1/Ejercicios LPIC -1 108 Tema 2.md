**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson 1
# Guided Exercises
##### 1. What utilities/commands would you use in the following scenarios:

| Purpose                                    | Utility      |
| ------------------------------------------ | ------------ |
| Read /var/log/syslog.7.gz                  | zcat         |
| Read /var/log/syslog                       | tail         |
| Filter for word renewal in /var/log/syslog | grep renewal |
| Read /var/log/faillog                      | faillog -a   |
| Read /var/log/syslog dynamically           | tail -f      |
##### 2. Rearrange the following log entries in such a way that they represent a valid log message with the proper structure:
◦ debian-server
◦ sshd
◦ [515]:
◦ Sep 13 21:47:56
◦ Server listening on 0.0.0.0 port 22
The correct order is:
Sep 13 21:47:56 debian-server sshd[515]: Server listening on 0.0.0.0 port 22
##### 3. What rules would you add to /etc/rsyslog.conf in order to accomplish each of the following:
◦ Send all messages from the mail facility and a priority/severity of crit (and above) to /var/log/mail.crit:
R: mail.crit /var/log/mail.crit
◦ Send all messages from the mail facility with priorities of alert and emergency to /var/log/mail.urgent:
R:  mail.alert /var/log/mail.urgent
◦ Except for those coming from the cron and ntp facilities, send all messages — irrespective of their facility and priority — to /var/log/allmessages:
R:  \*.\*;cron.none;ntp.none /var/log/allmessages
◦ With all required settings properly configured first, send all messages from the mail facility to a remote host whose IP address is 192.168.1.88 using TCP and specifying the default port:
R:   mail.* @@192.168.1.88:514
◦ Irrespective of their facility, send all messages with the warning priority (only with the warning priority) to /var/log/warnings preventing excessive writing to the disk:
R:   \*.=warning -/var/log/warnings
##### 4. Consider following stanza from /etc/logrotate.d/samba and explain the different options:
``` bash
carol@debian:~$ sudo head -n 11 /etc/logrotate.d/samba
/var/log/samba/log.smbd {
weekly
missingok
rotate 7
postrotate
[ ! -f /var/run/samba/smbd.pid ] || /etc/init.d/smbd reload > /dev/null
endscript
compress
delaycompress
notifempty
}
```

| Option        | Meaning                             |
| ------------- | ----------------------------------- |
| weekly        | Log files are rotated weekly        |
| missingok     | No error if log file is missing     |
| rotate 7      | Keep 7 rotated logs before deleting |
| postrotate    | Scripts to execute after rotation   |
| endscript     | Marks end of postrotate script      |
| compress      | Rotated logs should be compressed   |
| delaycompress | Don't compress previous version     |
| notifyempty   | Don't rotate if log is empty        |

# Explorational Exercises
##### 1. In section “Templates and Filter Conditions” we used an expression-based filter as a filter condition. Property-based filters are another type of filter unique to rsyslogd. Translate our expression-based filter into a property-based filter:
Expression-Based Filter: if $FROMHOST-IP\=='192.168.1.4' then ?RemoteLogs
Property-Based Filter:
- R:  :fromhost-ip, isequal, "192.168.1.4" ?RemoteLogs
##### 2. omusrmsg is an rsyslog built-in module which facilitates notifying users (it sends log messages to the user terminal). Write a rule to send all emergency messages of all facilities to both root and the regular user carol.
- R:  \*.emerg :omusrmsg:root,carol

# Lesson 2

# Guided Exercise
##### 1. journalctl commands:

| Purpose                                    | Command                        |
| ------------------------------------------ | ------------------------------ |
| Print kernel entries                       | journalctl -k                  |
| Print messages from second boot from start | journalctl --list-boots -1     |
| Print messages from second boot from end   | journalctl --list-boots -1 -r  |
| Print recent logs and watch for new        | journalctl -f                  |
| Print only new messages since now          | journalctl -n 0 -f             |
| Print previous boot warnings in reverse    | journalctl -b -1 -p warning -r |

##### 2. Storage behavior:

| Behavior                                           | Storage Type       |
| -------------------------------------------------- | ------------------ |
| Log data thrown away but forwarding possible       | Storage=none       |
| Store in /var/log/journal, create if missing       | Storage=persistent |
| Store in /var/log/journal, don't create if missing | Storage=auto       |
| Store in /var/run/journal, temporary               | Storage=volatile   |

##### 3.  As you learned, the journal can be manually vacuumed based on time, size and number of files. Complete the following tasks using journalctl and the appropriate options:

1. Check disk space: 
```bash
journalctl --disk-usage
```

2. Set 200MB limit:
```bash
journalctl --vacuum-size=200M
```

3. Verify space reduction:
```bash
journalctl --disk-usage
```

# Explorational Exercises
##### 1. What options should you modify in /etc/systemd/journald.conf so that messages are forwarded to /dev/tty5? What values should the options have?
- R: ForwardToConsole=yes
TTYPath=/dev/tty5
##### 2. Provide the correct journalctl filter to print the following:
- R:

| Purpose                                      | Filter + Value     |
| -------------------------------------------- | ------------------ |
| Print messages belonging to a specific user  | _ID=\<user-id>     |
| Print messages from host debian              | _HOSTNAME=debian   |
| Print messages belonging to a specific group | _GID=1000          |
| Print messages belonging to root             | _UID=0             |
| Print sudo messages (executable path)        | _EXE=/usr/bin/sudo |
| Print sudo messages (command name)           | COMM=sudo          |
##### 3. When filtering by priority, logs with a higher priority than indicated will also be included in the listing; for instance journalctl -p err will print error, critical, alert and emergency messages. However, you can have journalctl show only a specific range. What command would you use to have journalctl print only messages in the warning, error and critical priority levels?
- R: journalctl -p warning..crit
##### 4. Priority levels can also be specified numerically. Rewrite the command in the previous exercise using the numeric representation of priority levels:
- R: journalctl -p 4..2
- - - 
## ***Sources:***