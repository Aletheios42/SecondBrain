**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson1 
# Guided Exercises
##### 1. oneko is a nice funny program that displays a cat chasing your mouse cursor. If not already installed in your desktop system, install it using your distribution’s package manager. We will use it to study job control.
◦ Start the program. How do you do that?
R: oneko 
◦ Move the mouse cursor to see how the cat chases it. Now suspend the process. How do you do that? What is the output?
R: `control + z`    [1]+  Stopped                 oneko
◦ Check how many jobs you currently have. What do you type? What is the output?
R: `jobs`  [1]+  Stopped                 oneko
◦ Now send it to the background specifying its job ID. What is the output? How can you tell the job is running in the background?
R: $ bg %1
[1]+ oneko &
◦ Finally, terminate the job specifying its job ID. What do you type?
R: kill %1
##### 2. Discover the PIDs of all the processes spawned by the Apache HTTPD web server (apache2) with two different commands:
- R: pgreg/pidof apache2
##### 3. Terminate all apache2 processes without using their PIDs and with two different commands:
- R: pkill/killall apache2
##### 4. Suppose you have to terminate all instances of apache2 and you do not have time to find out what their PIDs are. How would you accomplish that using kill with the default SIGTERM signal in a one-liner:
- R: kill $(pgrep apache2)
##### 5. Start top and interact with it by performing the following:
◦ Show a forest view of processes:
R: V
◦ Show full paths of processes differentiating between userspace and kernelspace:
R: c
##### 6. Type the ps command to display all processes started by the Apache HTTPD web server user (www-data):
◦ Using BSD syntax:
R:  ps U www-data
◦ Using UNIX syntax:
R: ps -U www-data
◦ Using GNU syntax:
R: ps --user www-data
# Explorational Exercises
##### 1. The SIGHUP signal can be used as a way to restart certain daemons. With the Apache HTTPD web server — for example — sending SIGHUP to the parent process (the one started by init) kills off its children. The parent, however, re-reads its configuration files, re-opens log files and spawns a new set of children. Do the following tasks:
◦ Start the web server:
R:  sudo systemctl start apache2
◦ Make sure you know the PID of the parent process:
R:  ps aux | grep apache2
◦ Make the Apache HTTPD web server restart by sending it the SIGHUP signal to the parent process:
R: kill -SIGHUP 1653
◦ Check that the parent was not killed and that new children have been spawned:
R: ps aux | grep apache2
##### 2. Although initially static, the output of ps can be turned dynamic by combining ps and watch. We will monitor the Apache HTTPD web server for new connections. Before doing the tasks described below it is recommended that you read the description of the MaxConnectionsPerChild directive in Apache MPM Common Directives.
◦ Add the MaxConnectionsPerChild directive with a value of 1 in the configuration file of apache2 — in Debian and derivatives that is found in /etc/apache2/apache2.conf; in the CentOS family, in /etc/httpd/conf/httpd.conf. Do not forget to restart apache2 for the changes to take effect.
R:  The line to include in the config file is MaxConnectionsPerChild 1. One way to restart the
web server is through sudo systemctl restart apache2.
◦ Type in a command that uses watch, ps and grep for apache2 connections.
R:   watch 'ps aux | grep apache2'
◦ Now open a web browser or use a command line browser such as lynx to establish a connection to the web server through its IP address. What do you observe in the output of watch?
R:  top -o %MEM
##### 3. As you have learned, by default top sorts the tasks by percentage of CPU usage in descending order (the higher values on top). This behaviour can be modified with the interactive keys M (memory usage), N (process unique identifier), T (running time) and P (percentage of CPU time). However, you can also sort the task list to your liking by launching top with the -o switch (for more information, check top’s man page). Now, perform the following tasks:
◦ Launch top so that the tasks are sorted by memory usage:
R:   top -o %MEM
◦ Verify that you typed the right command by highlighting the memory column:
R:  press x
##### 4. ps also has an o switch to specify the columns you want shown. Investigate this option and do the following tasks:
◦ Launch ps so that only information about user, percentage of memory used, percentage of CPU time used and full command is shown:
R:   ps o user,%mem,%cpu,cmd
◦ Now, launch ps so that the only information displayed is that of the user and the name of the programs they are using:
R:  ps o user,comm

# Lesson2
# Guided Exercises
##### 1. Indicate if the following statements/features correspond to GNU Screen, tmux or both: Feature/Statement Default command prefix is Ctrl + a Client-Server Model Panes are pseudo-terminals Killing a region does not kill its associated window(s)Sessions include windows Sessions can be detached GNU Screen tmux
- R:  

| Feature/Statement                                       | GNU Screen | tmux     |
| ------------------------------------------------------- | ---------- | -------- |
| Default command prefix is                               | Ctrl + a   | Ctrl + b |
| Client-Server Model                                     | No         | Yes      |
| Panes are pseudo-terminals                              | Yes        | Yes      |
| Killing a region does not kill its associated window(s) | No         | Yes      |
| Sessions include windows                                | Yes        | Yes      |
| Sessions can be detached                                | Yes        | Yes      |

##### 2. Install GNU Screen on your computer (package name: screen) and complete the following tasks:
◦ Start the program. What command do you use?
R: screen
◦ Start top:
R: top
◦ Using screen’s key prefix, open a new window; then, open /etc/screenrc using vi:
R: Ctrl + a - c
sudo vi /etc/screenrc
◦ List the windows at the bottom of the screen:
R: Ctrl + a - w
◦ Change the name of the current window to vi:
R: Ctrl + a - A . Then we have to type vi and press enter .
◦ Change the name of the remaining window to top. To do that, first display a list of all windows so that you can move up and down and select the right one:
R:  First we type Ctrl + a - " . Then we use the arrow keys to mark the one that says 0 bash and
press enter . Finally, we type Ctrl + a - A , type in top and press enter .
◦ Check that the names have changed by having the window names displayed at the bottom of the screen again:
R: Ctrl + a - w
◦ Now, detach the session and have screen create a new one named ssh:
R:  Ctrl + a - d screen -S "ssh" and press enter .
◦ Detach also from ssh and have screen display the list of sessions:
R:  Ctrl + a - d screen -list or screen -ls.
◦ Now, attach to the first session using its PID:
R:  screen -r PID-OF-SESSION
◦ You should be back at the window displaying top. Split the window horizontally and move to the new empty region:
R:  Ctrl + a - S
Ctrl + a - Tab
◦ Have screen list all windows and select vi to be displayed in the new empty region:
R:  We use Ctrl + a - " to have all windows displayed for selection, mark vi and press enter .
◦ Now, split the current region vertically, move into the newly created empty region and associate it with a brand new window:
R:  Ctrl + a - |
Ctrl + a - Tab
Ctrl + a - c
◦ Terminate all regions except the current one (remember, although you kill the regions, the windows are still alive). Then, quit out of all the windows of the current session until the session itself is terminated:
R:  Ctrl + a - Q . exit (to exit Bash). Shift + : , then we type quit and press enter (to exit vi). After that, we type exit (to exit the underlying Bash shell) q (to terminate top); then we type exit (to exit the underlying Bash shell).
◦ Finally, have screen list its sessions one more time, kill the remaining ssh session by PID and check that there are actually no sessions left:
R: screen -list or screen -ls
screen -S PID-OF-SESSION -X quit
screen -list or screen -ls
##### 3. Install tmux on your computer (package name: tmux) and complete the following tasks:
◦ Start the program. What command do you use? Start top (note how — in a couple of seconds — the name of the window changes to top in the status bar):
R: tmux
top
◦ Using tmux’s key prefix, open a new window; then, create ~/.tmux.conf using nano:
R: Ctrl + b - c nano
 ~/.tmux.conf
◦ Split the window vertically and reduce the size of the newly created pane a few times:
R:  Ctrl + b - "
Ctrl + b - Ctrl + ↓
◦ Now change the name of the current window to text editing; then, have tmux display a list with all its sessions:
R: Ctrl + b - , . Then we supply the new name and press enter . Ctrl + b - s or tmux ls.
◦ Move to the window running top and back to the current one using the same key combination:
R:  Ctrl + b - n or Ctrl + b - p
◦ Detach from the current session and create a new one whose name is ssh and its window name is ssh window:
R: Ctrl + b - d tmux new -s "ssh" -n "ssh window"
◦ Detach also from the ssh session and have tmux display the list of sessions again: NOTE From this point on the exercise requires that you use a remote machine for ssh connections to your local host (a virtual machine is perfectly valid and can prove really practical). Make sure you have openssh-server installed and running on your local machine and that at least openssh-client is installed on the remote machine.
R: Ctrl + b - d tmux ls
◦ Now, start a remote machine and connect via ssh with your local host. Once the connection has been established, check for tmux sessions:
R:  On remote host: ssh local-username@local-ipaddress. Once connected to the local
machine: tmux ls.
◦ On the remote host, attach to the ssh session by name: 
R:  tmux a -t ssh (a can be replaced by at or attach).
◦ Back at your local machine, attach to the ssh session by name making sure the connection to the remote host is terminated first:
R: tmux a -d -t ssh (a can be replaced by at or attach).
◦ Have all sessions displayed for selection and go to your first session ([0]). Once there, kill session ssh by name:
R:  We type Ctrl + b - s , use the arrow keys to mark session 0 and press enter tmux kill-session -t ssh.
◦ Finally, detach from the current session and kill it by name:
R:  Ctrl + b - d tmux kill-session -t 0.
# Explorational Exercises
##### 1. Both screen and tmux can enter command line mode through command prefix + : (we already saw a brief example with tmux). Do some research and the following tasks in command line mode:
◦ Make screen enter copy mode:
R: Ctrl + a - : — then, we type copy.
◦ Make tmux rename the current window:
R:  Ctrl + b - : — then, we type rename-window.
◦ Make screen close all windows and terminate session:
R:  Ctrl + a - : — then, we type quit.
◦ Make tmux split a pane into two:
R:  Ctrl + b - : — then, we type split-window.
◦ Make tmux kill the current window:
R:  Ctrl + b - : — then, we type kill-window.
##### 2. When you enter copy mode in screen not only can you use the arrow keys and PgUP or PgDown to navigate the current window and the scrollback buffer. There is also the possibility of using a vi-like full screen editor. Using this editor, perform the following tasks:
◦ Echo supercalifragilisticexpialidocious in your screen terminal:
R: echo supercalifragilisticexpialidocious
◦ Now, copy the five consecutive characters (left-to-right) in the line right above your cursor:
R: We enter copy mode: Ctrl + a - [ or Ctrl + a - : and then type copy. Then, we move to the line
above using k and press space to mark beginning of selection. Finally, we move forward four
characters using l and press space again to mark the end of the selection.
◦ Finally, paste the selection (stice) back at your command prompt:
R:  Ctrl + a - ]
##### 3. Suppose you want to share a tmux session (our_session) with another user. You have created the socket (/tmp/our_socket) with the right permissions so that both you and the other user can read and write. What other two conditions should be met in order for the second user to be able to successfully attach the session through tmux -S /tmp/our_socket a -t our_session?
- R:  the socket (/tmp/our_socket) with the right permissions so that both you and the other user can read and write. What other two conditions should be met in order for the second user to be able to successfully attach the session through tmux -S /tmp/our_socket a -t our_session? Both users must have a group in common, e.g. multiplexer. Then, we must have the socket changed into that group as well: chgrp multiplexer /tmp/our_socket.
- - - 
## ***Sources:***