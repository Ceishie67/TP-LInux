# TP3 : Services
![Alt text](image.png)

## I. Service SSH

## 1. Analyse du service

### 🌞 S'assurer que le service sshd est démarré

```
● tp3linux
    State: degraded
    Units: 279 loaded (incl. loaded aliases)
     Jobs: 0 queued
   Failed: 1 units
    Since: Mon 2024-01-29 15:40:22 CET; 52min ago
  systemd: 252-13.el9_2
   CGroup: /
           ├─init.scope
           │ └─1 /usr/lib/systemd/systemd --switched-root --system --de>
           ├─system.slice
           │ ├─NetworkManager.service
           │ │ └─11268 /usr/sbin/NetworkManager --no-daemon
           │ ├─auditd.service
           │ │ └─641 /sbin/auditd
           │ ├─chronyd.service
           │ │ └─676 /usr/sbin/chronyd -F 2
           │ ├─crond.service
           │ │ └─695 /usr/sbin/crond -n
           │ ├─dbus-broker.service
           │ │ ├─677 /usr/bin/dbus-broker-launch --scope system --audit
           │ │ └─680 dbus-broker --log 4 --controller 9 --machine-id 8a>
           │ ├─firewalld.service
           │ │ └─669 /usr/bin/python3 -s /usr/sbin/firewalld --nofork ->
           │ ├─rsyslog.service
           │ │ └─670 /usr/sbin/rsyslogd -n
           │ ├─sshd.service
           │ │ └─688 "sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 st>
           │ ├─systemd-journald.service
           │ │ └─557 /usr/lib/systemd/systemd-journald
           │ ├─systemd-logind.service
           │ │ └─673 /usr/lib/systemd/systemd-logind
           │ └─systemd-udevd.service
lines 1-33
```

### 🌞 Analyser les processus liés au service SSH

```
root         688       1  0 15:40 ?        00:00:00 sshd: /usr/sbin/ssh -D [listener] 0 of 10-100 startups
root       11324     688  0 16:31 ?        00:00:00 sshd: nath [priv]
nath       11328   11324  0 16:31 ?        00:00:00 sshd: nath@pts/0
nath       11367   11329  0 16:39 pts/0    00:00:00 grep --color=auto sshd
```
### 🌞 Déterminer le port sur lequel écoute le service SSH

```
State   Recv-Q  Send-Q   Local Address:Port   Peer Address:Port Process
LISTEN  0       128            0.0.0.0:22          0.0.0.0:*
LISTEN  0       128               [::]:22             [::]:*
```

### 🌞 Consulter les logs du service SSH

````
 journalctl -xe -u sshd

 Jan 30 14:17:55 tp3linux sshd[1307]: main: sshd: ssh-rsa algorithm is disabled
Jan 30 14:17:58 tp3linux sshd[1307]: Accepted password for nath from 10.1.1.1 port 62232 ssh2
Jan 30 14:17:58 tp3linux sshd[1307]: pam_unix(sshd:session): session opened for user nath(uid=1000) by (uid=0)
```
