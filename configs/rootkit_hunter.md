# Rootkit hunter and chkrootkit

## Install
```bash
apt install -y rkhunter chkrootkit
```
## Update
```bash
rkhunter --propupd
```
## Run full system check 
```bash
rkhunter --check # => /var/log/rkhunter.log
rkhunter --check --report-warnings-onl
```
## Run chkrootkit scan
```bash
chkrootkit
chkrootkit -q
```