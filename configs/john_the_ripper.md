# Cracking password hashes with John the Ripper
```bash
apt install john
```
# Combine /etc/passwd and /etc/shadow
```bash
unshadow /etc/passwd /etc/shadow > unshadowed.txt
```
# Cracking in single mode

# Brute force and dict attacks

# Dict files
/usr/share/dict
/usr/share/metasploit-framework/data/wordlists (kali)
# Show cracked hashes
```bash
john --show unshadowed.txt
```
# Restore session
```bash
john -restore
```
# Crack accounts per shell
```bash
john --wordlist=mydict.txt --rules --shell=bash,sh unshadowed.txt
```
# Crack specific accounts
```bash
john --wordlist=mydict.txt --rules --users=admin,mark unshadowed.txt
```
# Incremental crack
```bash
john --wordlist=mydict.txt --rules --users=admin,mark unshadowed.txt
```