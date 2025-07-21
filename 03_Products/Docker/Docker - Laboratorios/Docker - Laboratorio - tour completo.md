**MetaTags:** #_Todo
**Tags:** #ToTag #ToLink 
- - -


Aquí tienes el laboratorio ampliado y enriquecido con los pasos adicionales que me pediste. El flujo está diseñado para que el alumno entienda la interacción entre `docker run`, el modo interactivo, el shell, `docker inspect`, y el comportamiento de procesos como `sleep` con o sin `-it`.

---

# Laboratorio Docker Completo: Ejecución, inspección y gestión de contenedores

---

### Paso 1: Buscar imagen

```bash
docker search centos
```

**Pregunta:**

* ¿Qué datos muestra? ¿Cuál usarías y por qué?

---

### Paso 2: Ejecutar contenedor sin argumentos (CMD por defecto)

```bash
docker run centos:7
```

**Pregunta:**

* ¿Qué sucede?
* ¿Por qué termina inmediatamente?
* ¿Cómo se relaciona esto con el campo `CMD` o `ENTRYPOINT` de la imagen?

---

### Paso 3: Ejecutar contenedor con modo interactivo y terminal

```bash
docker run -it centos:7
```

**Pregunta:**

* ¿Qué cambia respecto al paso 2?
* ¿Qué proceso corre en el contenedor?
* ¿Cómo interactúas con él?

---

### Paso 4: Ejecutar otro contenedor con shell explícito

```bash
docker run -it centos:7 /bin/sh
```

**Pregunta:**

* ¿Por qué usamos `/bin/sh` o `/bin/bash` explícitamente?
* ¿Qué diferencia hay entre esto y el paso 3?

---

### Paso 5: En otra terminal, inspeccionar el contenedor en ejecución

Encuentra el ID o nombre con:

```bash
docker ps
```

Luego inspecciona con:

```bash
docker inspect <CONTAINER_ID_or_NAME> | grep -A5 '"Cmd"'
```

**Pregunta:**

* ¿Qué muestra el campo `"Cmd"`?
* ¿Cómo afecta esto a la ejecución del contenedor?

---

### Paso 6: Ejecutar un contenedor con `sleep infinity` sin modo interactivo

```bash
docker run centos:7 sleep infinity
```

**Pregunta:**

* ¿Por qué tu terminal se "libera" inmediatamente?
* ¿Qué pasa dentro del contenedor?
* ¿Qué sucede con stdin y tty?

---

### Paso 7: Ejecutar un contenedor con `sleep infinity` y modo interactivo

```bash
docker run -it centos:7 sleep infinity
```

**Pregunta:**

* ¿Qué cambia respecto al paso 6?
* ¿Para qué sirve la conexión tty?

---

### Paso 8: Ejecutar un `docker exec` en el contenedor de sleep

En otra terminal:

```bash
docker ps
docker exec -it <CONTAINER_ID_or_NAME> /bin/sh
ps aux
```

**Pregunta:**

* ¿Qué procesos ves?
* ¿Cómo te permite `docker exec` interactuar con el contenedor?

---

### Paso 9: Detach del contenedor interactivo

Dentro del contenedor, presiona:

```
Ctrl+P Ctrl+Q
```

**Pregunta:**

* ¿Qué ocurre con el contenedor y tu sesión?
* ¿Puedes seguir interactuando?

---

### Paso 10: Parar el contenedor

```bash
docker stop <CONTAINER_ID_or_NAME>
```

**Pregunta:**

* ¿Qué señal recibe el proceso dentro del contenedor?
* ¿Qué pasa si el proceso ignora SIGTERM?
* ¿Cómo afecta esto a tu terminal si estás en foreground?

---
### Paso 11: Eliminar el contenedor

Para eliminar el contenedor después de haberlo parado, ejecuta:

```bash
docker rm <CONTAINER_ID_or_NAME>
```

**Pregunta:**

* ¿Qué diferencia hay entre `docker stop` y `docker rm`?
* ¿Qué pasa si intentas eliminar un contenedor que está corriendo?
* ¿Por qué es importante limpiar contenedores que ya no usas?

---
### Pregunta final

Explica el flujo de ejecución y gestión del contenedor desde:

* La creación y ejecución (`docker run`)
* La interacción (modos `-it` o no)
* La ejecución de procesos con o sin tty
* La inspección del campo `"Cmd"`
* La detención y señales recibidas

¿Cómo se comporta tu terminal y qué bloqueos o liberaciones ocurren en cada paso?


---
#### ***Sources:***