**Tags:** #_Todo
#ToTag #ToLink 
- - -
==Terner la practica de multiplexores y aplicar los patrones==
==Mejoras los ejercicios para tener en cuenta los diferentes patrones de paneles y ventanas==
==Explora la idea de que cada ejercico sea una sesion==
# **Clase: Introducción a los Procesos en Linux**  
### **💻 Práctica**  
Ejecutar y observar procesos en tiempo real:  
```bash
ps aux | less  # Ver procesos activos
top  # Monitor interactivo de procesos
htop  # Alternativa con interfaz mejorada (si está instalado)
```

---

## **📌 2. Identificación y Administración de Procesos (30 min)**  
### **📖 Teoría**  
- **UID/GID:** Usuario y grupo propietario del proceso.  
- **Cómo encontrar información de un proceso específico.**  

### **💻 Práctica**  
```bash
ps -ef | grep bash  # Buscar procesos de bash
pidof firefox  # Encontrar PID de una aplicación
pgrep -l ssh  # Buscar procesos relacionados con SSH
```

---

## **📌 3. Creación, Suspensión y Terminación de Procesos (30 min)**  
### **📖 Teoría**  
- Comandos básicos para ejecutar y controlar procesos:  
  - `&` (Ejecutar en segundo plano).  
  - `jobs` (Listar trabajos en la sesión actual). 
  - `fg` y `bg` (Mover procesos entre primer y segundo plano).  
- **Señales de proceso:**  
  - `SIGKILL (9)`: Mata un proceso inmediatamente.  
  - `SIGTERM (15)`: Solicita una terminación educada.  
  - `SIGSTOP (19)`: Pausa un proceso.  
  - `SIGCONT (18)`: Reanuda un proceso.  

### **💻 Práctica**  
```bash
sleep 60 &  # Crear un proceso en segundo plano
jobs  # Ver procesos en la sesión
fg %1  # Traer proceso de vuelta a primer plano
kill -STOP <PID>  # Pausar proceso
kill -CONT <PID>  # Reanudar proceso
kill -9 <PID>  # Forzar terminación
```

---

## **📌 4. Priorización y Gestión Avanzada de Procesos (30 min)**  
### **📖 Teoría**  
Los procesos en Linux tienen prioridades que afectan su acceso a los recursos de CPU. La prioridad se maneja con un valor llamado **niceness** (nivel de amabilidad).  

- **Nice Value (Valor nice):** Rango de `-20` (mayor prioridad) a `19` (menor prioridad).  
- **Renice:** Modifica la prioridad de un proceso en ejecución.  
- **Top y Htop:** Monitorizan procesos en tiempo real y permiten cambiarlos fácilmente.  
- **Systemd:** Gestiona servicios del sistema y procesos en segundo plano.  

---

### **💻 Práctica**  

#### **1️⃣ Modificar la prioridad al iniciar un proceso**  
Ejecuta un comando con diferente prioridad:  
```bash
nice -n 10 sleep 300  # Ejecutar con menor prioridad
```
- `nice -n 10` → Ejecuta el proceso con prioridad baja (menos CPU).  
- `sleep 300` → Simula un proceso de larga duración.  

Verifica el **nice value** del proceso:  
```bash
ps -eo pid,comm,nice | grep sleep
```

---

#### **2️⃣ Cambiar la prioridad de un proceso en ejecución**  
Primero, encuentra el PID del proceso:  
```bash
ps aux | grep sleep
```
Luego, aumenta su prioridad (haciéndolo más importante para el sistema):  
```bash
renice -5 -p <PID>
```
Verifica el cambio con:  
```bash
ps -eo pid,comm,nice | grep sleep
```

---

#### **3️⃣ Monitoreo y gestión interactiva con `top` o `htop`**  
Abre `top` y observa la columna **NI** (nice value):  
```bash
top
```
Para modificar la prioridad dentro de `top`:  
1. Presiona `r`.  
2. Introduce el **PID** del proceso.  
3. Escribe un nuevo valor de **nice** (por ejemplo, `-10`).  

Alternativamente, usa `htop` (si está instalado):  
```bash
htop
```
- Navega con las flechas hasta un proceso.  
- Presiona `F7` para aumentar la prioridad o `F8` para reducirla.  

---

#### **4️⃣ Administración de servicios con `systemctl`**  
Verifica el estado de un servicio del sistema (por ejemplo, SSHD):  
```bash
systemctl status sshd
```
Reinicia el servicio si es necesario:  
```bash
sudo systemctl restart sshd
```
Detén un servicio temporalmente:  
```bash
sudo systemctl stop sshd
```
Inicia un servicio que estaba detenido:  
```bash
sudo systemctl start sshd
```

---

## **📌 5. Conclusión y Preguntas (10 min)**  
- Resumen de lo aprendido.  
- Espacio para preguntas y discusión.  

---

## **📌 Resumen General**
- `nice` → Ejecuta un proceso con una prioridad específica.  
- `renice` → Cambia la prioridad de un proceso en ejecución.  
- `top` / `htop` → Monitorean procesos y permiten ajustar prioridades.  
- `systemctl` → Gestiona servicios del sistema.  

- - - 
## ***Sources:***