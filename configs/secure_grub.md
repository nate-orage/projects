# Secure GRUB
Set a password for grub.
```bash
grub-mkpassword-pbkdf2
```
## Secure grub
Copy hashed output after setting grub password. Edit /etc/grub.d/40_custom
```bash
sudo nano /etc/grub.d/40_custom
```
On the last line, input:
```bash
set superusers='root'
password_pbkdf2 root <hash value>
```
Update grub
```bash
sudo update-grub2
```
You may reboot and grub will prompt you for root username/password.