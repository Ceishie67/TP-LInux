# TP5 : We do a little scripting
![Alt text](image.png)

## Partie 1 : Script carte d'identité

[nath@localhost idcard]$ /srv/idcard/idcard.sh
Machine name: Static
OS Rocky Linux 9.2 (Blue Onyx) and kernel version is 5.14.0-284.11.1.el9_2.x86_64
IP: 1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:ca:48:a1 brd ff:ff:ff:ff:ff:ff
    inet 10.5.2.10/24 brd 10.5.2.255 scope global noprefixroute enp0s3
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:feca:48a1/64 scope link 
       valid_lft forever preferred_lft forever
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:08:b9:b6 brd ff:ff:ff:ff:ff:ff
    inet 10.0.3.15/24 brd 10.0.3.255 scope global dynamic noprefixroute enp0s8
       valid_lft 76763sec preferred_lft 76763sec
    inet6 fe80::a00:27ff:fe08:b9b6/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
RAM :               total        used        free      shared  buff/cache   available
Mem:           1.7Gi       508Mi       991Mi       4.0Mi       428Mi       1.2Gi
Swap:          2.0Gi          0B       2.0Gi memory available on 1.7Gi  total memory
Disk :Filesystem           Size  Used Avail Use% Mounted on
devtmpfs             4.0M     0  4.0M   0% /dev
tmpfs                890M     0  890M   0% /dev/shm
tmpfs                356M  5.0M  351M   2% /run
/dev/mapper/rl-root   17G  1.5G   16G   9% /
/dev/sda1           1014M  220M  795M  22% /boot
tmpfs                178M     0  178M   0% /run/user/1000 space left
Top 5 processes by RAM usage :
 - python3
 - NetworkManager
 - systemd
 -     PID TTY          TIME CMD
  12010 pts/1    00:00:00 bash
  28094 pts/1    00:00:00 idcard.sh
  28119 pts/1    00:00:00 ps
Listening ports :
 - 22 tcp : sshd
 - State  Recv-Q Send-Q Local Address:Port  Peer Address:PortProcess                          
LISTEN 0      128          0.0.0.0:22         0.0.0.0:*                                    
LISTEN 0      511        127.0.0.1:42223      0.0.0.0:*    users:(("node",pid=11894,fd=19))
LISTEN 0      128             [::]:22            [::]:*                                    
PATH directories :
  - /usr/local/bin
 - /srv/idcard
