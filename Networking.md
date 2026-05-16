



```

## `🌐 TCP/IP Model`

```
┌───────────────────┬────────────────────────────────────────────────┐
│ Layer             │ Protocols                                      │
├───────────────────┼────────────────────────────────────────────────┤
│ Application       │ HTTP · HTTPS · FTP · SSH · DNS · SMTP · SNMP  │
│ Transport         │ TCP · UDP                                      │
│ Internet          │ IP · ICMP · ARP                               │
│ Network Access    │ Ethernet · Wi-Fi · MAC                        │
└───────────────────┴────────────────────────────────────────────────┘
```

### TCP vs UDP:
```
# TCP (Transmission Control Protocol)
> Connection-oriented — 3-way handshake (SYN → SYN-ACK → ACK)
> Reliable delivery — packets are acknowledged and retransmitted
> Used by: HTTP, HTTPS, SSH, FTP, SMTP

# UDP (User Datagram Protocol)
> Connectionless — fire and forget
> Faster but no guarantee of delivery
> Used by: DNS, DHCP, VoIP, video streaming, gaming
```

### TCP 3-Way Handshake:
```
  Client                         Server
    │                              │
    │  ──── SYN ────────────────►  │   "I want to connect"
    │  ◄─── SYN-ACK ────────────   │   "OK, acknowledged"
    │  ──── ACK ────────────────►  │   "Connection established"
    │                              │
```

---

```
╔══════════════════════════════════════════════════╗
║        C O M M O N   P O R T S                  ║
╚══════════════════════════════════════════════════╝
```

## `🔌 Important Ports to Know`

```
# ── WEB ────────────────────────────────────────────────
> 80    HTTP        — Unencrypted web traffic
> 443   HTTPS       — Encrypted web traffic (TLS/SSL)
> 8080  HTTP-Alt    — Dev servers, proxies

# ── FILE TRANSFER ────────────────────────────────────────
> 20    FTP Data    — File transfer data channel
> 21    FTP Control — FTP command channel
> 22    SSH/SFTP    — Secure shell + encrypted file transfer
> 69    TFTP        — Trivial FTP (UDP, no auth — dangerous)

# ── EMAIL ────────────────────────────────────────────────
> 25    SMTP        — Sending email (often abused for spam)
> 110   POP3        — Receiving email (unencrypted)
> 143   IMAP        — Receiving email (synced)
> 465   SMTPS       — SMTP over SSL
> 993   IMAPS       — IMAP over SSL

# ── NETWORK SERVICES ─────────────────────────────────────
> 53    DNS         — Domain Name System (TCP + UDP)
> 67/68 DHCP        — Dynamic IP assignment
> 123   NTP         — Time synchronization
> 161   SNMP        — Network device monitoring

# ── REMOTE ACCESS ────────────────────────────────────────
> 23    Telnet      — Unencrypted remote access (AVOID)
> 3389  RDP         — Windows Remote Desktop
> 5900  VNC         — Remote desktop (cross-platform)

# ── DATABASES ────────────────────────────────────────────
> 3306  MySQL       — MySQL/MariaDB
> 5432  PostgreSQL  — PostgreSQL
> 27017 MongoDB     — MongoDB
> 1433  MSSQL       — Microsoft SQL Server

# ── HACKING / PENTESTING CONTEXT ─────────────────────────
> 4444  Metasploit  — Default reverse shell listener
> 1337  Leet        — Often used in CTF backdoors
> 31337 Elite       — Legacy hacker port
```

---

```
╔══════════════════════════════════════════════════╗
║         K E Y   P R O T O C O L S               ║
╚══════════════════════════════════════════════════╝
```

## `📡 DNS — Domain Name System`

```
# How DNS works:
> You type: google.com
> Your system asks the DNS resolver: "What's the IP?"
> Resolver checks cache → asks root → TLD → authoritative server
> Returns: 142.250.80.46
> Your browser connects to that IP

# DNS Record Types:
> A      →  Maps domain to IPv4 address
> AAAA   →  Maps domain to IPv6 address
> CNAME  →  Alias — points one domain to another
> MX     →  Mail server records
> TXT    →  Verification, SPF, DKIM records
> NS     →  Nameserver records
> PTR    →  Reverse lookup (IP → domain)

# DNS Attacks:
> DNS Spoofing     — Poisoning cache with fake records
> DNS Enumeration  — Finding subdomains via brute force
> DNS Tunneling    — Hiding data exfiltration in DNS queries
```

## `🔒 HTTP vs HTTPS`

```
# HTTP (Port 80)
> Plain text — anyone on the network can read it
> No verification of server identity
> NEVER send passwords or sensitive data over HTTP

# HTTPS (Port 443)
> Encrypted via TLS (Transport Layer Security)
> Server presents a digital certificate for identity verification
> Uses asymmetric encryption (handshake) → symmetric (session)

# TLS Handshake (simplified):
> Client → "Hello, here are the cipher suites I support"
> Server → "Here's my certificate and chosen cipher"
> Client → Verifies cert, sends session key (encrypted)
> Both   → Switch to symmetric encryption for the session
```

## `🐚 SSH — Secure Shell`

```
# What SSH does:
> Encrypted remote login to another machine
> Replaces Telnet (which is plain text and dangerous)
> Also used for: SFTP, port forwarding, tunneling

# Basic SSH commands:
> ssh user@192.168.1.10              # Connect to remote host
> ssh -p 2222 user@host             # Specify custom port
> ssh -i key.pem user@host          # Use private key file
> ssh -L 8080:localhost:80 user@host  # Local port forwarding

# SSH Key-based authentication (more secure than password):
> ssh-keygen -t rsa -b 4096         # Generate RSA key pair
> ssh-copy-id user@host             # Copy public key to server
```

## `📁 FTP — File Transfer Protocol`

```
# Ports: 20 (data) · 21 (control)
# WARNING: FTP sends credentials in PLAIN TEXT — avoid on public networks

# Secure alternatives:
> SFTP  →  SSH File Transfer Protocol (port 22)
> FTPS  →  FTP over TLS/SSL (port 990)

# FTP commands (basic):
> ftp 192.168.1.10                  # Connect to FTP server
> ls                                # List files
> get filename.txt                  # Download file
> put localfile.txt                 # Upload file
> quit                              # Exit
```

---

```
╔══════════════════════════════════════════════════╗
║         S U B N E T T I N G                     ║
╚══════════════════════════════════════════════════╝
```

## `🧮 Subnetting Basics`

```
# What is an IP Address?
> IPv4: 32-bit number written as 4 octets — e.g. 192.168.1.100
> Each octet: 0–255

# What is a Subnet Mask?
> Divides IP into Network + Host portions
> Example: 255.255.255.0  →  /24 in CIDR notation

# CIDR Notation Quick Reference:
┌────────────┬──────────────────┬───────────────┬─────────────────┐
│ CIDR       │ Subnet Mask      │ Hosts         │ Example         │
├────────────┼──────────────────┼───────────────┼─────────────────┤
│ /8         │ 255.0.0.0        │ 16,777,214    │ 10.0.0.0/8      │
│ /16        │ 255.255.0.0      │ 65,534        │ 172.16.0.0/16   │
│ /24        │ 255.255.255.0    │ 254           │ 192.168.1.0/24  │
│ /25        │ 255.255.255.128  │ 126           │ 192.168.1.0/25  │
│ /30        │ 255.255.255.252  │ 2             │ Point-to-point  │
│ /32        │ 255.255.255.255  │ 1 (host only) │ Single IP       │
└────────────┴──────────────────┴───────────────┴─────────────────┘

# Private IP Ranges (not routable on the internet):
> 10.0.0.0/8         — Class A private
> 172.16.0.0/12      — Class B private
> 192.168.0.0/16     — Class C private (home/office networks)

# Special Addresses:
> 127.0.0.1          — Loopback (localhost)
> 0.0.0.0            — Any/all interfaces
> 255.255.255.255    — Broadcast
```

---

```
╔══════════════════════════════════════════════════╗
║      N E T W O R K I N G   T O O L S            ║
╚══════════════════════════════════════════════════╝
```

## `🛠️ Essential Networking Commands`

```
# ── IP & INTERFACE INFO ──────────────────────────────────
> ip a                           # Show all network interfaces and IPs
> ip r                           # Show routing table
> ifconfig                       # Legacy interface info (older systems)
> hostname -I                    # Quick IP address check

# ── CONNECTIVITY ─────────────────────────────────────────
> ping 8.8.8.8                   # Test connectivity (Google DNS)
> ping -c 4 google.com           # Send exactly 4 packets
> traceroute google.com          # Trace hops to destination
> mtr google.com                 # Live traceroute (combined ping + trace)
> curl -I https://example.com    # Check HTTP response headers

# ── DNS LOOKUP ───────────────────────────────────────────
> nslookup google.com            # Basic DNS query
> dig google.com                 # Detailed DNS query
> dig google.com MX              # Check mail records
> dig -x 8.8.8.8                 # Reverse DNS lookup
> host google.com                # Simple DNS resolution

# ── PORT & CONNECTION INFO ───────────────────────────────
> ss -tulnp                      # Show all listening ports (modern)
> netstat -tulnp                 # Show listening ports (legacy)
> netstat -an | grep ESTABLISHED # Show active connections
> lsof -i :80                    # What process is using port 80?

# ── TRAFFIC ANALYSIS ─────────────────────────────────────
> tcpdump -i eth0                # Capture all traffic on eth0
> tcpdump -i eth0 port 80        # Capture HTTP traffic only
> tcpdump -w capture.pcap        # Save capture to file
> tcpdump -r capture.pcap        # Read saved capture
> tcpdump host 192.168.1.10      # Filter by IP address

# ── NMAP (Network Scanner) ───────────────────────────────
> nmap 192.168.1.1               # Basic scan
> nmap -sV 192.168.1.1           # Detect service versions
> nmap -O 192.168.1.1            # OS detection
> nmap -p 1-1000 192.168.1.1     # Scan specific port range
> nmap -sn 192.168.1.0/24        # Ping sweep (host discovery)
> nmap -A 192.168.1.1            # Aggressive scan (OS + service + scripts)

# ── FILE TRANSFER ─────────────────────────────────────────
> scp file.txt user@host:/path/  # Secure copy to remote
> rsync -avz src/ user@host:/dst # Sync files over SSH
> wget https://example.com/file  # Download file from URL
```

---

```
╔══════════════════════════════════════════════════╗
║     N E T W O R K   A T T A C K   T Y P E S     ║
╚══════════════════════════════════════════════════╝
```

## `⚠️ Common Network Attacks`

```
> Man-in-the-Middle (MITM)
  ↳ Attacker intercepts traffic between two parties
  ↳ Tools: arpspoof, ettercap, Bettercap
  ↳ Defense: TLS/HTTPS, VPN, network segmentation

> ARP Spoofing
  ↳ Attacker sends fake ARP replies to poison the ARP cache
  ↳ Redirects traffic through attacker's machine
  ↳ Defense: Dynamic ARP Inspection (DAI), static ARP entries

> DNS Spoofing / Cache Poisoning
  ↳ Injecting fake DNS records to redirect users
  ↳ Defense: DNSSEC, use trusted resolvers

> Port Scanning
  ↳ Probing a target for open ports and services
  ↳ Tool: Nmap
  ↳ Defense: Firewall rules, port knocking, IDS

> DoS / DDoS
  ↳ Flooding a target with traffic to cause unavailability
  ↳ Types: SYN flood, UDP flood, HTTP flood
  ↳ Defense: Rate limiting, CDN, upstream filtering

> Packet Sniffing
  ↳ Capturing unencrypted traffic on a network
  ↳ Tools: Wireshark, tcpdump
  ↳ Defense: Encryption (TLS/SSH), switched networks, VPN
```

---

```
> "Know the network. Own the network."
> "Every packet tells a story — learn to read them."
```

---

*Part of the [Linux_Cybersec_Course](https://github.com/Ayushburman/Linux_Cybersec_Course)*
