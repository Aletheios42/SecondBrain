**Tags:** #_Todo
#ToTag #ToLink 
- - -
[DOcker Course](https://learn.kodekloud.com/user/courses/docker-training-course-for-the-absolute-beginner)
## cosas que añadir
docker por defecto corre en modo no-interactivo , es decir que no lee del stdin

--help 
##### ¿Qué es Docker?

Docker es una solucion a un problema conocido como "The Matrix from Hell" asegurando compatibilidad de los distintos componente de un proyecto, ademas de facilitiar drasticamente  la replicacoin del enterno.

Su proposito es paquetizar aplicaciones y desplegar aplicaciones en diferentes sistemas

#### ¿Que son las imagenes?(completar)
==Meter una practica con dive==
explicar es sistema de capas y los caches
explicar que el contenedor es una capa extra desechable sobre la imagen y el esquema read only de la image y read/write del contenedor, como se copiar los archivos que pertenecen a las capas de la imagen para ser modificados por el contenedor
Una imagen es un paquete plantilla,  para instanciar contenedores
practicas sobre dive

#### ¿Que es un contenedor?
==Practica para entender las capas readwrite, instalar algo y volver a correr el contenedor==
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

#### Volumenes y storage
- el volumen es una capa writable desacoplada del contenedor, por lo que puede ser importada por diferentes conteneddores
volumen mounting (desde el directorio de los volumenes) vs binding mounting( desde donde sea) 
- v 
- --mount=
storage drivers:
	- AUFS
	- ZFS
	- BTRFS
	- DEVICE MAPPER
	- OVERLAY
	- OVERLAY2
#### Practica super interesante:
https://github.com/dockersamples/example-voting-app
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
==mirar documentacion==
https://docs.docker.com/reference/dockerfile/
instrucciones
- FROM
- COPY
- RUN
- ENTRYPOINT
- CMD
dockerfile como heredoc
dockerignore
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
### arquitectura de docker engine
- docker-cli: el cli puede correr en otro host, gracias a la flag -H
- docker rest-api
- docker daemon
#### Nameespaces y cgroups , relacionar con docker engine
==Hacer practicas con esto==
--cpu modifica las propiesdades del cgroup
- unix timesharing
- mount
- proccess ID
- Network
- Interprocces comunicatioon
#### Network
- none
- bridge(por defecto)
- host
DNS embeded que resuelve las conexiones por nombre de contendor
#### registro
==Practica deployear ty registro pushear y pullear alguna imagnes copiar de aqui:==
https://github.com/sidpalas/devops-directive-docker-course/tree/main/04-using-3rd-party-containers
imagen registro para registro privado

#### orquestacion
--replica
loadbalancer, 
networing entre host dinamicos
docker swam vs kubernettes vs mesos

###### aprender yml
- key pair , 2 puntos espacio
- array con guines
- diccionarios con tabs
diccionario unordered, lista oredered
#### Desarrollo de software en contenedores
####

- - - 
## ***Sources:***
- [Complete Docker Course - From BEGINNER to PRO! (Learn Containers)](https://www.youtube.com/watch?v=RqTEHSBrYFw&list=WL&index=1&t=1s)
- [Curso Docker basico kodekloud](https://learn.kodekloud.com/user/courses/docker-training-course-for-the-absolute-beginner
- https://courses.devopsdirective.com/docker-beginner-to-pro/lessons/00-introduction/01-main
- https://github.com/sidpalas/devops-directive-docker-course