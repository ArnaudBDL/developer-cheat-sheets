# Linux : Storage

## Inspect Devices

```bash
lsblk
lsblk -f
blkid
findmnt
df -hT
du -sh /path
```

## Partition Tables

```bash
sudo fdisk -l
sudo parted -l
sudo fdisk /dev/sdX
sudo parted /dev/sdX
```

Partitioning and formatting commands can destroy data. Verify the target device before execution.

## Create a Filesystem

```bash
sudo mkfs.ext4 /dev/sdX1
sudo mkfs.xfs /dev/sdX1
sudo mkswap /dev/sdX2
sudo swapon /dev/sdX2
```

## Mount Persistently

```bash
sudo blkid /dev/sdX1
sudo mkdir -p /mnt/data
sudo mount /dev/sdX1 /mnt/data
sudoedit /etc/fstab
sudo mount -a
findmnt /mnt/data
```

## LVM Inspection

```bash
sudo pvs
sudo vgs
sudo lvs
sudo lvdisplay
```

## Disk Health

```bash
sudo smartctl -a /dev/sdX
sudo dmesg --level=err,warn | grep -iE 'disk|ata|nvme|I/O'
```
