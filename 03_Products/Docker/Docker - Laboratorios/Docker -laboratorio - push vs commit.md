**MetaTags:** #_Todo
**Tags:** #ToTag #ToLink 
- - -
# 🐳 Laboratorio Docker: Persistencia de datos y diferencias entre contenedores e imágenes

## 🎯 Objetivos

- Entender por qué los cambios en un contenedor **no modifican** su imagen base.
- Comparar tres estrategias para persistir cambios:
  1. `docker push` (fallido sin `commit`)
  2. `docker commit`
  3. Uso de `Dockerfile`
  4. Uso de volúmenes

---

## 🧪 Parte 1: Simulación de persistencia (Push sin Commit)

> El objetivo es engañar al alumno: simular que un cambio se va a guardar con `push`, pero no ocurre.

### 1. Descargar la imagen base

```bash
docker pull busybox
```

### 2. Crear un contenedor y modificar su sistema de archivos

```bash
docker run -it busybox sh
```

Dentro del contenedor:

```sh
echo "Este archivo será ignorado" > /mock.txt
exit
```

### 3. Etiquetar y hacer push

```bash
docker tag busybox alumno/busybox-falsa
docker push alumno/busybox-falsa
```

### 4. Verificar en una nueva ejecución

```bash
docker run --rm alumno/busybox-falsa cat /mock.txt
```

**❌ Resultado esperado:**

```text
cat: can't open '/mock.txt': No such file or directory
```

---

## 🧠 Pregunta

> ¿Por qué no aparece el archivo si el contenedor lo tenía? ¿Qué hace realmente `docker push`?

---

## ✅ Parte 2: Persistencia real usando `docker commit`

### 1. Repetir la creación del archivo

```bash
docker run -it busybox sh
```

```sh
echo "Ahora sí persistimos el cambio" > /mock.txt
exit
```

### 2. Crear nueva imagen con `commit`

```bash
docker ps -a         # obtener CONTAINER ID
docker commit <ID> alumno/busybox-real
```

### 3. (Opcional) Push al registro

```bash
docker push alumno/busybox-real
```

### 4. Verificación

```bash
docker run --rm alumno/busybox-real cat /mock.txt
```

**✅ Resultado esperado:**

```text
Ahora sí persistimos el cambio
```

---

## 🧠 Pregunta

> ¿Qué diferencias ves entre `docker commit` y `docker push`?

---

## 🛠️ Parte 3: Persistencia a través de Dockerfile

### 1. Crear un `Dockerfile`

```Dockerfile
# Dockerfile
FROM busybox
RUN echo "Este archivo fue añadido desde un Dockerfile" > /mock.txt
```

### 2. Construir la imagen

```bash
docker build -t alumno/busybox-dockerfile .
```

### 3. Verificar

```bash
docker run --rm alumno/busybox-dockerfile cat /mock.txt
```

**✅ Resultado esperado:**

```text
Este archivo fue añadido desde un Dockerfile
```

---

## 🧠 Pregunta

> ¿Qué ventajas tiene el `Dockerfile` respecto a `commit`?  
> ¿Qué ventaja tiene `commit` respecto al `Dockerfile`?

---

## 📦 Parte 4: Uso de volúmenes

> Ahora el archivo no está dentro de la imagen, sino persistido fuera, en el host.

### 1. Crear volumen

```bash
docker volume create data-volume
```

### 2. Usar volumen y escribir archivo

```bash
docker run -it -v data-volume:/data busybox sh
```

```sh
echo "Este archivo vive fuera del contenedor" > /data/host.txt
exit
```

### 3. Verificar desde otro contenedor

```bash
docker run --rm -v data-volume:/data busybox cat /data/host.txt
```

**✅ Resultado esperado:**

```text
Este archivo vive fuera del contenedor
```

---

## 🧠 Preguntas finales

- ¿Qué diferencia fundamental hay entre una imagen, un contenedor y un volumen?
- ¿Qué estrategia elegirías para:
  - Entornos de producción?
  - Experimentos rápidos?
  - Generar imágenes reproducibles?

---

## 🧹 Limpieza final

```bash
docker rm -f $(docker ps -aq)               # eliminar contenedores
docker rmi alumno/busybox-falsa             # eliminar imagen falsa
docker rmi alumno/busybox-real              # eliminar imagen real
docker rmi alumno/busybox-dockerfile        # eliminar imagen Dockerfile
docker volume rm data-volume                # eliminar volumen
```

- - - 
#### ***Sources:***