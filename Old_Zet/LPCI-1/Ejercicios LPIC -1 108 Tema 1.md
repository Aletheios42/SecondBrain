**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson 1
# Guided Exercise
##### 1. Indicate whether the following commands are displaying or modifying system time or hardware time:

| Command                         | System/Hardware/Both |
| ------------------------------- | -------------------- |
| date -u                         | S                    |
| hwclock --set --date "12:00:00" | H                    |
| timedatectl                     | B                    |
| timedatectl \| grep RTC         | H                    |
| hwclock --hctosys               | S                    |
| date +%T -s "08:00:00"          | S                    |
| timedatectl set-time 1980-01-10 | B                    |
##### 2. Observe the following output, and then correct the format of the argument so that the command is successful:
```
$ date --debug --date "20/20/12 0:10 -3"

date: warning: value 20 has less than 4 digits. Assuming MM/DD/YY[YY]
date: parsed date part: (Y-M-D) 0002-20-20
date: parsed time part: 00:10:00 UTC-03
date: input timezone: parsed date/time string (-03)
date: using specified time as starting value: '00:10:00'
date: error: invalid date/time value:
date:
 user provided time: '(Y-M-D) 0002-20-20 00:10:00 TZ=-03'
date:
 normalized time: '(Y-M-D) 0003-08-20 00:10:00 TZ=-03'
date:
 ---- --
date:
 possible reasons:
date:
 numeric values overflow;
date:
 incorrect timezone
date: invalid date ‘20/20/2 0:10 -3’
```
- R: date --debug --set "12/20/20 0:10 -3"
##### 3. Use the date command and sequences so that the system’s month is set to February. Leave the rest of the date and time unchanged.
- R: date +%m -s "2"
##### 4. Assuming that the command above was successful, use hwclock to set the hardware clock from the system clock.
- R:  hwclock -systohc
##### 5. There is a location called eucla. What continent is it part of? Use the grep command to find out.
- R:  timedatectl list-timezones \| grep -i eucla OR grep -ri eucla /usr/share/zoneinfo
##### 6. Set your current timezone to that of eucla.
- R: timedatectl set-timezone 'Australia/Eucla' or ln -s /usr/share/zoneinfo/Australia/Eucla /etc/localtime
# Explorational Exercises
##### 1. Which method of setting time is optimal? In what scenario might the preferred method be impossible?
 - R: NTP 
##### 2. Why do you think there are so many methods to accomplish the same thing, i.e. setting system time?
- R:  Since setting time has been a requirement of all *nix systems for decades, there are many legacy methods for setting time that are still maintained.
##### 3. After January 19, 2038, Linux System Time will require a 64-bit number to store. However, it is possible that we could simply choose to set a “New Epoch”. For example, January 1st, 2038 at midnight could be set to a New Epoch Time of 0. Why do you think this has not become the preferred solution?
- R:  32 bit machines will not exist by 2038

# Lesson 2
# Guided Exercise
##### 1. Enter the appropriate term for each definition:
- R

| Term     | Definition                                                                 |
| -------- | -------------------------------------------------------------------------- |
| Provider | A computer that will share network time with you                           |
| Stratum  | Distance from a reference clock, in hops or steps                          |
| Offset   | Difference between system time and network time                            |
| Jitter   | Difference between system time and network time since the last NTP poll    |
| Pool     | Group of servers that provide network time and share the load between them |

##### 2. Specify which of the commands you would use to output the following values:
- R:

| Value to Check         | chronyc tracking | timedatectl show-timesync --all | ntpq -pn | chrony ntpdata | chronyc sources |
| ---------------------- | ---------------- | ------------------------------- | -------- | -------------- | --------------- |
| Jitter                 |                  | x                               | x        |                |                 |
| Drift                  |                  |                                 |          |                |                 |
| Interval of Poll       | x                | x                               | x        | x              | x               |
| Offset                 | x                |                                 | x        | x              |                 |
| Stratum                | x                | x                               | x        | x              | x               |
| IP Address of Provider |                  | x                               | x        | x              | x               |
| Root Delay             | x                |                                 |          | x              |                 |

##### 3. You are setting up an enterprise network consisting of a Linux server and several Linux desktops. The server has a static IP address of 192.168.0.101. You decide that the server will connect to pool.ntp.org and then provide NTP time to the desktops. Describe the configuration of the server and of the desktops.
- R: Ensure that the server has an ntpd service running, rather than SNTP. Use pool.ntp.org pools in the /etc/ntp.conf or /etc/chrony.conf file. For each client, specify 192.168.0.101 in each /etc/ntp.conf or /etc/chrony.conf file.
##### 4. A Linux machine has the incorrect time. Describe the steps you would take to troubleshoot NTP.
- R: First, ensure that the machine is connected to the Internet. Use ping for this. Check that an ntpd or SNTP service is running using systemctl status ntpd or systemctl status systemd-timesyncd. You may see error messages that provide useful information. Finally, use a command such as ntpq -p or chrony tracking to verify if any requests have been made. If the system time is drastically different from network time, it may be that system time is considered “insane” and will not be changed without manual intervention. In this case, use a command from the previous lesson or a command such as ntpdate pool.ntp.org to perform a one-time ntp synchronisation.

# Explorational Exercise
##### 1. Research the differences between SNTP and NTP.
- R: SNTP
less accurate
requires fewer resources
cannot act as a time provider
steps time only
requests time from a single source
NTP
more accurate
requires more resources
can act as a time provider
steps or slews time
can monitor multiple NTP servers and use the optimal provider
##### 2. Why might a system administrator choose not to use pool.ntp.org?
- R: From ntppool.org: If it is absolutely crucial to have correct time, you should consider an alternative. Similarly, if your Internet provider has a time server, it is recommended to use that instead.
##### 3. How would a system administrator choose to join or otherwise contribute to the pool.ntp.org project?
- R: From www.ntppool.org: Your server must have a static IP address and a permanent internet connection. The static IP address must not change at all or at least less than once a year. Beyond that, the bandwidth requirements are modest: 384 - 512 Kbit bandwidth. Stratum 3 or 4 servers are welcome to join.
- - - 
## ***Sources:***