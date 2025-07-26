**Tags:** #_Todo
**MetaTags:** #Disco #Linux #ToLink 
- - -
### 🔹 **Información General del Disco**
 **Listar discos y sus particiones:**  
```bash
lsblk -fm
```
- Muestra dispositivos, tamaños, sistemas de archivos, etiquetas y UUIDs.  
- Opción `-f` incluye información sobre el sistema de archivos.  
- Opción `-m` muestra permisos y usuarios propietarios.  

 **Ver detalles de todos los discos y particiones (con tamaños y tipos de sistema de archivos):**  
```bash
fdisk -l
```
- Útil para ver estructuras de partición y tamaños.  
- Si solo quieres un disco específico:  
  ```bash
  fdisk -l /dev/sdX
  ```

 **Identificar los dispositivos de bloque y su relación con nombres de discos físicos:**  
```bash
lsblk -o NAME,FSTYPE,SIZE,MOUNTPOINT,UUID,PARTLABEL
```
- Muestra nombres, sistema de archivos, tamaño, puntos de montaje, UUID y etiquetas.  

---

### 🔹 **Estado SMART del Disco (Salud y Errores)**
 **Comprobar el estado SMART (para discos HDD/SSD):**  
```bash
sudo smartctl -a /dev/sdX
```
- Requiere `smartmontools`.  
- Usa `-H` para ver solo el estado de salud del disco:  
  ```bash
  sudo smartctl -H /dev/sdX
  ```

 **Realizar una prueba rápida del disco:**  
```bash
sudo smartctl -t short /dev/sdX
```
- Para una prueba completa:  
  ```bash
  sudo smartctl -t long /dev/sdX
  ```

---

### 🔹 **Uso de Espacio y Tipo de Sistema de Archivos**
 **Mostrar sistemas de archivos montados y espacio usado:**  
```bash
df -hT
```
- `-h` → Tamaño legible  
- `-T` → Muestra el tipo de sistema de archivos  

 **Ver información detallada sobre una partición específica:**  
```bash
sudo tune2fs -l /dev/sdX3  # Para EXT4
```
- Muestra UUID, último montaje, número de bloques, etc.  

 **Para sistemas Btrfs:**  
```bash
btrfs filesystem df /mnt
```
- Muestra el uso real de espacio en una partición Btrfs.  

 **Para sistemas XFS:**  
```bash
xfs_info /mnt
```

---

### 🔹 **Velocidad y Rendimiento del Disco**
 **Medir velocidad de lectura secuencial:**  
```bash
sudo hdparm -Tt /dev/sdX
```
- `-T` mide la velocidad de caché.  
- `-t` mide la velocidad de lectura directa del disco.  

 **Benchmark de lectura con `dd` (⚠️ NO HACER SI EL DISCO ESTÁ EN USO):**  
```bash
sudo dd if=/dev/sdX of=/dev/null bs=4M count=1000 status=progress
```
- Lee datos sin escribirlos, útil para ver la velocidad de lectura.  

---

### 🔹 **Buscar Errores y Sectores Dañados**
 **Escaneo de sectores defectuosos (⚠️ Puede tardar mucho en discos grandes):**  
```bash
sudo badblocks -sv /dev/sdX
```
- `-s` → Muestra progreso  
- `-v` → Modo detallado  

 **Buscar errores en particiones EXT4:**  
```bash
sudo e2fsck -f /dev/sdX3
```
- `-f` → Fuerza la comprobación  

 **Verificar sectores dañados en un SSD (NVMe):**  
```bash
sudo nvme smart-log /dev/nvme0
```

---

### 🔹 **Ver Información del Hardware del Disco**
 **Obtener detalles del modelo, serial y firmware:**  
```bash
sudo hdparm -I /dev/sdX
```
 **Para discos NVMe:**  
```bash
sudo nvme list
```
 **Para ver información con `lsscsi` (si está instalado):**  
```bash
lsscsi -s
```

##  **Conclusión**
Si solo quieres un **resumen rápido del estado del disco**, usa:
```bash
lsblk -fm && df -hT && sudo smartctl -H /dev/sdX
```
Si buscas algo más profundo, usa `smartctl -a`, `badblocks`, o `hdparm` para analizar rendimiento.  
- - - 
## ***Sources:***