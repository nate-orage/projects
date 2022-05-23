# FULL DISK ENCRYPTION
 
## 1. installing cryptsetup & dm-crypt
```bash
apt install cryptsetup
```
 
## 2. Idenfity the name of the disk or partition to encrypt:
```bash
fdisk -l  # for this example it will be /dev/sdc
or 
dmesg  # for usb sticks

```
 
## 3. Filling the disk or partition to encrypt with random data (optional)
```bash
dd if=/dev/urandom of=/dev/sdc status=progress
```
 
## 4. Initialize the LUKS partition and set the initial passphrase
```bash
cryptsetup -y -v luksFormat /dev/sdc 
 
    WARNING!
    ========
    This will overwrite data on /dev/sdc irrevocably.
    
    Are you sure? (Type uppercase yes): YES
    Enter passphrase for /dev/sdc: 
    Verify passphrase: 
    Command successful.
```
 
##5.  Open the encrypted device and set up a mapping name
```bash
cryptsetup luksOpen /dev/sdc secretdata
ls -l /dev/mapper
```
 
## display the status of the mapping file
```bash
cryptsetup status secretdata
```
 
## 6. Format the filesystem
```bash
mkfs.ext4 /dev/mapper/secretdata
```
 
## 7. Mount the encrypted file system into the main file tree.
```bash
mount /dev/mapper/secretdata /mnn  # -> you can mount it to any existing directory like /mnt
```
 
## 8. Unmount the encrypted disk
```bash
umount /mnt
cryptsetup luksClose secretdata
```
 
## 9. Accesing the encrypted disk after a restart or unmounting:
```bash
cryptsetup luksOpen /dev/hdc secretdata
mount /dev/mapper/secretdata /root/secret
```
 
##10. Unlocking LUKS Encrypted Drives With A Keyfile
 
## generating a random keyfile
```bash
dd if=/dev/urandom of=/root/keyfile bs=1024 count=4
```
 
## set the permissions (only root can read it)
```bash
chmod 400 /root/keyfile
```
 
## add the keyfile as an additional authorization method
```bash
cryptsetup luksAddKey /dev/sdc /root/keyfile
```
 
## unlock the drive using the keyfile
```bash
cryptsetup luksOpen /dev/hdc secret --key-file /root/keyfile
```
