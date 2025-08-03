**Tags:** #_Todo
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. Divide the following shared library names into their parts: Complete file name linux-vdso.so.1 libprocps.so.6 libdl.so.2 libc.so.6 libsystemd.so.0 ld-linux-x86- 64.so.2 Library name so suffix Version number
- R: 

| Complete file name   | Library name    | SO suffix | Version number |
| -------------------- | --------------- | --------- | -------------- |
| linux-vdso.so.1      | linux-vdso      | .so       | 1              |
| libprocps.so.6       | libprocps       | .so       | 6              |
| libdl.so.2           | libdl           | .so       | 2              |
| libc.so.6            | libc            | .so       | 6              |
| libsystemd.so.0      | libsystemd      | .so       | 0              |
| ld-linux-x86-64.so.2 | ld-linux-x86-64 | .so       | 2              |
##### 2. You have developed a piece of software and want to add a new shared library directory to your system (/opt/lib/mylib). You write its absolute path in a file called mylib.conf. 1) In what directory should you put this file? 2) What command should you run to make the changes fully effective?
- R: 1) /etc/ld.so.conf.d 2) ldconfig
##### 3. What command would you use to list the shared libraries required by kill?
- R:  ldd /bin/kill

# Explorational Exercises
##### 1. objdump is a command line utility that displays information from object files. Check if it is installed in your system with which objdump. If it is not, please, install it. 1) Use objdump with the -p (or --private-headers) option and grep to print the dependencies of glibc: 2)  Use objdump with the -p (or --private-headers) option and grep to print the soname of glibc: 3) Use objdump with the -p (or --private-headers) option and grep to print the dependencies of Bash:
- R: 
1) objdump -p /lib/x86_64-linux-gnu/libc.so.6 | grep NEEDED
2) objdump -p /lib/x86_64-linux-gnu/libc.so.6 | grep SONAME
3) objdump -p /bin/bash | grep NEEDED
- - - 
## ***Sources:***