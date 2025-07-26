**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson 1
# Guided Exercises
##### 1. For each of the following crontab shortcuts, indicate the corresponding time specification (i.e. the first five columns in a user crontab file):

- R:

| Shortcut  | Time Specification |
| --------- | ------------------ |
| @hourly   | 0 * * * *          |
| @daily    | 0 0 * * *          |
| @weekly   | 0 0 * * 0          |
| @monthly  | 0 0 1 * *          |
| @annually | 0 0 1 1 *          |
##### 2. For each of the following OnCalendar shortcuts, indicate the corresponding time specification (the longer normalized form):
- R:

| Shortcut | Normalized Form    |
| -------- | ------------------ |
| hourly   | *-*-* *:00:00      |
| daily    | *-*-* 00:00:00     |
| weekly   | Mon *-*-* 00:00:00 |
| monthly  | *-*-01 00:00:00    |
| yearly   | *-01-01 00:00:00   |
##### 3. Explain the meaning of the following time specifications found in a crontab file:
- R:

| Specification      | Meaning                                |
| ------------------ | -------------------------------------- |
| 30 13 * * 1-5      | At 13:30 on weekdays                   |
| 00 09-18 * * *     | Every hour from 9 AM to 6 PM           |
| 30 08 1 1 *        | At 8:30 on January 1st                 |
| 0,20,40 11 * * Sun | At minutes 0,20,40 of 11 AM on Sundays |
| 00 09 10-20 1-3 *  | At 9 AM, days 10-20 in Jan-Mar         |
| */20 * * * *       | Every 20 minutes                       |
##### 4. Explain the meaning of the following time specifications used in the OnCalendar option of a timer file:
- R:

| Specification             | Meaning                          |
| ------------------------- | -------------------------------- |
| *-*-* 08:30:00            | Every day at 8:30                |
| Sat,Sun *-*-* 05:00:00    | Every Sat and Sun at 5:00        |
| *-*-01 13:15,30,45:00     | 1st of each month at 13:15,30,45 |
| Fri *-09..12-* 16:20:00   | Fridays at 16:20 in Sep-Dec      |
| Mon,Tue *-*-1,15 08:30:00 | Mon,Tue on 1st & 15th at 8:30    |
| *-*-* *:00/05:00          | Every 5 minutes                  |

# Explorational Exercises
##### 1. Assuming that you are authorized to schedule jobs with cron as an ordinary user, what command would you use to to create your own crontab file?
- R:  crontab -e
##### 2. Create a simple scheduled job that executes the date command every Friday at 01:00 pm. Where can you see the output of this job?
- R: 00 13 * * 5 date
##### 3. Create another scheduled job that executes the foobar.sh script every minute, redirecting the output to the output.log file in your home directory so that only standard error is sent to you by e-mail.
 - R: */1 * * * * ./foobar.sh >> output.log
##### 4. Look at the crontab entry of the newly created scheduled job. Why is it not necessary to specify the absolute path of the file in which the standard output is saved? And why can you use the ./foobar.sh command to execute the script?
- R: cron invokes the commands from the user’s home directory.
##### 5. Edit the previous crontab entry by removing the output redirection and disable the first cron job you have created.
- R: */1 * * * * ./foobar.sh
##### 6. How can you send the output and errors of your scheduled job to the emma user account via e- mail? And how can you avoid sending the standard output and error via e-mail?
- R: MAILTO="emma"
##### 7. Execute the command ls -l /usr/bin/crontab. Which special bit is set and what is its meaning?
- R:   the SGID bit set (the s character instead of the executable flag for
the group), which means that it is executed with the privileges of the group 

# Lesson 2
# Guided Exercises
##### 1. For each of the following time specifications, indicate which is valid and which is invalid for
- R:

| Time Specification     | Validity | Reason/Note                        |
| ---------------------- | -------- | ---------------------------------- |
| at 08:30 AM next week  | Valid    | Time + relative date format        |
| at midday              | Invalid  | Should be 'noon' or '12:00'        |
| at 01-01-2020 07:30 PM | Invalid  | Incorrect date format              |
| at 21:50 01.01.20      | Valid    | 24h time + date format             |
| at now +4 days         | Valid    | Relative time format               |
| at 10:15 PM 31/03/2021 | Invalid  | Wrong date separator (should be .) |
| at tomorrow 08:30 AM   | Valid    | Time + relative date format        |
##### 2. Once you have scheduled a job with at, how can you review its commands?
 - R: at -c "job ID"
##### 3. Which commands can you use to review your pending at jobs? Which commands would you use to delete them?
 - R: at -l
##### 4. With systemd, which command is used as an alternative to at?
- R: system-run
# Explorational Exercises
##### 1. Create an at job that runs the foo.sh script, located in your home directory, at 10:30 am on coming October 31st. Assume you are acting as an ordinary user.
- R:  $ at 10:30 AM October 31
warning: commands will be executed using /bin/sh
at> ./foo.sh
at> Ctrl+D
job 50 at Thu Oct 31 10:30:00 2019
##### 2. Login to the system as another ordinary user and create another at job that runs the bar.sh script tomorrow at 10:00 am. Assume the script is located in the user’s home directory.
 - R:   at 10:00 AM tomorrow
warning: commands will be executed using /bin/sh
at> ./bar.sh
at> Ctrl+D
job 51 at Sun Oct 6 10:00:00 2019
##### 3. Login to the system as another ordinary user and create another at job that runs the foobar.sh script just after 30 minutes. Assume the script is located in the user’s home directory.
- R: at now +30 minutes
warning: commands will be executed using /bin/sh
at> ./foobar.sh
at> Ctrl+D
job 52 at Sat Oct 5 10:19:00 2019
##### 4. Now as root, run the atq command to review the scheduled at jobs of all users. What happens if an ordinary user executes this command?
- R:  atq
52  Sat Oct 5 10:19:00 2019 a dave
50  Thu Oct 31 10:30:00 2019 a frank
51  Sun Oct 6 10:00:00 2019 a emma
##### 5. As root, delete all these pending at jobs using a single command.
- R:   atrm 50 51 52
##### 6. Run the ls -l /usr/bin/at command and examine its permissions.
- R:   at command has both the SUID (the s character instead of the
executable flag for the owner) and SGID (the s character instead of the executable flag for the
group) bits set, which means that it is executed with the privileges of the owner and group of
the file (daemon for both). This is why ordinary users are able to schedule jobs with at.
- - - 
## ***Sources:***