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

- - - 
``` bash
# Para poder tener el teclado en espñol
loadkeys es
```
- - - 
# Internet 
 SI lo haces desde maquina virtual con NAT ya tienes internet 
==CON EL CABLE CONECTADO EN VBOX==
### Como usar IWCTL
``` bash
iwctl
> scan devices
> iwctl show address
> station wlan0 scan
> station wlan0 connect SSID
exit
ping archlinux.org
```
# Conectarte por ssh
En el medio de instalacion:
``` bash
# Mirar  si la red enp0s3 o eth0 estan UP
ip a
```
==Ver como se resuelve no tener la tarjate de red activa(probable systemctl)==

### ACTIVAR EL DEMONIO SSH
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

2. Partition disk (example for UEFI with /dev/nvme0n1):
```bash
# Create:
# /dev/nvme0n1p1: EFI (550M)
# /dev/nvme0n1p2: swap (RAM x 1.5)
# /dev/nvme0n1p3: root (remaining)
# Ver discos disponibles
fdisk -l

# Iniciar fdisk
fdisk /dev/sda

# Crear particiones:
g   # Nueva tabla GPT
n   # Nueva partición boot (500M)
    # (presiona Enter para defaults)
    # Last sector: +500M
t   # Cambiar tipo a EFI (1)

n   # Nueva partición swap (2GB)
    # Last sector: +2G
t   # Cambiar tipo a Linux swap (19)

n   # Nueva partición root (resto)
    # (usa valores default)

w   # Guardar y salirV
```

3. Format partitions:
```bash
mkfs.fat -F32 /dev/nvme0n1p1
mkswap /dev/nvme0n1p2
mkfs.btrfs /dev/nvme0n1p3
```

4. Mount and create subvolumes for snapshots:
```bash
mount /dev/nvme0n1p3 /mnt
btrfs subvolume create /mnt/@
btrfs subvolume create /mnt/@home
btrfs subvolume create /mnt/@snapshots
umount /mnt
```

5. Mount subvolumes:
```bash
mount -o noatime,compress=zstd,space_cache=v2,subvol=@ /dev/nvme0n1p3 /mnt
mkdir -p /mnt/{boot,home,.snapshots}
mount -o noatime,compress=zstd,space_cache=v2,subvol=@home /dev/nvme0n1p3 /mnt/home
mount -o noatime,compress=zstd,space_cache=v2,subvol=@snapshots /dev/nvme0n1p3 /mnt/.snapshots
mount /dev/nvme0n1p1 /mnt/boot
swapon /dev/nvme0n1p2
```

6. Install base system:
```bash
pacstrap /mnt base linux linux-firmware btrfs-progs base-devel vim
```

7. Generate fstab:
```bash
genfstab -U /mnt >> /mnt/etc/fstab
```

8. Chroot and configure:
```bash
arch-chroot /mnt
ln -sf /usr/share/zoneinfo/Region/City /etc/localtime
hwclock --systohc
vim /etc/locale.gen  # Uncomment en_US.UTF-8
locale-gen
echo "LANG=en_US.UTF-8" > /etc/locale.conf
echo "hostname" > /etc/hostname
```

9. Install and configure bootloader:
```bash
pacman -S grub efibootmgr
grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB
grub-mkconfig -o /boot/grub/grub.cfg
```

10. Set root password and create user:
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