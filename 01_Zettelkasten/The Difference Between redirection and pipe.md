**Tags:** #_Todo
#ToTag #ToLink 
- - -
At first glance, it may be hard to understand the redirection performed by the
pipeline operator | versus the redirection operator >. Simply put, the redirection
operator connects a command with a file, while the pipeline operator connects the
output of one command with the input of a second command.
command1 > file1
command1 | command2
A lot of people will try the following when they are learning about pipelines, “just
to see what happens”:
command1 > command2
Answer: sometimes something really bad.
Here is an actual example submitted by a reader who was administering a Linux-
based server appliance. As the superuser, he did this:
```bash
# No ejecutar como administrador
cd /usr/bin
ls > less
```

The first command put him in the directory where most programs are stored and
the second command told the shell to overwrite the file less with the output of
the ls command. Since the /usr/bin directory already contained a file named
less (the less program), the second command overwrote the less program
file with the text from ls, thus destroying the less program on his system.
The lesson here is that the redirection operator silently creates or overwrites files,
so you need to treat it with a lot of respect.
- - - 
## ***Sources:***