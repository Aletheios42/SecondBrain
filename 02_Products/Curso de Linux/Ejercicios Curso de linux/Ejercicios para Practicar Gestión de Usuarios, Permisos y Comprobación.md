**Tags:** #_Todo
#ToTag #ToLink 
- - -

#### Ejercicio 0
hacer sudo su; passwd
#### **Ejercicio 1: Crear Usuarios y Asignar Permisos a Archivos**

1. **Objetivo:**
    
    - Crear dos usuarios: `usuario1` y `usuario2`.
    - Crear un archivo accesible solo para `usuario1`.
    - Verificar que `usuario2` no pueda acceder al archivo.
2. **Pasos:**
    
    a. **Crear los usuarios:**
    
    
    `sudo useradd usuario1 sudo useradd usuario2 sudo passwd usuario1 sudo passwd usuario2`
    
    b. **Iniciar sesión como `usuario1` y crear un archivo:**
    
    
    `su - usuario1 touch archivo_usuario1.txt echo "Este archivo pertenece a usuario1" > archivo_usuario1.txt chmod 600 archivo_usuario1.txt  # Permisos: solo el propietario puede leer y escribir. exit`
    
    c. **Iniciar sesión como `usuario2` y comprobar acceso:**
    
    
    `su - usuario2 cat /home/usuario1/archivo_usuario1.txt  # Debería dar un error de permisos. exit`
    
    d. **Modificar los permisos para que ambos puedan leerlo:**
    
    
    `sudo chmod 640 /home/usuario1/archivo_usuario1.txt sudo chgrp $(id -gn usuario2) /home/usuario1/archivo_usuario1.txt su - usuario2 cat /home/usuario1/archivo_usuario1.txt  # Ahora debería ser legible. exit`
    

---

#### **Ejercicio 2: Cambiar Propietario y Permisos de Archivos**

1. **Objetivo:**
    
    - Crear un archivo como `root`.
    - Cambiar el propietario a `usuario1`.
    - Modificar permisos para que todos los usuarios puedan leerlo pero solo `usuario1` pueda escribir.
2. **Pasos:**
    
    a. **Crear el archivo como `root`:**
    
    bash
    
    CopyEdit
    
    `sudo touch /tmp/archivo_root.txt sudo echo "Creado por root" > /tmp/archivo_root.txt`
    
    b. **Cambiar el propietario y el grupo del archivo a `usuario1`:**
    
    `sudo chown usuario1:usuario1 /tmp/archivo_root.txt`
    
    c. **Modificar los permisos:**
    
    `sudo chmod 644 /tmp/archivo_root.txt  # Todos pueden leer, solo usuario1 puede escribir.`
    
    d. **Comprobar los permisos:**
    
    - Inicia sesión como `usuario1` y escribe en el archivo:
        `su - usuario1 echo "Modificado por usuario1" >> /tmp/archivo_root.txt exit`
        
    - Inicia sesión como `usuario2` e intenta escribir:
        `su - usuario2 echo "Intento modificar" >> /tmp/archivo_root.txt  # Debería fallar. exit`
        

---

#### **Ejercicio 3: Permisos Avanzados con Directorios**

1. **Objetivo:**
    
    - Crear un directorio con permisos de escritura para un grupo compartido.
    - Asegurar que solo los miembros del grupo puedan modificar o acceder al contenido.
2. **Pasos:**
    
    a. **Crear un grupo y añadir usuarios:**
    
    `sudo groupadd grupocompartido sudo usermod -aG grupocompartido usuario1 sudo usermod -aG grupocompartido usuario2`
    
    b. **Crear el directorio y establecer permisos:**
    
    `sudo mkdir /compartido sudo chown :grupocompartido /compartido sudo chmod 770 /compartido  # Solo el grupo tiene acceso completo.`
    
    c. **Comprobar el acceso como diferentes usuarios:**
    
    - Inicia sesión como `usuario1` y crea un archivo:
        `su - usuario1 touch /compartido/archivo1.txt exit`
        
    - Inicia sesión como `usuario2` y edita el archivo:
        `su - usuario2 echo "Editado por usuario2" >> /compartido/archivo1.txt exit`
        
    - Intenta acceder al directorio como un usuario que no sea miembro del grupo:
        `su - usuario3  # Asegúrate de que usuario3 no está en el grupo. ls /compartido  # Debería fallar. exit`

- - - 
## ***Sources:***