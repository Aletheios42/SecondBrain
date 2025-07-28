**MetaTags:** #_Completar
**Tags:** #Docker #Devops 
- - -
==Añadir labs de iximiuz==
Aunque puede varias dependiendo de las flags 
Docker run es un comando compuesto que hace:
1) Image pull
2) container create
3) container attach
4) network-connect
5) container start

la terminal redirecciona stdin y señales a docker cli, el cual le remite a dockerd atraves de sockets;
dockerd atraves de http-restapi, este le remite el input a containerd;
containerd, atraves de grpc-api, se lo remite a runc,
runc se lo remite por FIFO contenedor, es decir a su proceso hijo;
el contendor le remite la salida por FIFO a runc de vuelta, y se vuelve a los otros seeervicios mencionados arriba hsata la terminal

- - - 
#### ***Sources:***
