# Considerations for securing SSH
## Non-standard port
Use a port other than 22 to obscure network scanners.
## Disable root login
PermitRootLogin should be commented out or comment it out and input "PermitRootLogin No"
## Allow specific users
AllowUsers user1 user2 user3...
## Allow specific ip address 
```bash
sudo iptables -A INPUT -p tcp --dport 22 -s <IP Address> -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 22 -j DROP
```
To use entire subnet, input subnet IP instead of individual IP.
## Set inactive timeout
ClientAliveInterval 300 
SSH disconnects after 300 seconds.
## Set maximum number of authentication attempts
MaxAuthTries 10
## Set maximum unauthenticated connections
MaxStartups 25