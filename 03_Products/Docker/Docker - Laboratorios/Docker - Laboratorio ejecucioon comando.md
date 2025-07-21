**MetaTags:** #_Todo
**Tags:** #ToTag #ToLink 
- - -
Limitate a ejecutar estos comandos y entender la salida

``` bash
echo $\$
```

``` bash
docker run ubuntu sleep -5
```
``` bash
docker inspect --format '{{.Path}} {{.Args}}' $(docker ps -alq)
```
``` bash
docker run ubuntu echo $\$
```
`` bash
docker inspect --format '{{.Path}} {{.Args}}' $(docker ps -alq)
``

`` bash
docker run ubuntu sh -c "echo $\$"
``
`` bash
docker inspect --format '{{.Path}} {{.Args}}' $(docker ps -alq)
``

`` bash
docker run ubuntu sh -c 'echo $\$'
``
`` bash
docker inspect --format '{{.Path}} {{.Args}}' $(docker ps -alq)
``
`` bash
docker ps
``

`` bash
docker ps -a
``
extrae el identificador

`` bash
docker rm \<identificador\>
``

`` bash
docker rmi ubuntu
``
- - - 
#### ***Sources:***