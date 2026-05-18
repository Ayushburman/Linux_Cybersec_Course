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
