# TP4 : Real services
![Alt text](image.png)

## Partie 1 : Partitionnement du serveur de stockage

### 🌞 Partitionner le disque à l'aide de LVM

PV :
```
sudo pvcreate /dev/sdb

Physical volume "/dev/sdb" successfully created.

sudo pvcreate /dev/sdc

Physical volume "/dev/sdc" successfully created.

```
VG:
```
sudo vgcreate storage /dev/sdb

Volume group "storage" successfully created

sudo vgextend storage /dev/sdc

Volume group "storage" successfully extended
```
LV
```
sudo lvcreate -l 100%FREE storage -n lvgroupedata

Logical volume "lvgroupedata" created.
```

### 🌞 Formater la partition

```
sudo mkfs -t ext4 /dev/storage/lvgroupedata


Creating filesystem with 1046528 4k blocks and 261632 inodes
Filesystem UUID: 5e93146a-c361-4fff-b8ad-87ea5ee5d7c3
Superblock backups stored on blocks:
    32768, 98304, 163840, 229376, 294912, 819200, 884736

Allocating group tables: done
Writing inode tables: done
Creating journal (16384 blocks): done
Writing superblocks and filesystem accounting information: done
```
### 🌞 Monter la partition
```
sudo mount /dev/storage/lvgroupedata /mnt/data1
```

```
df -h

/dev/mapper/storage-lvgroupedata  3.9G   24K  3.7G   1% /mnt/data1

df -h | grep mnt

/dev/mapper/storage-lvgroupedata  3.9G   24K  3.7G   1% /mnt/data1
```