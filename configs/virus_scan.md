# Virus Scanning
## Installing clamav
sudo apt install && sudo apt install clamav clamav-daemon
 ## Checking the status
systemctl status clamav-freshclam
systemctl status clamav-daemon
 ## Starting the clamav daemon
systemctl start clamav-daemon
 ## Enabling the daemon to start and boot
systemctl enable clamav-daemon
 ## Getting a test virus
wget www.eicar.org/download/eicar.com
 ## Scanning a directory using clamdscan
clamdscan --fdpass /root/
 ## Moving found viruses to a quarantine directory
clamdscan --move=/quarantine --fdpass /root
 ## Scanning a directory using clamscan
clamscan --recursive /etc
clamscan --recursive --infected /quarantine
clamscan --recursive --infected --remove /quarantine/