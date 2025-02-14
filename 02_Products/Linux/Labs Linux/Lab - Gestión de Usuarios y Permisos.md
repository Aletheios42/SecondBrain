**Tags:** #_Todo
#ToTag #ToLink 
- - -
#### Ejercicio 0 Poner password al root
1. Enunciado: cambia la contraseña de tu root
2. Solucion
``` bash
hacer sudo 
su; passwd
```

#### **Ejercicio 1: Crear Usuarios y Asignar Permisos a Archivos**
3. **Setup:**
    - Crear dos usuarios: `usuario1` y `usuario2`.
    - Crear un archivo accesible solo para `usuario1`.
    - Verificar que `usuario2` no pueda acceder al archivo.
4. **Solucion 1**
    a. **Crear los usuarios: usuario1,usuario2, usuario3 **
	``` bash
sudo useradd usuario1
sudo useradd usuario2 
sudo useradd usuario3
sudo passwd usuario1 
sudo passwd usuario2
sudo passwd usuario3
	```
    b. **Iniciar sesión como `usuario1` y crear un archivo:**
	``` bash
# Permisos: solo el propietario puede leer y escribir. 
    su - usuario1 
	touch archivo_usuario1.txt 
	echo "Este archivo pertenece a usuario1" > archivo_usuario1.txt 
	chmod 600 archivo_usuario1.txt
	```
    c. **Iniciar sesión como `usuario2` y comprobar acceso:**
	``` bash
	# Debería dar un error de permisos.
    su - usuario2 
	cat /home/usuario1/archivo_usuario1.txt    
```
	 
    d. **Modificar los permisos para que ambos puedan leerlo:**
	``` bash
	# Ahora debería ser legible
	sudo chmod 640 /home/usuario1/archivo_usuario1.txt 
	sudo chgrp $(id -gn usuario2) /home/usuario1/archivo_usuario1.txt 
	su - usuario2 
	cat /home/usuario1/archivo_usuario1.txt
    
```

---

#### **Ejercicio 2: Cambiar Propietario y Permisos de Archivos**
1. **Enunciado**
    - Crear un archivo como `root`.
    - Cambiar el propietario a `usuario1`.
    - Modificar permisos para que todos los usuarios puedan leerlo pero solo `usuario1` pueda escribir.
2. **Solucion:**
    a. **Crear el archivo como `root`:**
    ```bash
    sudo touch /tmp/archivo_root.txt 
	sudo echo "Creado por root" > /tmp/archivo_root.txt
   ``` 
    b. **Cambiar el propietario y el grupo del archivo a `usuario1`:**
   ``` bash 
    sudo chown usuario1:usuario1 /tmp/archivo_root.txt
	```
    c. **Modificar los permisos:**
    ``` bash 
	# Todos pueden leer, solo usuario1 puede escribir.`
	sudo chmod 644 /tmp/archivo_root.txt  
```    
    d. **Comprobar los permisos:**
    - Inicia sesión como `usuario1` y escribe en el archivo:
		``` bash
        su - usuario1 echo "Modificado por usuario1" >> /tmp/archivo_root.txt
		```
        
    - Inicia sesión como `usuario2` e intenta escribir:
	``` bash
	# Debería fallar.
       su - usuario2 echo "Intento modificar" >> /tmp/archivo_root.txt  
	```
---
#### **Ejercicio 3: Permisos Avanzados con Directorios**
1. **Enunciado:**
    - Crear un directorio con permisos de escritura para un grupo compartido.
    - Asegurar que solo los miembros del grupo puedan modificar o acceder al contenido.
2. **Solucion:**
    a. **Crear un grupo y añadir usuarios:**
	``` bash
    sudo groupadd grupocompartido
	sudo usermod -aG grupocompartido usuario1 
	sudo usermod -aG grupocompartido usuario2
	```
    b. **Crear el directorio y establecer permisos:**
	``` bash    
# Solo el grupo tiene acceso completo.
    sudo mkdir /compartido 
	sudo chown :grupocompartido /compartido
	sudo chmod 770 /compartido  
```
	c. **Comprobar el acceso como diferentes usuarios:**
    - Inicia sesión como `usuario1` y crea un archivo:
		``` bash
        su - usuario1 
		touch /compartido/archivo1.txt
       ``` 
    - Inicia sesión como `usuario2` y edita el archivo:
		``` bash 
        su - usuario2 
		echo "Editado por usuario2" >> /compartido/archivo1.txt
		```
        
    - Intenta acceder al directorio como un usuario que no sea miembro del grupo:
		``` bash
	# Asegúrate de que usuario3 no está en el grupo.
		ls /compartido
	# Debería fallar.
        su - usuario3  
		```
	

- - - 
## ***Sources:***