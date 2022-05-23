# Securing User Accounts
## Lock password authentication
```bash
sudo passwd -l USERNAME
sudo password --lock USERNAME
```
## Check account status
```bash
sudo passwd --status USERNAME
sudo chage -l USERNAME
```
## Unlock password authentication
```bash
sudo passwd -u USERNAME
```
## Disable account
```bash
sudo usermod --expiredate 1 tux
sudo usermod --expiredate 1970-01-02 tux
```
## Check account expiration
```bash
sudo chage -l tux
```