**Tags:** #_Todo 
#Linux 
- - -
Un proceso es una instancia en ejecución de un programa que consiste en:

Un espacio de direcciones virtual privado y protegido
Un conjunto de segmentos de memoria que incluyen:

Texto (código ejecutable)
Datos (variables globales/estáticas)
Heap (memoria dinámica)
Stack (variables locales/información de llamadas)

The fact that a program can launch other programs is expressed in the process scheme as
a parent process producing a child process.(zombie)
//Daemon

Un Process Control Block (PCB) que contiene:

Process ID único
Program Counter
Registros de CPU
Estado del proceso
Información de scheduling -> "renice -n PID" cambia la prioridad

- - - 
## ***Sources:***
https://www.youtube.com/watch?v=7ge7u5VUSbE