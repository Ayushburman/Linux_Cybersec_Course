# Linux and Cybersecurity Learning Roadmap

A complete step-by-step roadmap to learn Linux and Cybersecurity from beginner to advanced level.

---

# Table of Contents

1. Linux Learning Roadmap
2. Linux Commands
3. Cybersecurity Roadmap
4. Important Tools
5. Practice Platforms
6. Certifications
7. Recommended Projects

---

# Linux Learning Roadmap

## Beginner Level

### 1. Introduction to Linux
Learn what Linux is and how operating systems work.

### 2. Linux Distributions
Understand Linux distributions like Ubuntu, Kali, Fedora, and Arch.

### 3. Linux Installation
Install Linux using VirtualBox or dual boot.

### 4. Linux File System
Learn Linux file system structure:
- `/home`
- `/etc`
- `/bin`
- `/usr`

### 5. Basic Terminal Commands
Practice basic terminal commands like:
- `ls`
- `pwd`
- `cd`

### 6. File and Directory Operations
Learn:
- `mkdir`
- `rm`
- `cp`
- `mv`

### 7. Paths in Linux
Understand:
- Absolute paths
- Relative paths

### 8. Text Editors
Learn:
- `nano`
- `vim`

### 9. Linux Permissions
Understand:
- `chmod`
- `chown`
- `sudo`

### 10. Users and Groups
Learn user and group management commands.

---

## Intermediate Level

### 11. File Searching
Practice:
- `find`
- `locate`
- `grep`

### 12. Redirection and Pipes
Learn:
- `>`
- `>>`
- `|`

### 13. Process Management
Understand:
- `ps`
- `top`
- `kill`
- `htop`

### 14. Package Management
Learn:
- `apt`
- `yum`
- `dnf`
- `pacman`

### 15. Environment Variables
Understand shell configuration files and environment variables.

### 16. Bash Scripting Basics
Learn Bash shell scripting fundamentals.

### 17. Bash Logic Building
Practice:
- Loops
- Conditions
- Functions

### 18. Networking Commands
Learn:
- `ping`
- `ifconfig`
- `netstat`
- `ssh`

### 19. SSH Remote Access
Understand SSH and remote server access.

### 20. Linux Services
Learn:
- `systemctl`
- Linux services management

---

## Advanced Level

### 21. Cron Jobs
Understand task scheduling using cron jobs.

### 22. Disk Management
Learn:
- `df`
- `du`
- `fdisk`
- `mount`

### 23. File Compression
Practice:
- `tar`
- `zip`
- `gzip`

### 24. Log Monitoring
Learn:
- `/var/log`
- `journalctl`

### 25. Linux Kernel
Understand Linux kernel basics and boot process.

### 26. Firewall and Security
Learn:
- `ufw`
- `iptables`

### 27. Git and GitHub
Practice Git and GitHub using Linux terminal.

### 28. Docker Basics
Learn Docker and container management.

### 29. System Administration
Explore:
- Automation
- Server management
- Advanced Linux administration

### 30. Real Projects
Build real-world projects and use Linux daily.

---

# Final Goal

By following this roadmap, you will learn:
- Linux fundamentals
- Command-line mastery
- Bash scripting
- Networking
- Security
- Automation
- DevOps basics
- System administration

---

# Recommended Practice

- Use Linux daily
- Practice terminal commands regularly
- Solve Linux challenges
- Build automation scripts
- Create real-world projects

---

# Outcome

After completing this roadmap, you will be able to:
- Work confidently in Linux environments
- Manage servers
- Write Bash scripts
- Automate tasks
- Use Linux for development, cybersecurity, DevOps, and cloud computing

---

# 20 Important Linux Commands

## 1. Print Current Directory
```bash
pwd
```

## 2. List Files and Folders
```bash
ls
```

## 3. Change Directory
```bash
cd folder_name
```

## 4. Create New Directory
```bash
mkdir new_folder
```

## 5. Create Empty File
```bash
touch file.txt
```

## 6. Remove File
```bash
rm file.txt
```

## 7. Remove Directory
```bash
rmdir folder_name
```

## 8. Copy Files
```bash
cp file1.txt file2.txt
```

## 9. Move or Rename File
```bash
mv old.txt new.txt
```

## 10. Display File Content
```bash
cat file.txt
```

## 11. Edit File Using Nano
```bash
nano file.txt
```

## 12. Search Text in File
```bash
grep "word" file.txt
```

## 13. Find Files
```bash
find /home -name file.txt
```

## 14. Change File Permissions
```bash
chmod 777 file.txt
```

## 15. Change File Owner
```bash
chown user file.txt
```

## 16. Check Running Processes
```bash
ps
```

## 17. Kill a Process
```bash
kill PID
```

## 18. Check Internet Connection
```bash
ping google.com
```

## 19. Install Package
```bash
sudo apt install package_name
```

## 20. Update System
```bash
sudo apt update && sudo apt upgrade
```

---

# Bonus Commands

## Check System Information
```bash
uname -a
```

## Check Disk Usage
```bash
df -h
```

## Check Memory Usage
```bash
free -m
```

## Open Root Terminal
```bash
sudo su
```

---

# Cybersecurity Roadmap

A complete step-by-step roadmap to learn Cybersecurity from beginner to advanced level.

---

## Beginner Level

### 1. Learn Computer Basics
Understand how computers, operating systems, and networks work.

### 2. Learn Linux
Master Linux commands, terminal usage, permissions, and file systems.

### 3. Learn Networking Fundamentals
Study:
- IP addresses
- DNS
- HTTP
- TCP/IP
- Routers
- Ports

### 4. Understand Cybersecurity Basics
Learn:
- CIA Triad
- Threats
- Vulnerabilities
- Malware
- Attacks

### 5. Learn Programming Basics
Start with:
- Python
- Bash
- Basic scripting

### 6. Understand Web Technologies
Learn:
- HTML
- CSS
- JavaScript
- APIs

### 7. Learn Git and GitHub
Use version control and manage projects.

### 8. Learn Virtualization
Use:
- VirtualBox
- VMware

### 9. Build a Home Lab
Install:
- Kali Linux
- Metasploitable

### 10. Learn Basic Security Tools
Practice:
- Nmap
- Wireshark
- Burp Suite
- Netcat

---

## Intermediate Level

### 11. Learn Ethical Hacking Concepts
Understand:
- Reconnaissance
- Scanning
- Exploitation
- Reporting

### 12. Practice Information Gathering
Use:
- WHOIS
- DNS lookup
- OSINT

### 13. Learn Vulnerability Scanning
Use:
- Nessus
- OpenVAS

### 14. Learn Web Application Security
Study:
- SQL Injection
- XSS
- CSRF
- OWASP Top 10

### 15. Learn Password Security
Understand:
- Hashing
- Salting
- Brute force
- Password cracking

### 16. Learn Wireless Security
Study:
- WiFi attacks
- WPA/WPA2
- Packet capturing

### 17. Learn System Security
Understand Windows and Linux hardening.

### 18. Learn Firewalls and IDS/IPS
Study:
- Snort
- Suricata
- Firewall rules

### 19. Learn Cryptography Basics
Understand:
- Encryption
- Hashing
- RSA
- AES
- Digital signatures

### 20. Practice Capture The Flag (CTF)
Solve beginner cybersecurity challenges.

---

## Advanced Level

### 21. Learn Malware Analysis
Study:
- Trojans
- Ransomware
- Reverse engineering

### 22. Learn Reverse Engineering
Use:
- Ghidra
- IDA Free
- Debuggers

### 23. Learn Exploit Development
Understand:
- Buffer overflows
- Memory exploitation

### 24. Learn Active Directory Security
Study Windows domain attacks and privilege escalation.

### 25. Learn Cloud Security
Understand:
- AWS
- Azure
- IAM
- Cloud misconfigurations

### 26. Learn Container Security
Study Docker and Kubernetes security.

### 27. Learn Digital Forensics
Analyze:
- Logs
- Memory dumps
- Incident evidence

### 28. Learn SIEM Tools
Use:
- Splunk
- ELK Stack
- Wazuh

### 29. Learn Incident Response
Understand:
- Detection
- Containment
- Eradication
- Recovery

### 30. Learn Security Automation
Automate tasks using Python and Bash.

---

# Specialized Paths

## Red Team
- Penetration Testing
- Exploit Development
- Social Engineering
- Web Hacking

## Blue Team
- SOC Analysis
- Threat Hunting
- Incident Response
- SIEM Monitoring

## Purple Team
Combination of Red Team and Blue Team operations.

---

# Important Tools

| Tool | Purpose |
|------|----------|
| Nmap | Network Scanning |
| Wireshark | Packet Analysis |
| Burp Suite | Web Security Testing |
| Metasploit | Exploitation Framework |
| Hydra | Password Cracking |
| John the Ripper | Password Recovery |
| Aircrack-ng | Wireless Security |
| Nikto | Web Vulnerability Scanner |
| Gobuster | Directory Enumeration |
| Hashcat | Advanced Password Cracking |

---

# Best Platforms for Practice

- TryHackMe
- Hack The Box
- OverTheWire
- PortSwigger Web Security Academy
- PicoCTF

---

# Certifications

## Beginner
- CompTIA Security+
- Google Cybersecurity Certificate

## Intermediate
- CEH
- eJPT
- PNPT

## Advanced
- OSCP
- CISSP
- OSEP

---

# Best Learning Strategy

1. Learn theory
2. Build labs
3. Practice daily
4. Solve CTFs
5. Build projects
6. Document work on GitHub
7. Stay updated with cybersecurity news

---

# Recommended Projects

- Port Scanner
- Keylogger Detector
- Vulnerability Scanner
- Packet Sniffer
- Password Strength Checker
- Web Security Scanner
- Log Analyzer
- Network Monitoring Tool

---

# Final Outcome

After completing this roadmap, you will understand:
- Ethical Hacking
- Network Security
- Web Security
- Linux Security
- Malware Analysis
- Cloud Security
- Security Automation
- Incident Response

---

# Final Advice

- Practice more than watching tutorials
- Build projects consistently
- Create a cybersecurity portfolio
- Participate in bug bounty programs
- Never stop learning because cybersecurity changes daily
