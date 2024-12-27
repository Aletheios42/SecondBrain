**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises

##### 1. In a preemptive multi-tasking system, what happens when a lower priority process is occupying the processor and a higher priority process is queued to be executed?
- R:  El high priority se ejecuta, el low espera
##### 2. Consider the following `top` screen:

```plaintext
top - 08:43:14 up 23 days, 12:29,  5 users,  load average: 0,13, 0,18, 0,21
Tasks: 240 total,   2 running, 238 sleeping,   0 stopped,   0 zombie
%Cpu(s):  1,4 us,  0,4 sy,  0,0 ni, 98,1 id,  0,0 wa,  0,0 hi,  0,0 si,  0,0 st
MiB Mem :   7726,4 total,    590,9 free,   1600,8 used,   5534,7 buff/cache
MiB Swap:  30517,0 total,  30462,5 free,     54,5 used.   5769,4 avail Mem 

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND     
    1 root      20   0  171420  10668   7612 S   0,0  0,1   9:59.15 systemd     
    2 root      20   0       0      0      0 S   0,0  0,0   0:02.76 kthreadd    
    3 root       0 -20       0      0      0 I   0,0  0,0   0:00.00 rcu_gp      
    4 root       0 -20       0      0      0 I   0,0  0,0   0:00.00 rcu_par_gp  
    8 root       0 -20       0      0      0 I   0,0  0,0   0:00.00 mm_percpu_wq
    9 root      20   0       0      0      0 S   0,0  0,0   0:49.06 ksoftirqd/0 
   10 root      20   0       0      0      0 I   0,0  0,0  18:24.20 rcu_sched   
   11 root      20   0       0      0      0 I   0,0  0,0   0:00.00 rcu_bh      
   12 root      rt   0       0      0      0 S   0,0  0,0   0:08.17 migration/0 
   14 root      20   0       0      0      0 S   0,0  0,0   0:00.00 cpuhp/0     
   15 root      20   0       0      0      0 S   0,0  0,0   0:00.00 cpuhp/1     
   16 root      rt   0       0      0      0 S   0,0  0,0   0:11.79 migration/1 
   17 root      20   0       0      0      0 S   0,0  0,0   0:26.01 ksoftirqd/1 
   ```
   What PIDs have real-time priorities?
   - R: 12 y 16
##### 3. Consider the following ps -el listing:

| F   | S   | UID | PID | PPID | C   | PRI | NI  | ADDR | SZ    | WCHAN | TTY | TIME     | CMD         |
| --- | --- | --- | --- | ---- | --- | --- | --- | ---- | ----- | ----- | --- | -------- | ----------- |
| 4   | S   | 0   | 1   | 0    | 0   | 80  | 0   | -    | 42855 | -     | ?   | 00:09:59 | systemd     |
| 1   | S   | 0   | 2   | 0    | 0   | 80  | 0   | -    | 0     | -     | ?   | 00:00:02 | kthreadd    |
| 1   | I   | 0   | 3   | 2    | 0   | 60  | -20 | -    | 0     | -     | ?   | 00:00:00 | rcu_gp      |
| 1   | S   | 0   | 9   | 2    | 0   | 80  | 0   | -    | 0     | -     | ?   | 00:00:49 | ksoftirqd/0 |
| 1   | I   | 0   | 10  | 2    | 0   | 80  | 0   | -    | 0     | -     | ?   | 00:18:26 | rcu_sched   |
| 1   | I   | 0   | 11  | 2    | 0   | 80  | 0   | -    | 0     | -     | ?   | 00:00:00 | rcu_bh      |
| 1   | S   | 0   | 12  | 2    | 0   | -40 | -   | -    | 0     | -     | ?   | 00:00:08 | migration/0 |
| 1   | S   | 0   | 14  | 2    | 0   | 80  | 0   | -    | 0     | -     | ?   | 00:00:00 | cpuhp/0     |
| 5   | S   | 0   | 15  | 2    | 0   | 800 | -0  | -    | 0     | -     | ?   | 00:00:00 | cpuhp/1     |
Which PID has higher priority? 
- R:  12
##### 4. After trying to renice a process with renice, the following error happens: $ renice -10 21704 renice: failed to set priority for 21704 (process ID): Permission denied What is the probable cause for the error?
 - R: solo el root puede cambiar prioridades por debajo de 0 . 
# Explorational Exercises
##### 1. Changing process priorities is usually required when a process is occupying too much CPU time. Using ps with standard options for printing all system processes in long format, what --sort flag will sort processes by CPU utilization, increasing order?
- R:  ps -el --sort=pcpu
##### 2. Command schedtool can set all CPU scheduling parameters Linux is capable of or display information for given processes. How can it be used to display the scheduling parameters of process 1750? Also, how can schedtool be used to change process 1750 to real-time with priority -90 (as displayed by top)?
- R:  schedtool 1750
 schedtool -R -p 89 1750
- - - 
## ***Sources:***