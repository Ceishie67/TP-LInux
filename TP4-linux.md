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

