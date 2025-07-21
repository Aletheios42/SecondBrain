**MetaTags:** #_Done 
**Tags:** #Linux #C-Groups 
- - -
> los grupos de control, generalmente conocidos como cgroups, son una característica del kernel de linux que permite organizar los procesos en grupos jerárquicos cuyo uso de varios tipos de recursos puede ser entonces limitado y monitorizado.

la interfaz del kernel para acceder a los grupos de control es cgroupfs, no se gestiona a través de llamadas al sistema - syscalls, sino de archivos especiales*
montados en /sys/fs/cgroup en la mayoria de distribuciones.
```bash
$ mount -l | grep cgroup
cgroup2 on /sys/fs/cgroup type cgroup2 (rw,nosuid,nodev,noexec,relatime,nsdelegate,memory_recursiveprot)
```

#### controladores
los controladores son subsistemas del kernel que gestionan diferentes tipos de recursos: el archivo cgroup.controllers lista los controladores disponibles (activos)
- cpuset: asigna procesos a cpus/nodos de memoria específicos
- cpu: controla cuotas y prioridad de tiempo de cpu
- io: regula ancho de banda y prioridad de operaciones e/s
- memory: limita consumo de ram y swap
- hugetlb: controla asignación de páginas de gran tamaño
- pids: restringe número máximo de procesos en un cgroup

####   oom killer en cgroups

es el mecanismo para terminar proceso que se exceden en el gasto de recursos especificado en el c-group, similar al oom killer del sistema.
se gestiona desde la interfaz de kernel memory.oom.group, con 0(estado por defecto) termina el proceso que se exceda y con 1 termina toods los procesos de grupo de control.

```bash
# activar terminación de grupo completo en oom
echo 1 > /sys/fs/cgroup/programa/memory.oom.group

# ver si un proceso fue terminado por oom
dmesg | grep -i "out of memory"
```
#### delegacion.
mecanismo que permite a usuarios (no solo root) generar sus propios subarboles de cgroups. la arquitectura es top-down y se otorgan o quitan controladores con + .- 
``` bash ej.
$ echo "+cpu +memory -io" > /sys/fs/cgroup/<parent>/cgroup.subtree_control
```

### metodos para interactuar con los c-groups

##### como archivos

```bash
$ mkdir /sys/fs/cgroup/programa
```
creara todos los archivos de control automaticamente donde puedes asignar recursos a tus procesos ej.
``` bash
echo "50000 100000" > /sys/fs/cgroup/programa/cpu.max
```
> en sistemas multicores se puede pasar del 100% de cpu sin problema, cada core es un 100%

es muy util escribir el pid de tu shell para evitar que los hungry-process ej.
```bash
echo $$ >> /sys/fs/cgroup/programa/cgroup.procs
```

```bash
rmdir /sys/fs/cgroup/programa
```
a pesar de no ser un directorio vacio lo borrara pues estos archivos son en realidad interfaces de kernel. el comando **stat** da pistas sobre ello

##### libcgroup
instalación:
```bash
$ apt-get install cgroup-tools
# yum install libcgroup libcgroup-tools
```

administración:
```bash
$ cgcreate -g cpu,memory:programa
$ cgset -r cpu.max="50000 100000" programa      # establecer límites
$ cgclassify -g cpu,memory:programa ${programa_pid}  # mover proceso existente
$ cgexec -g cpu,memory:programa ~/programa           # ejecutar proceso dentro del cgroup
$ cgdelete -g cpu,memory:/programa
```

> libcgroup proporciona una interfaz de alto nivel para gestionar cgroups sin manipular directamente archivos de pseudo-sistema.

##### systemd
es la mejor manera de administrar tus cgroups, pues herramientas como docker y kubernettes  usan slides
mirar: https://kubernetes.io/docs/setup/production-environment/container-runtimes/#cgroup-drivers
https://www.freedesktop.org/software/systemd/man/latest/systemd.slice.html

system-run es una herramienta que permite correr procesos en segundo plano
systemd se integra directamente con el systema de cgroups del kernel
ofrece comando de monitoreo como:
```bash 
# listar unidades de control de grupos (ls)
systemd-cgls --all

# monitorear recursos utilizados por los c-groups (top)
systemd-cgtop
```

###### unidades transitorias
```bash ej
systemd-run -u \<nombre-unidad\> -p cpuquota=50% -p memorymax=100m ./programa
```

crea una unidad transitoria en /sys/fs/cgroup/system.slice/[nombre-unidad].service
con las propiedades especificadas para los controladores.

si el programa falla , es decir no devuelve en exit status de 0, la unidad no se limpia automaticamente y tendras que:
```bash
failed to start transient service unit:
unit <nombre-unidad>.service was already loaded or has a fragment file.


# error típico que se resuelve con estos comandos:

# opción 1: usar la bandera --collect al ejecutar para limpiar automáticamente unidades fallidas
systemd-run --collect -u nombre-unidad comando_que_podria_fallar

# opción 2: limpiar manualmente todas las unidades fallidas
systemctl reset-failed

```

###### unidades persistentes
para crear slices persistentes  se crean como cualquier otra unidad, cada proceso obtiene su propio cgroup hijo
todos los procesos comparten colectivamente los límites del slice


diferencia clave con cgroups transitorios:

los límites son acumulativos para todos los procesos en el slice
la configuración persiste entre reinicios
los procesos colocados en el slice heredan sus restricciones
```bash
# para crearla
cat <<eof > /etc/systemd/system/hog_pen.slice
[slice]
cpuquota=50%
memorymax=100m
eof

# para activarla
systemctl daemon-reload 
```

se puede integrar con docker

```bash
docker run -d --name web --cgroup-parent=nombre.slice nginx
docker run -d --name rdb --cgroup-parent=nombre.slice redis
```

- - - 
#### ***sources:***
- [Control Group v2 - The Linux kernel user's and administrator's guide](https://docs.kernel.org/admin-guide/cgroup-v2.html)
- [cgroups(7) - Linux man pages](https://man7.org/linux/man-pages/man7/cgroups.7.html)
- [Using libcgroup Tools - Red Hat Enterprise Linux Documentation](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/7/html/resource_management_guide/chap-using_libcgroup_tools)
- [cgroups - ArchWiki](https://wiki.archlinux.org/title/Cgroups)
- [systemd-run — Run programs in transient scope and service units](https://www.freedesktop.org/software/systemd/man/latest/systemd-run.html)
- [systemd.slice — Slice unit configuration](https://www.freedesktop.org/software/systemd/man/latest/systemd.slice.html)