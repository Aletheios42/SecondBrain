**Tags:** #_Done 
#Linux   #ToLink 
- - -
# Guided Exercises
##### 1. Which partitioning scheme should be used to partition a 3 TB hard disk into three 1 GB partitions? Why?
- R: GPT porque MBR solo soporta 2TB
##### 2. On gdisk, how can we find out how much space is available on the disk?
- R: p
##### 3. What would be the command to create an ext3 filesystem, checking for bad blocks before, with the label MyDisk and a random UUID, on the device /dev/sdc1?
- R: mkfs.ext3 -c -L MyDisk -U random /dev/sdc1.
##### 4. Using parted, what is the command to create a 300 MB ext4 partition, starting at 500 MB on the disk?
- R: creas la particion con  mkfs.ext4 y la formateas con  mkpart primary ext4 500m 800m.
##### 5. Imagine you have 2 partitions, one on /dev/sda1 and the other on /dev/sda2, both 20 GB in size. How can you use them on a single Btrfs filesystem, in such a way that the contents of one partition will be automatically mirrored on the other, like on a RAID1 setup? How big will the filesystem be?
- R: mkfs.btrfs /dev/sda1 /dev/sdb1 -m raid1

# Explorational Exercises
##### 1. Consider a 2 GB disk with an MBR partition table and the following layout:
```
Disk /dev/sdb: 1.9 GiB, 1998631936 bytes, 3903578 sectors
Disk model: DataTraveler 2.0
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x31a83a48

Device     Boot   Start     End Sectors  Size Id Type
/dev/sdb1         2048  1050623 1048576  512M 83 Linux
/dev/sdb3      2099200  3147775 1048576  512M 83 Linux
```
 Can you create a 600 MB partition on it? Why?
- R:  vemos que el espacion libre esta en 2 sitios entre el sector 1048576 y 2099200,
y entre 3147775 hasta el final. asi que hagamos los calculos, teniendo en cuenta que cada bloque mide 512KB y la relacion entre las MB y GB esta a escala 1024 
Primer candidato: (2099200 - 1048576) * 512  / 1024 / 1024= 513MB insuficiente
Segundo candidato (1.9GB * 1024) - (3147775 * 512 / 1024 / 1024) = 409.6 MB insuficiente
asi que no se puede.
##### 2. On a disk at /dev/sdc, we have a first partition of 1 GB, containing about 256 MB of files. Using parted, how can you shrink it so it has just enough space for the files?
- R:  primero resize2fs -M /dev/sdc1. y luego resizepart 1 241M.
##### 3. Imagine you have a disk at /dev/sdb, and you want to create a 1 GB swap partition at the start of it. So, using parted, you create the partition with mkpart primary linux-swap 0 1024M. Then, you enable swap on this partition with swapon /dev/sdb1, but get the following error message: swapon: /dev/sdb1: read swap header failed What went wrong?
- R: que parted solo formatea antes tienes que crear la particion con: mkswap
##### 4. During the course of this lesson, you were trying out some commands in parted but, bymistake, deleted the 3rd partition on your hard disk. You know that it came after a 250 MB UEFI partition and a 4 GB swap partition, and was 10 GB in size. Which command can you use to recover it?
- R: rescue 4346m 14586m
##### 5. Imagine you have a 4 GB unused partition on /dev/sda3. Using fdisk, what would be the sequence of operations to turn it into an active swap partition?
- R: First, change the partition type to “Linux Swap” (82), write your changes to disk and quit. Then, use mkswap to set up the partition as a swap area. Then, use swapon to enable it.

- - - 
## ***Sources:***