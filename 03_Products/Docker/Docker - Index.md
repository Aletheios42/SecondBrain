**Tags:** #_Todo
#ToTag #ToLink 
- - -
## cosas que añadir
docker por defecto corre en modo no-interactivo , es decir que no lee del stdin
muchas practicas de iximiuz
--help 
##### ¿Qué es Docker?

Docker es una solucion a un problema conocido como "The Matrix from Hell" asegurando compatibilidad de los distintos componente de un proyecto, ademas de facilitiar drasticamente  la replicacoin del enterno.

Su proposito es paquetizar aplicaciones y desplegar aplicaciones en diferentes sistemas

#### ¿Que son las imagenes?(completar)
==Meter una practica con dive==
==Explorar comandos==
explicar es sistema de capas y los caches
explicar que el contenedor es una capa extra desechable sobre la imagen y el esquema read only de la image y read/write del contenedor, como se copiar los archivos que pertenecen a las capas de la imagen para ser modificados por el contenedor
Una imagen es un paquete plantilla,  para instanciar contenedores
practicas sobre dive
- multi arquitectura buildx (utiliza kemu por dentro): https://www.youtube.com/watch?v=hWSHtHasJUI
- mirar buildkit
##### Registros
- es un servidor para almacenar imagenes, el oficial es dockerhub
==meter el nombre real de las imagenes ==
==hacer practica de como pushear a distinto registros, prob deployear un par de registors y usarlos en la practica sea interesante==
==Explicar el nombre real de las imagenes y por ende que es el "Prefix registry"==
==explicar el login tambien, y  como distintos registros utilizan distintas herramientas para la autentificacion(g-cloud)asi como distiiontos OS (MAC)==
#### ¿Que es un contenedor?
==Practica para entender las capas readwrite, instalar algo y volver a correr el contenedor==
==explorar comandos==
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
Si va por aplicaciones de terceros
	 -montar sistema de versiones **Completas**, o versiones de lanzamiento
Si el codigo es propio:
1. Commit del código (git commit)
2. Obtener el hash: git rev-parse --short HEAD
3. Construir la imagen usando ese hash como tag: docker build -t myapp:$(git rev-parse --short HEAD) .
4. Testear esa imagen

se pueden combinar ambas con por ejemplo
registro/ubuntu.22.04.7@elhashcorrespondiente
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
[[Docker - Como Escribir un Buen Dockerfile]]
https://docs.docker.com/reference/dockerfile/
mirar la imagen scratch
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

#### Docker run vs docker compose
imperativo vs declarativo
el ciclo d evida de contenedor es mucho mas sencillo con el compose
https://www.composerize.com/
#### Opciones mas populares
- -d corre en segundo plano
- -entrypoint  modifica el entrypoing
- --interactive -i --tty -t  la combinacion me permite entrar al contenedor con bash
- --mount --volumen -v para aplicar una capa writable persistente
- --init 
- --env -e --envfile
- --name
- --network --net
- --platform
- --publish -p
- --restart
- --rm
#### opciones avanzadas
--cap-add, --cap-drop
--cgroup-parent
--cpu-shares
--cpuset-cpus (pin execution to specific CPU cores)
--device-cgroup-rule,
--device-read-bps, --device-read-iops, --device-write-bps, --device-write-iops
--gpus (NVIDIA Only)
--health-cmd, --health-interval, --health-retries, --health-start-period, --health-timeout
--memory , -m
--pid, --pids-limit
--privileged
--read-only
--security-opt
--userns

### Security
==Interesante: https://www.chainguard.dev/ ==
  ==Snyk o trivy==
Container Security
There are two main considerations when it comes to container security (1) the contents of your container image and (2) the security of the execution configuration and environment.

Image Security
“What vulnerabilities exist in your image that an attacker could exploit?”

Keep attack surface area as small as possible:
Use minimal base images (multi-stage builds are a key enabler)
Don’t install things you don’t need (don’t install dev deps)
Scan images!
Use users with minimal permissions
Keep sensitive info out of images
Sign and verify images
Use fixed image tags, either:
Pin major.minor (allows patch fixes to be integrated)
Pin specific image hash
Runtime Security
If an attacker successfully compromises a container, what can they do? How difficult will it be to move laterally?

Docker daemon (dockerd)
Start with --userns-remap option(https://docs.docker.com/engine/security/userns-remap/)
Individual containers:
Use read only filesystem if writes are not needed
--cap-drop=all, then --cap-add anything you need
Limit cpu and memory --cpus=“0.5” --memory 1024m
Use --security-opt
seccomp profiles (https://docs.docker.com/engine/security/seccomp/)
apparmor profiles (https://docs.docker.com/engine/security/apparmor/)

#### Docker network
https://www.youtube.com/watch?v=bKFMS5C4CG0


#### Desarrollo de software en contenedores
- aprender a debuggear en contenedores
- CD/CI para testeao por pipelines
- https://github.com/BretFisher/docker-ci-automation
#### Entornos efimeros
- shipyard: la idea es que cada desarrollador **en un equipo** pueda tener un entorno en el que validar las PR

#### Deploy Containeres
- cloud providers
		- aws : https://www.lastweekinaws.com/blog/the-17-ways-to-run-containers-on-aws/

Caracteristicas de buen proveedor:
- Seguridad
- Comodidad: ¿Es facil de configurar? ¿Puedo hacer acutializaciones son downtime? ¿Como se ven los logs, observability?
- Escalabilidad: ¿Puedo elegir CPUS- GPUS? ¿Como se comunican con sistemsa distribuidos?
- Como configurar la persistencia 
-  Coste
- - - 
## ***Sources:***
- DevOps Directive TOP
1. [Complete Docker Course - From BEGINNER to PRO! (Learn Containers)](https://www.youtube.com/watch?v=RqTEHSBrYFw&list=WL&index=1&t=1s)
 2. https://courses.devopsdirective.com/docker-beginner-to-pro/lessons/00-introduction/01-main
 3. https://github.com/sidpalas/devops-directive-docker-course

- kodekloud userfriendly
[Curso Docker basico kodekloud](https://learn.kodekloud.com/user/courses/docker-training-course-for-the-absolute-beginner