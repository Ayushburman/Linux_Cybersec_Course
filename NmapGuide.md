```bash

-> Network Mapper (nmap) is an open-source tool for network discovery and security auditing.
It sends raw IP packets to determine what hosts are available, what services those hosts 
offer, what OS they run, and dozens of other characteristics. ethical use Always scan only 
networks you own or have explicit written permission to scan. Unauthorized scanning is illegal
in most jurisdictions.

```
```markdown
How a scan works — packet lifecycle
> Probe sent -> ``bash  nmap crafts a raw packet (SYN, ICMP, UDP...) to a target IP:port
> Network transit -> Packet travels through routers, firewalls, and switches
> Target response (or silence) -> SYN-ACK = open; RST = closed; no reply = filtered
> Nmap interpretation -> Response pattern mapped to port state, OS fingerprint, service version
> Report generation -> Results written to stdout, XML, grepable, or JSON format
```

open | OPEN | Application actively accepting connections on this port |
-----|------|---------------------------------------------------------|
closed| CLOSED| Port accessible but no application listening |
filtered| FILTERED| Firewall/filter blocking; nmap can't determine state|
unfiltered| UNFILTRD| Port accessible but state undetermined (ACK scan) |
openfiltered | OPENFLT | Can't determine if open or filtered (UDP/IP scans)|


<img width="353" height="212" alt="image" src="https://github.com/user-attachments/assets/50750b40-1db1-4162-b697-925de0e96686" />


```bash
-> TCP connect scan — -sT
-> Completes the full 3-way TCP handshake. No root needed. Loud — leaves logs on the target. Default when non-root.
```
<img width="661" height="160" alt="image" src="https://github.com/user-attachments/assets/ffe9cd69-9e22-47be-bde4-4c0237c07fca" />

```bash
-> SYN stealth scan — -sS (default with root)
-> Sends SYN, receives SYN-ACK, then sends RST — never completes handshake.
   Faster, less logged. Requires root/sudo.
```

<img width="653" height="152" alt="image" src="https://github.com/user-attachments/assets/9fce542e-90b9-4d12-a32c-e9fc398a31df" />

```bash
-> UDP scan — -sU
-> Slower than TCP. No handshake. Open = response received.
   Filtered = ICMP port unreachable. Crucial for DNS (53), SNMP (161), NTP (123).
```
<img width="656" height="120" alt="image" src="https://github.com/user-attachments/assets/91da6ec3-1f34-4043-a766-82de3130591b" />


<img width="692" height="330" alt="image" src="https://github.com/user-attachments/assets/012d3199-c30b-4ef7-b2cb-b5a5d07b1c16" />


