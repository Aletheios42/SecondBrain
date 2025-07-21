**Tags:** #_Todo
#ToTag #ToLink 
- - -
[DOcker Course](https://learn.kodekloud.com/user/courses/docker-training-course-for-the-absolute-beginner)
## cosas que añadir
docker por defecto corre en modo no-interactivo , es decir que no lee del stdin
##### ¿Qué es Docker?

Docker es una solucion a un problema conocido como "The Matrix from Hell" asegurando compatibilidad de los distintos componente de un proyecto, ademas de facilitiar drasticamente  la replicacoin del enterno.

Su proposito es paquetizar aplicaciones y desplegar aplicaciones en diferentes sistemas

#### ¿Que es un contenedor?
Un contenedor es un entorno aislado y limitado en recursos (Cambiar esto ultimo, porque parece que tiene mala performance en vez de que simplemente el kernel pone limites de consmo de recusos), provisto por el kernel gracias a nameespaces y cgruops.
tipos:
-  LXC
- LXD
- LXCFS
Estados
- ejecutando
- salido
Disponibilidad.
- attacht
- deattched

Un contenedor solo se mantiene en ejecucaion si los procesos que corren dentro estan en ejecucion

#### ¿Que son las imagenes?(completar)
Una imagen es un paquete plantilla,  para instanciar contenedores


#### TAGS

### Comandos
- search:
- run: start a container, permite apendizar un comando como "entrypoint" (revisar esto)
- ps: muestra los procesos
- stop: para un container
- rm: Borrars un contenedor
- image: maneja imagenes, como borrar pushear pullear ...
- rmi: borra imagenes
- exec, ejecuta un comando en un contenedor en ejecucion
- attach, para traer al primer plano un contenedeor en ejecucoin de segundo plano


##### Dockerfile
instrucciones
- FROM
- COPY
- RUN
- ENTRYPOINT
- CMD
### en win en linux y en mac
### que es compartir un kernel y compartimentacion
##### vm vs container. (la union es lo mejor)
###### Arquitectura de vm
hyper visor contiene maquinas virtuales que contienen OS que compartimenta(sandbox) librerias y dependencias sobre los que se corren las aplicaciones.

###### Arquitectura de vm
en cambio en docker la arquitectura es
kernel -> sistema operativo corre docker que compartimenta librerias y dependencias sobre las que se corre la applicacion

##### Meter la arquitectura de vm && containeer del curso de kodecloud al principio
- clave, provisionar algunas maquinas virtuales que provisiones muchos contenedores corriendo aplicaciones
#### enlazar con el final del curso de linux para saber lo que es un cgroup y un hipervisor


### port mapping
###
####
####
####
####
####
####
####

- - - 
## ***Sources:***