**MetaTags:** #_Todo
**Tags:** #Linux #ToLink 
- - -
Un **proceso** es una instancia en ejecución de un programa que consiste en:
Un programa puede lanzar otros programas, lo que se expresa en el esquema de procesos como un **proceso padre** que produce un **proceso hijo**.

- **Espacio de direcciones virtual privado y protegido**.
- **Segmentos de memoria**:
  - **Texto**: Código ejecutable.
  - **Datos**: Variables globales/estáticas.
  - **Heap**: Memoria dinámica.
  - **Stack**: Variables locales e información de llamadas.

## Tipos de Procesos

1. **Foreground (Primer plano)**: Requieren interacción con el usuario.
2. **[[Jobs en Linux|Background]]:**: Se ejecutan sin intervención del usuario.
3. **Daemon (Demonios)**: Procesos del sistema que corren en segundo plano.

## Estados de un Proceso

- **Running**: En ejecución.
- **Sleeping**: Esperando un recurso.
- **Zombie**: Proceso finalizado que aún está en la tabla de procesos.
- **Stopped**: Detenido por el usuario.

## Diferencia entre Programa y Proceso

- **Programa**: Conjunto de instrucciones escritas en un lenguaje de programación (código fuente o binario).
- **Proceso**: Instancia en ejecución de un programa, con su propio espacio de memoria y estado.

## Process Control Block (PCB)

Estructura que contiene información sobre un proceso:

- **Process ID único (PID)**.
- **Program Counter**.
- **Registros de CPU**.
- **Estado del proceso**.
- **Información de scheduling**: Prioridad del proceso (se puede modificar con `renice -n PID`).

[[Proceso Zombie]]
---

==Meterlos==

- clases forward backwards y daemon
- **PID (Process ID):** Identificador único de un proceso.
- **PPID (Parent Process ID):** ID del proceso padre.

- - -
## **_Sources:_**

- https://www.youtube.com/watch?v=7ge7u5VUSbE

