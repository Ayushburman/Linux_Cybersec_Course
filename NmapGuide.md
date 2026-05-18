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
