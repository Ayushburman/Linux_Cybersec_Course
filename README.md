<div align="center"> 
<pre>
 __     ______   __  __  __  __   __   __     
/\ \   /\__  _\ /\ \/\ \/\ \/\ \ /\ \ /\ \    
\ \ \  \/_/\ \/ \ \ `\\ \ \ \ \ \\ `\`\/'/'   
 \ \ \  __\ \ \  \ \ , ` \ \ \ \ \`\/ > <     
  \ \ \L\ \\_\ \__\ \ \`\ \ \ \_\ \  \/'/\`\  
   \ \____//\_____\\ \_\ \_\ \_____\ /\_\\ \_\
    \/___/ \/_____/ \/_/\/_/\/_____/ \/_/ \/_/
</pre>

```bash
> CYBERSECURITY  ·  LINUX  ·  HACKING  ·  DEFENSE  ·  MASTERY
```

[![Roadmap](https://img.shields.io/badge/ROADMAP-Beginner_→_Advanced-orange?style=for-the-badge&logo=roadmap.sh)](https://roadmap.sh)
[![Linux](https://img.shields.io/badge/Linux-Mastery-yellow?style=for-the-badge&logo=linux&logoColor=black)](https://linux.org)
[![Cybersecurity](https://img.shields.io/badge/CyberSec-RedTeam_%7C_BlueTeam-red?style=for-the-badge&logo=hackthebox&logoColor=white)](https://hackthebox.com)
[![CTF](https://img.shields.io/badge/CTF-Practice_Daily-green?style=for-the-badge&logo=tryhackme&logoColor=white)](https://tryhackme.com)

</div>

---

## `$ cat table_of_contents.txt`

```bash
> [1]  Linux Learning Roadmap        →  Beginner → Intermediate → Advanced
> [2]  Linux Commands                →  20 Core + Bonus Commands
> [3]  Cybersecurity Roadmap         →  Beginner → Intermediate → Advanced
> [4]  Important Tools               →  Industry-Standard Arsenal
> [5]  Practice Platforms            →  Where to Sharpen Skills
> [6]  Certifications                →  Career Credentials
> [7]  Recommended Projects          →  Build. Break. Learn.
```

---

<div align="center">

```

           L I N U X   R O A D M A P              

```

</div>

## `🐧 PHASE 1 — Beginner Level`

```bash
> STEP 01  →  Introduction to Linux
             How operating systems work, what Linux is
             
> STEP 02  →  Linux Distributions
             Ubuntu · Kali · Fedora · Arch

> STEP 03  →  Linux Installation
             VirtualBox · Dual Boot setup

> STEP 04  →  Linux File System
             /home  /etc  /bin  /usr

> STEP 05  →  Basic Terminal Commands
             ls  ·  pwd  ·  cd

> STEP 06  →  File & Directory Operations
             mkdir  ·  rm  ·  cp  ·  mv

> STEP 07  →  Paths in Linux
             Absolute Paths  ·  Relative Paths

> STEP 08  →  Text Editors
             nano  ·  vim

> STEP 09  →  Linux Permissions
             chmod  ·  chown  ·  sudo

> STEP 10  →  Users and Groups
             User management commands & group control
```

---

## `⚙️ PHASE 2 — Intermediate Level`

```bash
> STEP 11  →  File Searching
             find  ·  locate  ·  grep

> STEP 12  →  Redirection and Pipes
             >  ·  >>  ·  |

> STEP 13  →  Process Management
             ps  ·  top  ·  kill  ·  htop

> STEP 14  →  Package Management
             apt  ·  yum  ·  dnf  ·  pacman

> STEP 15  →  Environment Variables
             Shell config files & environment control

> STEP 16  →  Bash Scripting Basics
             Shell scripting fundamentals

> STEP 17  →  Bash Logic Building
             Loops  ·  Conditions  ·  Functions

> STEP 18  →  Networking Commands
             ping  ·  ifconfig  ·  netstat  ·  ssh

> STEP 19  →  SSH Remote Access
             Secure Shell & remote server access

> STEP 20  →  Linux Services
             systemctl  ·  service management
```

---

## `🔥 PHASE 3 — Advanced Level`

```bash
> STEP 21  →  Cron Jobs           — Automate with task scheduling
> STEP 22  →  Disk Management     — df · du · fdisk · mount
> STEP 23  →  File Compression    — tar · zip · gzip
> STEP 24  →  Log Monitoring      — /var/log · journalctl
> STEP 25  →  Linux Kernel        — Kernel basics & boot process
> STEP 26  →  Firewall & Security — ufw · iptables
> STEP 27  →  Git and GitHub      — Version control via terminal
> STEP 28  →  Docker Basics       — Container management
> STEP 29  →  System Administration — Automation · Server mgmt
> STEP 30  →  Real Projects       — Build. Deploy. Master.
```

---

<div align="center">

```
╔══════════════════════════════════════════════════╗
║       20 CORE LINUX COMMANDS  [ CHEATSHEET ]     ║
╚══════════════════════════════════════════════════╝
```

</div>

```bash
# ── NAVIGATION ──────────────────────────────────────────
> pwd                          # print current directory
> ls -la                       # list all files (detailed)
> cd folder_name               # change directory

# ── FILE OPERATIONS ─────────────────────────────────────
> touch file.txt               # create empty file
> mkdir new_folder             # create directory
> cp file1.txt file2.txt       # copy file
> mv old.txt new.txt           # move / rename
> rm file.txt                  # remove file
> rmdir folder_name            # remove directory
> cat file.txt                 # display file content

# ── SEARCH & EDIT ────────────────────────────────────────
> nano file.txt                # edit with nano
> grep "word" file.txt         # search text in file
> find /home -name file.txt    # find files by name

# ── PERMISSIONS ──────────────────────────────────────────
> chmod 777 file.txt           # change file permissions
> chown user file.txt          # change file owner

# ── PROCESS & NETWORK ────────────────────────────────────
> ps                           # check running processes
> kill PID                     # terminate a process
> ping google.com              # check internet connection

# ── PACKAGE MANAGEMENT ───────────────────────────────────
> sudo apt install pkg_name    # install a package
> sudo apt update && sudo apt upgrade   # update system

# ── BONUS ────────────────────────────────────────────────
> uname -a                     # system information
> df -h                        # disk usage (human readable)
> free -m                      # memory usage in MB
> sudo su                      # open root terminal
```

---

<div align="center">

```
╔══════════════════════════════════════════════════╗
║      C Y B E R S E C U R I T Y   R O A D M A P  ║
╚══════════════════════════════════════════════════╝
```

</div>

## `🛡️ PHASE 1 — Foundation`

```bash
> STEP 01  →  Computer Basics
             OS internals · Networks · How the web works

> STEP 02  →  Learn Linux First
             Terminal · Permissions · File Systems · Scripting

> STEP 03  →  Networking Fundamentals
             IP · DNS · HTTP · TCP/IP · Routers · Ports

> STEP 04  →  Cybersecurity Basics
             CIA Triad · Threats · Vulnerabilities · Malware

> STEP 05  →  Programming Basics
             Python · Bash · Basic scripting

> STEP 06  →  Web Technologies
             HTML · CSS · JavaScript · REST APIs

> STEP 07  →  Git & GitHub
             Version control · Project management

> STEP 08  →  Virtualization
             VirtualBox · VMware

> STEP 09  →  Build a Home Lab
             Kali Linux · Metasploitable · Isolated network

> STEP 10  →  Basic Security Tools
             Nmap · Wireshark · Burp Suite · Netcat
```

---

## `⚔️ PHASE 2 — Offensive & Defensive`

```bash
> STEP 11  →  Ethical Hacking Concepts
             Reconnaissance → Scanning → Exploitation → Report

> STEP 12  →  Information Gathering
             WHOIS · DNS Lookup · OSINT techniques

> STEP 13  →  Vulnerability Scanning
             Nessus · OpenVAS

> STEP 14  →  Web Application Security
             SQL Injection · XSS · CSRF · OWASP Top 10

> STEP 15  →  Password Security
             Hashing · Salting · Brute Force · Cracking

> STEP 16  →  Wireless Security
             WiFi Attacks · WPA/WPA2 · Packet Capturing

> STEP 17  →  System Hardening
             Windows & Linux hardening techniques

> STEP 18  →  Firewalls & IDS/IPS
             Snort · Suricata · Firewall rule management

> STEP 19  →  Cryptography Basics
             Encryption · RSA · AES · Digital Signatures

> STEP 20  →  Capture The Flag (CTF)
             Solve beginner cybersecurity challenges daily
```

---

## `💀 PHASE 3 — Elite Level`

```bash
> STEP 21  →  Malware Analysis       — Trojans · Ransomware · RE
> STEP 22  →  Reverse Engineering    — Ghidra · IDA Free · Debuggers
> STEP 23  →  Exploit Development    — Buffer Overflows · Memory Exploits
> STEP 24  →  Active Directory       — Domain attacks · Privilege escalation
> STEP 25  →  Cloud Security         — AWS · Azure · IAM · Misconfigs
> STEP 26  →  Container Security     — Docker · Kubernetes hardening
> STEP 27  →  Digital Forensics      — Logs · Memory dumps · Evidence
> STEP 28  →  SIEM Tools             — Splunk · ELK Stack · Wazuh
> STEP 29  →  Incident Response      — Detect · Contain · Eradicate · Recover
> STEP 30  →  Security Automation    — Python + Bash powered pipelines
```

---

<div align="center">

```
╔══════════════════════════════════════════════════╗
║         CHOOSE  YOUR  PATH                       ║
╠════════════════╦═════════════════════════════════╣
║   🔴 RED TEAM  ║   🔵 BLUE TEAM                  ║
╠════════════════╬═════════════════════════════════╣
║  Pentest       ║  SOC Analysis                   ║
║  Exploitation  ║  Threat Hunting                 ║
║  Social Eng.   ║  Incident Response              ║
║  Web Hacking   ║  SIEM Monitoring                ║
╠════════════════╩═════════════════════════════════╣
║           🟣 PURPLE TEAM = RED + BLUE            ║
╚══════════════════════════════════════════════════╝
```

</div>

---

## `🧰 Arsenal — Important Tools`

```bash
> nmap          →  Network Scanning & Host Discovery
> wireshark     →  Deep Packet Analysis
> burpsuite     →  Web Application Security Testing
> metasploit    →  Exploitation Framework
> hydra         →  Password Cracking via Brute Force
> john          →  John the Ripper — Password Recovery
> aircrack-ng   →  Wireless Network Security Testing
> nikto         →  Web Vulnerability Scanner
> gobuster      →  Directory & Subdomain Enumeration
> hashcat       →  Advanced GPU-Powered Password Cracking
```

---

## `🏁 Practice Platforms`

```md
- [TryHackMe](https://tryhackme.com)                     — Guided learning paths, rooms, CTFs
- [Hack The Box](https://hackthebox.com)                  — Real-world machine hacking challenges
- [OverTheWire](https://overthewire.org)                  — Wargames for command-line mastery
- [PortSwigger Web Academy](https://portswigger.net/web-security) — Best web security labs
- [PicoCTF](https://picoctf.org)                          — Beginner-friendly CTF competition
```

---

## `🏆 Certifications`

```bash
# ── BEGINNER ────────────────────────────────────────────
> CompTIA Security+             # Industry-recognized baseline
> Google Cybersecurity Cert     # Great for starters

# ── INTERMEDIATE ────────────────────────────────────────
> CEH                           # Certified Ethical Hacker
> eJPT                          # eLearnSecurity Junior Pentest
> PNPT                          # Practical Network Pentest

# ── ADVANCED ────────────────────────────────────────────
> OSCP                          # Gold standard in pentesting
> OSEP                          # Advanced evasion & exploitation
> CISSP                         # Senior security professional
```

---

## `🚀 Recommended Projects to Build`

```md
- [Port Scanner]              — Python/Bash network scanner from scratch
- [Keylogger Detector]        — Monitor suspicious keystroke processes
- [Vulnerability Scanner]     — Auto-detect common CVEs in a network
- [Packet Sniffer]            — Capture and analyze raw network traffic
- [Password Strength Checker] — Entropy-based password analysis tool
- [Web Security Scanner]      — Crawl and detect OWASP vulnerabilities
- [Log Analyzer]              — Parse system logs for anomaly detection
- [Network Monitor]           — Real-time traffic visualization tool
```

---

## `📋 Best Learning Strategy`

```bash
> Step 1  →  Learn theory first — understand before you hack
> Step 2  →  Build labs        — VirtualBox, Kali, Metasploitable
> Step 3  →  Practice daily    — even 1 hour compounds fast
> Step 4  →  Solve CTFs        — TryHackMe, PicoCTF, HTB
> Step 5  →  Build projects    — GitHub portfolio = your resume
> Step 6  →  Document work     — write writeups, notes, READMEs
> Step 7  →  Stay updated      — cybersec changes every single day
```

---

<div align="center">

```
╔══════════════════════════════════════════════════════════╗
║                  FINAL OUTCOME                           ║
╠══════════════════════════════════════════════════════════╣
║                                                          ║
║   ✦  Ethical Hacking      ✦  Network Security           ║
║   ✦  Web Security         ✦  Linux Security             ║
║   ✦  Malware Analysis     ✦  Cloud Security             ║
║   ✦  Security Automation  ✦  Incident Response          ║
║                                                          ║
╚══════════════════════════════════════════════════════════╝
```

```bash
> "Practice more than you watch. Build more than you read."
> "The terminal is your weapon. Learn to wield it."
> "Never stop — because cybersecurity never stops evolving."
```

---

*crafted for those who break things to understand them*

</div>
