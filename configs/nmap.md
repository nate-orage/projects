# Nmap
## Syn Scan - Half Open Scanning (root only)
```bash
nmap -sS 192.168.0.1
```
## Connect Scan
```bash
nmap -sT 192.168.0.1
```
## Scanning all ports (0-65535)
```bash
nmap -p- 192.168.0.1
```
## Specifying the ports to scan
```bash
nmap -p 20,22-100,443,1000-2000 192.168.0.1
```
## Scan Version
```bash
nmap -p 22,80 -sV 192.168.0.1
``` 
## Ping scanning (entire Network)
```bash
nmap -sP 192.168.0.0/24
```
## Treat all hosts as online -- skip host discovery
```bash
nmap -Pn 192.168.0.101
```
## Excluding an IP
```bash
nmap -sS 192.168.0.0/24 --exclude 192.168.0.10
```
## Saving the scanning report to a file
```bash
nmap -oN output.txt 192.168.0.1
```
## OS Detection
 ```bash
nmap -O 192.168.0.1
```
## Enable OS detection, version detection, script scanning, and traceroute
nmap -A 192.168.0.1
 ```bash
https://nmap.org/book/performance-timing-templates.html
 
-T paranoid|sneaky|polite|normal|aggressive|insane (Set a timing template)
These templates allow the user to specify how aggressive they wish to be, while leaving Nmap to pick the exact
timing values. The templates also make some minor speed adjustments for which fine-grained control options do
not currently exist.
``` 
## -A OS and service detection with faster execution
```bash
nmap -A -T aggressive cloudflare.com
```
## Using decoys to evade scan detection
```bash
nmap -p 22 -sV 192.168.0.101 -D 192.168.0.1,192.168.0.21,192.168.0.100
``` 
## reading the targets from a file (ip/name/network separeted by a new line or a whitespace)
```bash
nmap -p 80 -iL hosts.txt 
```
## exporting to out output file and disabling reverse DNS
```bash
nmap -n -iL hosts.txt -p 80 -oN output.txt
```