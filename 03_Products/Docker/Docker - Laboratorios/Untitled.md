**MetaTags:** #_Todo
**Tags:** #ToTag #ToLink 
- - -

Limitate a ejecutar estos comandos y entender la salida

``` bash
docker run ubuntu sleep -10
```

Inmediatamente despues del sleep
``` bash
docker ps
```

``` bash
docker run -d ubuntu sleep -10
```

Inmediatamente despues del sleep(tarda menos de 10 segundos)
``` bash
docker ps
```

crear este dockerfile
``` Dockerfile
FROM alpine
CMD while true; do date; sleep 1; done
```

Y construye el contendor con 
```bash
docker build -t timer .
```

``` bash
docker run timer
```
y cancela con control -C
``` bash
docker run -d timer
```

fijate en el identificador
``` bash
docker ps
```

```docker
docker attach -d \<identificador>
```
control -C

y borra el contenedor y la imagen
- - - 
#### ***Sources:***