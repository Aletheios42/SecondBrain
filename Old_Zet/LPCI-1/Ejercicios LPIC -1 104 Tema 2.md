**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. Using du, how can we check how much space is being used by just the files on the current directory?
- R:  du -S -h -d 0
##### 2. Using df, list information for every ext4 filesystem, with the outputs including the following fields, in order: device, mount point, total number of inodes, number of available inodes, percentage of free space.
- R:  df -t ext4 --output=source,target,itotal,iavail,pcent
##### 3. What is the command to run e2fsck on /dev/sdc1 in non-interactive mode, while trying to automatically fix most errors?
- R:  e2fsck -p /dev/sdc1
##### 4. Suppose /dev/sdb1 is an ext2 filesystem. How can you convert it to ext3, and at the same time reset its mount count and change its label to UserData?
- R:  tune2fs -j -C 0 -L UserData /dev/sdb1
##### 5. How can you check for errors on an XFS filesystem, without repairing any damage found?
- R: xfs -n DEVICE
# Explorational Exercises
##### 1. Consider you have an ext4 filesystem on /dev/sda1 with the following parameters, obtained with tune2fs:
``` bash
Mount count:
 8
Maximum mount count:
 -1
 ```
What will happen at the next boot if the command tune2fs -c 9 /dev/sda1 is issued?
- R: The command will set the maximum mount count for the filesystem to 9. Since the mount count is currently 8, the next system boot will cause a filesystem check.
##### 2. Consider the following output of du -h:
``` bash
$ du -h
216K ./somedir/anotherdir
224K ./somedir
232K .
 ```
 How much space is occupied by just the files on the current directory? How could we rewrite the command to show this information more clearly?
- R: du -hS
##### 3. What would happen to the ext2 filesystem /dev/sdb1 if the command below is issued?
``` bash
# tune2fs -j /dev/sdb1 -J device=/dev/sdc1 -i 30d
```
- R: A journal will be added to /dev/sdb1, converting it to ext3. The journal will be stored on the device /dev/sdc1 and the filesystem will be checked every 30 days. 
##### 4. How can we check for errors on a XFS filesystem on /dev/sda1 that has a log section on /dev/sdc1, without actually making any repairs?
- R:  xfs_repair -l /dev/sdc1 -n
##### 5. What is the difference between the -T and -t parameters for df?
- R: -T enseña todo y-t "type" filtra los de tipo "type"

- - - 
## ***Sources:***