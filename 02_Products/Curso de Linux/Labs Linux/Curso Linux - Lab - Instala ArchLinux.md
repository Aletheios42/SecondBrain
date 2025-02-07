**Tags:** #_Todo
#ToTag #ToLink 
- - -
Si cambias propiedades de red. como reglas de firewall o nat into bridge... tienes que apagar la maquina y volverla a encerder para hacer efectivos los cambios
==Entender como hacer la instalacion desde ssh, todos los problemas con las redes puertos tipos de conexion etc==
# Hacer la maquina en Virtual Box
``` bash
# en tu host para permitir la conexion ssh
VBoxManage modifyvm "NombreDeTuVM" --natpf1 "ssh,tcp,,2222,,22"
```
Si prefieres hacerlo por GUI:

Abre VirtualBox
Selecciona tu VM
Ve a Configuración > Red > Avanzado > Reenvío de Puertos
Agrega una regla:
Nombre: SSH
Protocolo: TCP
Puerto Anfitrión: 2222
Dirección Anfitrión: (dejar vacío)
Puerto Huésped: 22
Dirección Huésped: (dejar vacío)

# Corriendo el Medio de Booteo ISO
- - - 
``` bash
# Para poder tener el teclado en espñol
loadkeys es
```
- - - 
## Internet 
### Comprobar arquitectura de red en caso de virtualizar
==CON EL CABLE CONECTADO EN LAS OPCIONES EXPERTO DE RED EN VBOX==
### Como usar IWCTL (USB - BareMetal)
``` bash
iwctl
> scan devices
> iwctl show address
> station wlan0 scan
> station wlan0 connect SSID
exit
ping archlinux.org
```
## Conectarte por ssh
En el medio de instalacion:
``` bash
# Mirar  si la red enp0s3 o eth0 estan UP
ip a
```
==Ver como se resuelve no tener la tarjate de red activa(probable systemctl)==

### ACTIVAR EL DEMONIO SSH(En el medio de instalacion)
Activamos ssh. El medio de instalación de Arch trae sshd, pero no siempre está habilitado. Actívalo manualmente:
```bash
systemctl start sshd
```
Verifica que está corriendo:
```bash
systemctl status sshd
```
Configura una contraseña para el root
```bash
passwd
```

- - - 
1. Boot from the Arch Linux ISO and verify boot mode:
==VIRTUALIZANDO NO TENDRAS ESTO==
``` bash
cat /sys/firmware/efi/fw_platform_size
```

1. Update system clock:
```bash
timedatectl set-ntp true
```

### Establecer sistema de archivos

```markdown
# Instalación de Arch Linux: Particionado, Formateo y Montaje

Para instalar Arch Linux correctamente, debemos seguir tres pasos fundamentales:  
1. **Configurar la tabla de particiones** utilizando `fdisk`.  
2. **Formatear las particiones** con los sistemas de archivos adecuados.  
3. **Montar las particiones** en los puntos correspondientes para la instalación.  

---

## 1️⃣ Configurar la Tabla de Particiones

Primero, verificamos los discos disponibles:  

```bash
fdisk -l
```

Iniciamos `fdisk` en el disco destino (`/dev/sdX` debe ser reemplazado por el disco correcto en tu sistema):  

```bash
fdisk /dev/sdX
```

Dentro de `fdisk`, creamos las particiones:

```bash
g      # Crear nueva tabla de particiones GPT

n      # Crear partición EFI
       # (presiona Enter para valores por defecto)
       # Último sector: +550M
t      # Cambiar tipo de partición
1      # Seleccionar la partición EFI
uefi   # Cambiar tipo a EFI System (ESP)

n      # Crear partición swap
       # Último sector: +2G  (Ajusta según tu RAM)
t      # Cambiar tipo de partición
2      # Seleccionar la partición swap
swap   # Cambiar tipo a Linux swap

n      # Crear partición raíz (resto del disco)
       # (presiona Enter para valores por defecto)

w      # Guardar cambios y salir
```
## 2️⃣ Formatear las Particiones

Una vez creadas las particiones, debemos formatearlas correctamente:

```bash
mkfs.fat -F32 /dev/sdX1   # Formatear partición EFI en FAT32
mkswap /dev/sdX2          # Configurar partición swap
swapon /dev/sdX2          # Activar swap
mkfs.ext4 /dev/sdX3       # Formatear raíz en EXT4
```

> 💡 *Se usa EXT4 para la raíz por simplicidad. Si prefieres Btrfs o XFS, ajusta el formato.*
## 3️⃣ Montar las Particiones
Finalmente, montamos las particiones en los puntos adecuados:
```bash
mount /dev/sdX3 /mnt      # Montar la raíz
mkdir -p /mnt/boot        # Crear directorio de boot
mount /dev/sdX1 /mnt/boot # Montar EFI en boot
```
Con esto, el sistema de archivos está listo y podemos continuar con la instalación de Arch Linux. 
```bash
pacstrap /mnt base linux linux-firmware btrfs-progs base-devel vim
```
1. Generate fstab:
```bash
genfstab -U /mnt >> /mnt/etc/fstab
```
1. Chroot and configure:
```bash
arch-chroot /mnt
ln -sf /usr/share/zoneinfo/Region/City /etc/localtime
hwclock --systohc
vim /etc/locale.gen  # Uncomment en_US.UTF-8
locale-gen
echo "LANG=en_US.UTF-8" > /etc/locale.conf
echo "hostname" > /etc/hostname
```

2. Install and configure bootloader:
```bash
pacman -S grub efibootmgr
grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB
grub-mkconfig -o /boot/grub/grub.cfg
```

3. Set root password and create user:
```bash
passwd
useradd -m -G wheel username
passwd username
EDITOR=vim visudo  # Uncomment %wheel ALL=(ALL) ALL
```


- - - 


- - - 
``` bash

```
- - - 
``` bash

```



- - - 
## ***Sources:***
- [Descargar la Imagen](https://mirror.23m.com/archlinux/iso/latest/)