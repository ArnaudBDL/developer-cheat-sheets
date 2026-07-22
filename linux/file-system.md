# Linux : File System

## Main Directories

```text
/        Root of the filesystem
/bin     Essential user commands
/boot    Boot loader and kernel files
/dev     Device files
/etc     System configuration
/home    User home directories
/lib     Essential shared libraries
/media   Removable-media mount points
/mnt     Temporary mount points
/opt     Optional application software
/proc    Process and kernel virtual filesystem
/root    Root user's home directory
/run     Runtime state
/srv     Service data
/sys     Device and kernel virtual filesystem
/tmp     Temporary files
/usr     Userland programs and shared data
/var     Variable data, logs, caches and queues
```

## Inspect Filesystems

```bash
findmnt
findmnt /
lsblk -f
df -hT
mount
cat /etc/fstab
```

## Mount and Unmount

```bash
sudo mount /dev/sdb1 /mnt/data
sudo umount /mnt/data
sudo mount -a
```

## Filesystem Usage

```bash
df -h
df -i
du -sh /var/*
du -ah /var | sort -h | tail
```
