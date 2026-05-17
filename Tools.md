# 🛡️ Kali Linux / Linux / Networking / Cybersecurity Tools

> ⚠️ **Legal Disclaimer:** For authorized testing only. All tools must be used with **explicit written permission**. Unauthorized use is illegal under computer misuse laws.

---

## 📊 Stats

| Tools Covered | Categories | Skill Levels |
|:---:|:---:|:---:|
| 80+ | 15 | 3 |

---

## 📋 Table of Contents

1. [Recon & Info Gathering](#1--recon--info-gathering)
2. [Network Scanning & Enumeration](#2--network-scanning--enumeration)
3. [Vulnerability Assessment](#3--vulnerability-assessment)
4. [Web Application Security](#4--web-application-security)
5. [Wireless / Wi-Fi Security](#5--wireless--wi-fi-security)
6. [Password Attacks](#6--password-attacks)
7. [Exploitation Frameworks](#7--exploitation-frameworks)
8. [Sniffing & Packet Analysis](#8--sniffing--packet-analysis)
9. [Digital Forensics](#9--digital-forensics)
10. [Reverse Engineering](#10--reverse-engineering)
11. [System Monitoring & Admin](#11--system-monitoring--admin)
12. [Networking Tools](#12--networking-tools)
13. [Malware Analysis](#13--malware-analysis)
14. [Containers / Cloud / DevSecOps](#14--containers--cloud--devsecops)
15. [Programming & Scripting](#15--programming--scripting)
16. [Command Snapshots](#-command-snapshots)
17. [Learning Roadmap](#-learning-roadmap)

---

## 1. 🔍 Recon & Info Gathering

> **Phase 1 — Passive & Active** | Tags: `domains` `IPs` `emails` `DNS`

| Tool | Purpose |
|------|---------|
| **Nmap** | Network mapper — port scan + OS/service detection |
| **theHarvester** | Email, subdomain, IP OSINT from public sources |
| **Recon-ng** | Modular OSINT framework |
| **Maltego** | Visual link analysis for entity relationships |
| **Amass** | In-depth DNS enumeration and subdomain discovery |
| **Sublist3r** | Fast subdomain enumeration via search engines |
| **Shodan** | Search engine for internet-connected devices |
| **SpiderFoot** | Automated OSINT across 200+ data sources |
| **DNSRecon** | DNS record enumeration and zone transfers |
| **Whois** | Domain registration details |
| **Netdiscover** | ARP-based host discovery on local networks |

---

## 2. 📡 Network Scanning & Enumeration

> **Port / Service / Vuln Discovery** | Tags: `port scan` `services` `SMB` `SNMP`

| Tool | Purpose |
|------|---------|
| **Nmap** | Comprehensive port + service scanner |
| **Masscan** | Extremely fast internet-scale port scanner |
| **RustScan** | Fast Rust-based scanner, pipes to Nmap |
| **Unicornscan** | Async stateless TCP/UDP scanner |
| **Netcat** | TCP/UDP Swiss army knife |
| **Enum4linux** | SMB/Windows enumeration |
| **SNMPwalk** | Query SNMP devices for information |
| **SMBclient** | Access SMB shares interactively |
| **rpcclient** | Windows RPC enumeration |

---

## 3. 🛡️ Vulnerability Assessment

> **CVE / Weakness Detection** | Tags: `CVEs` `auditing` `web` `WordPress`

| Tool | Purpose |
|------|---------|
| **OpenVAS** | Open-source vulnerability scanner (Greenbone) |
| **Nessus** | Industry-standard vulnerability assessment |
| **Nikto** | Web server vulnerability scanner |
| **Lynis** | Linux system security auditing |
| **WPScan** | WordPress-specific vulnerability scanner |
| **Nuclei** | Template-based fast vulnerability scanner |
| **Retire.js** | Detect outdated JavaScript libraries |

---

## 4. 🌐 Web Application Security

> **SQLi / XSS / Fuzzing** | Tags: `SQLi` `XSS` `brute force` `proxy`

| Tool | Purpose |
|------|---------|
| **Burp Suite** | Full web app security testing proxy |
| **OWASP ZAP** | Free web application scanner |
| **sqlmap** | Automated SQL injection detection/exploitation |
| **Gobuster** | Directory/file brute-forcing |
| **Dirb** | Web content scanner |
| **ffuf** | Fast web fuzzer (params, dirs, virtual hosts) |
| **Wfuzz** | Advanced web fuzzer |
| **XSStrike** | Advanced XSS detection suite |
| **Commix** | Command injection exploiter |
| **Hydra** | Online brute force (web forms, SSH, FTP, etc.) |

---

## 5. 📶 Wireless / Wi-Fi Security

> **WPA/WPA2 Auditing** | Tags: `WPA crack` `capture` `MITM`

| Tool | Purpose |
|------|---------|
| **Aircrack-ng** | WPA/WEP cracking suite |
| **Kismet** | Wireless network detector and sniffer |
| **Reaver** | WPS PIN brute-force attack |
| **Wifite** | Automated Wi-Fi auditing |
| **hcxdumptool** | Capture PMKID and EAPOL packets |
| **Bettercap** | Advanced MITM and Wi-Fi attack framework |

---

## 6. 🔓 Password Attacks

> **Hash Cracking / Brute Force** | Tags: `hash cracking` `wordlists` `GPU`

| Tool | Purpose |
|------|---------|
| **John the Ripper** | CPU-based hash cracker |
| **Hashcat** | GPU-accelerated hash cracking |
| **Hydra** | Online brute force over many protocols |
| **Medusa** | Parallel brute force login tool |
| **CeWL** | Custom wordlist generator from websites |
| **Crunch** | Wordlist generator with patterns |

---

## 7. 💥 Exploitation Frameworks

> **Payload / Post-Exploitation** | Tags: `exploit` `payload` `C2` `persistence`

| Tool | Purpose |
|------|---------|
| **Metasploit Framework** | The most widely used exploitation framework |
| **BeEF** | Browser Exploitation Framework |
| **SearchSploit** | Offline Exploit-DB search |
| **Empire** | PowerShell/Python post-exploitation C2 |
| **RouterSploit** | Router and embedded device exploitation |

---

## 8. 🦈 Sniffing & Packet Analysis

> **Protocol / Traffic Inspection** | Tags: `capture` `MITM` `protocol`

| Tool | Purpose |
|------|---------|
| **Wireshark** | GUI packet capture and protocol analyzer |
| **tcpdump** | CLI packet sniffer and filter |
| **Ettercap** | ARP poisoning and MITM suite |
| **dsniff** | Network credential sniffer |
| **TShark** | CLI version of Wireshark |

---

## 9. 🔬 Digital Forensics

> **Disk / Memory / Evidence** | Tags: `disk` `memory` `recovery`

| Tool | Purpose |
|------|---------|
| **Autopsy** | GUI-based digital forensics platform |
| **Volatility** | Memory forensics framework |
| **Foremost** | File carving from raw disk images |
| **Binwalk** | Firmware analysis and extraction |
| **Sleuth Kit** | Command-line forensic tools (fls, icat, etc.) |

---

## 10. ⚙️ Reverse Engineering

> **Binary / Malware / Assembly** | Tags: `disassembly` `decompile` `malware`

| Tool | Purpose |
|------|---------|
| **Ghidra** | NSA-developed reverse engineering suite |
| **radare2** | CLI framework for binary analysis |
| **IDA Free** | Industry-standard disassembler (free version) |
| **strings** | Extract printable strings from binaries |
| **objdump** | Disassemble ELF binaries |

---

## 11. 📊 System Monitoring & Admin

> **Linux Ops / Process Tracking** | Tags: `processes` `I/O` `sockets`

| Tool | Purpose |
|------|---------|
| **htop** | Interactive process viewer |
| **top** | Built-in process monitor |
| **iftop** | Real-time network bandwidth monitor |
| **iotop** | Disk I/O monitor per process |
| **journalctl** | Query systemd journal logs |
| **systemctl** | Manage systemd services |
| **netstat** | Network connections and routing |
| **ss** | Modern socket statistics tool |
| **lsof** | List open files and sockets |

---

## 12. 🔗 Networking Tools

> **Routing / DNS / Connectivity** | Tags: `ping` `routing` `DNS` `ARP`

| Tool | Purpose |
|------|---------|
| **ping** | ICMP host reachability test |
| **traceroute** | Trace packet route to destination |
| **dig** | DNS query tool |
| **nslookup** | DNS lookup utility |
| **iperf** | Network bandwidth measurement |
| **arp** | ARP table management |
| **ifconfig** | Network interface configuration (legacy) |
| **ip** | Modern network interface tool |
| **route** | Routing table management |
| **mtr** | Combined ping + traceroute |

---

## 13. 🦠 Malware Analysis

> **Static & Dynamic Analysis** | Tags: `YARA rules` `sandbox` `PE`

| Tool | Purpose |
|------|---------|
| **YARA** | Pattern matching for malware classification |
| **Cuckoo Sandbox** | Automated dynamic malware analysis |
| **PEStudio** | Static PE file analysis (Windows) |
| **REMnux** | Linux distro for reverse-engineering malware |

---

## 14. ☁️ Containers / Cloud / DevSecOps

> **K8s Security / Image Scanning** | Tags: `Docker` `Kubernetes` `scanning`

| Tool | Purpose |
|------|---------|
| **Docker** | Container platform |
| **Kubernetes** | Container orchestration |
| **Trivy** | Container and filesystem vulnerability scanner |
| **kube-bench** | CIS Kubernetes benchmark checker |
| **Falco** | Runtime security monitoring for containers |

---

## 15. 💻 Programming & Scripting

| Language | Use in Security |
|----------|----------------|
| **Python** | Exploit scripts, automation, tool development |
| **Bash** | System automation, one-liners, recon scripts |
| **Perl** | Legacy exploit code, text processing |
| **PowerShell** | Windows post-exploitation, Active Directory |
| **Git** | Version control, exploit/tool repositories |

---

## 💻 Command Snapshots

### Nmap — Full Port Scan

```bash
root@kali:~$ nmap -sV -sC -O -p- 192.168.1.1

Starting Nmap 7.94 ( https://nmap.org )
PORT     STATE  SERVICE   VERSION
22/tcp   open   ssh       OpenSSH 8.2p1 Ubuntu
80/tcp   open   http      Apache httpd 2.4.41
443/tcp  open   https     nginx 1.18.0
3306/tcp open   mysql     MySQL 5.7.33

OS Details: Linux 4.15 - 5.6
Nmap done: 1 IP scanned in 23.4 seconds
```

### theHarvester — Email & Subdomain Enumeration

```bash
root@kali:~$ theHarvester -d target.com -b all

Emails found:
  admin@target.com
  john.doe@target.com
  support@target.com

Hosts found:
  mail.target.com - 104.21.3.x
  dev.target.com  - 172.67.1.x

Shodan results: 3 hosts exposed
```

### sqlmap — Automated SQL Injection

```bash
root@kali:~$ sqlmap -u "http://site.com/id=1" --dbs

[*] testing connection to target URL
[+] parameter 'id' is vulnerable!
    Type: UNION-based (4 columns)

Available databases [3]:
  [*] information_schema
  [*] users_db
  [*] admin_panel

[*] Fetched data logged to /root/.sqlmap
```

### Gobuster — Directory Brute-Forcing

```bash
root@kali:~$ gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt

===============================================================
/admin         (Status: 301)
/backup        (Status: 200)
/config.php    (Status: 200)
/login         (Status: 200)
/uploads       (Status: 403)
===============================================================
Progress: 4614/4614 (100%)
```

### Hashcat — GPU-Accelerated Hash Cracking

```bash
root@kali:~$ hashcat -m 0 hashes.txt rockyou.txt

hashcat (v6.2.6) starting...
Device #1: RTX 3080 - 10240MB
Speed: 12500 MH/s

5f4dcc3b5aa765d61d83...:password123
d8578edf8458ce06fbc5...:qwerty
482c811da5d5b4bc6d49...:[ NOT FOUND ]

Recovered: 2/3 (66.67%) Digests
```

### Metasploit — Exploit Framework & Payload Handler

```bash
root@kali:~$ msfconsole

msf6 > use exploit/multi/handler
msf6 exploit(handler) > set PAYLOAD linux/x86/meterpreter/reverse_tcp
msf6 exploit(handler) > set LHOST 10.0.0.1
msf6 exploit(handler) > run

[*] Started reverse TCP handler
[*] Meterpreter session 1 opened!
meterpreter > sysinfo
```

### Aircrack-ng — WPA2 Handshake Dictionary Attack

```bash
root@kali:~$ aircrack-ng -b AA:BB:CC:DD:EE:FF -w rockyou.txt cap.pcap

Opening cap.pcap
Read 142358 packets.

   #  BSSID              ESSID          Enc
   1  AA:BB:CC:DD:EE:FF  HomeNetwork   WPA2

[00:02:34] 148291 keys tested (1523.91 k/s)
KEY FOUND! [ mypassword2023 ]
```

### Volatility — Memory Forensics & Malware Detection

```bash
root@kali:~$ volatility -f mem.raw imageinfo
Volatility Foundation v2.6
Suggested Profile(s): Win10x64

root@kali:~$ volatility -f mem.raw --profile=Win10x64 pstree
 0xffff  4     System
 . 0xffff  544   smss.exe
 . 0xffff  3440  malware.exe
     → suspicious parent: explorer.exe
```

### Wireshark — Live Packet Capture & HTTP Inspection

```bash
root@kali:~$ wireshark -i eth0 -k

Capturing on eth0...
Frame 1:  TCP 192.168.1.5 → 10.0.0.1 [SYN]
Frame 2:  HTTP GET /admin/login HTTP/1.1
Frame 3:  POST /login pass=admin123
Frame 4:  HTTP 302 → /dashboard
Frame 5:  Set-Cookie: session=abc123...

[Filter: http.request.method == POST]
```

### Nikto — Web Server Vulnerability Scanner

```bash
root@kali:~$ nikto -h http://target.com

- Nikto v2.1.6
+ Server: Apache/2.4.41
+ /admin/: Directory indexing enabled
+ /phpMyAdmin/: phpMyAdmin detected
+ X-Frame-Options header missing
+ CVE-2017-12617: Apache RCE possible

7 items found, 3 critical
```

### tcpdump — CLI Packet Capture with Filters

```bash
root@kali:~$ tcpdump -i eth0 -n 'port 80' -A

listening on eth0, link-type EN10MB
13:22:01 IP 192.168.1.5.52341 > 10.0.0.1.80
GET / HTTP/1.1
Host: example.com
Cookie: auth=bearer_abc123
User-Agent: Mozilla/5.0...
3 packets captured, 3 received
```

### Hydra — Online Brute Force over SSH

```bash
root@kali:~$ hydra -l admin -P rockyou.txt ssh://192.168.1.1

Hydra v9.4 starting...
[DATA] 16 tasks, 1 server, 14344392 tries
[DATA] attacking ssh://192.168.1.1:22/

[22][ssh] host: 192.168.1.1
      login: admin
      password: letmein
1 of 1 target successfully completed
```

---

## 🗺️ Learning Roadmap

### 🟢 Beginner Path — START HERE

> Master these before anything else. Focus on fundamentals: networking concepts, Linux CLI, and basic scanning.

| # | Tool | Why |
|---|------|-----|
| 01 | **Linux Terminal** | Foundation of everything |
| 02 | **Nmap** | Port & service discovery |
| 03 | **Wireshark** | Understand traffic |
| 04 | **Burp Suite** | Web proxy interception |
| 05 | **Hydra** | Brute force basics |
| 06 | **Gobuster** | Dir & file enumeration |
| 07 | **Netcat** | Swiss army TCP tool |
| 08 | **Metasploit** | Exploitation basics |

---

### 🔵 Intermediate Path — LEVEL UP

> Deepen skills in web attacks, wireless auditing, and password cracking. Start CTF competitions (HackTheBox, TryHackMe).

| # | Tool | Why |
|---|------|-----|
| 01 | **sqlmap** | Automated SQL injection |
| 02 | **Aircrack-ng** | Wi-Fi security auditing |
| 03 | **John the Ripper** | Offline hash cracking |
| 04 | **Hashcat** | GPU-accelerated cracking |
| 05 | **OWASP ZAP** | Web app scanner |
| 06 | **Bettercap** | Network MITM attacks |
| 07 | **tcpdump** | CLI packet analysis |

---

### 🟣 Advanced Path — SPECIALIST

> Specialise in reverse engineering, forensics, or cloud security. Write custom exploits. Contribute to bug bounties.

| # | Tool | Why |
|---|------|-----|
| 01 | **Ghidra** | Binary reverse engineering |
| 02 | **Volatility** | Memory forensics |
| 03 | **Empire** | Post-exploitation C2 |
| 04 | **Cuckoo Sandbox** | Malware sandboxing |
| 05 | **Kubernetes Security** | Cloud attack surface |
| 06 | **Malware Analysis** | YARA + PEStudio + REMnux |

---

## ⚖️ Ethics & Legal

- Always obtain **written authorization** before testing any system
- Stay within the agreed **scope** — never touch out-of-scope assets
- **Report findings responsibly** via coordinated disclosure
- Practice only in **legal environments**: your own lab, VulnHub VMs, HackTheBox, TryHackMe
- Know your local laws: UK Computer Misuse Act · US CFAA · India IT Act 2000

---

*For ethical use only · Always get written authorization before testing · Unauthorized access is a criminal offence*
