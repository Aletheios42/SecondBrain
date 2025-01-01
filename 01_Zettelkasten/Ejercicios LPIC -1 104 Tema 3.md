**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. Using mount, how can you mount an ext4 filesystem on /dev/sdc1 to /mnt/external as read-only, using the noatime and async options?
- R: mount -t ext4 -o noatime,async,ro /dev/sdc1 /mnt/external 
##### 2. When unmounting a filesystem at /dev/sdd2, you get the target is busy error message. How can you find out which files on the filesystem are open, and what processes opened them?
- R:   lsof /dev/sdd2
##### 3. Consider the following entry in /etc/fstab: /dev/sdb1 /data ext4 noatime,noauto,async. Will this filesystem be mounted if the command mount -a is issued?Why?
- R: no ya mount all no monta con la opcion noauto
##### 4. How can you find out the UUID of a filesystem under /dev/sdb1?
- R:  lsblk -f /dev/sdb1
##### 5. How can you use mount to remount as read-only an exFAT filesystem with the UUID 6e2c12e3-472d-4bac-a257-c49ac07f3761, mounted at /mnt/data?
- R:   mount -o remount,ro /mnt/data
##### 6. How can you get a list of all ext3 and ntfs filesystems currently mounted on a system?
- R:   mount -t ext3,ntfs
# Explorational Exercises
##### 1. Consider the following entry in /etc/fstab: /dev/sdc1 /backup ext4noatime,nouser,async. Can a user mount this filesystem with the command mount /backup? Why?
- R: solo root, porque tiene paramentro nouser
##### 2. Consider a remote filesystem mounted at /mnt/server, which has become unreachable due to a loss of network connectivity. How could you force it to be unmounted, or mounted as read- only if this is not possible?
- R:   umount -f -r /mnt/server. 
##### 3. Write an /etc/fstab entry that would mount a btrfs volume with the label Backup on /mnt/backup, with default options and without allowing the execution of binaries from it.
- R:    LABEL=Backup /mnt/backup btrfs defaults,noexec
##### 4. Consider the following systemd mount unit:
``` systemd unit
[Unit]
Description=External data disk
[Mount]
What=/dev/disk/by-uuid/56C11DCC5D2E1334
Where=/mnt/external
Type=ntfs
Options=defaults
[Install]
WantedBy=multi-user.target
```
◦ What would be an equivalent /etc/fstab entry for this filesystem?
R:   UUID=56C11DCC5D2E1334 /mnt/external ntfs defaults
##### 5. What should be the file name for the unit above, so it can be used by systemd? Where should it be placed?
- R: /etc/systemd/system/mnt-external.mount

- - - 
## ***Sources:***