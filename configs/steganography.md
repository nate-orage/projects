# [Steganogrpahy](https://en.wikipedia.org/wiki/Steganography)
## installing steghide
```bash
apt update && apt install steghide
```
## embedding a secret file into a cover file
steghide embed -ef secret.txt -cf cat.jpg 
Enter passphrase: 
Re-Enter passphrase: 
embedding "secret.txt" in "cat.jpg"... done
 
## getting info about a cover/stego file
```bash
steghide info cat.jpg 
"cat.jpg":
  format: jpeg
  capacity: 47.5 KB
Try to get information about embedded data ? (y/n) n
```
 
## extracting the secret file from the stego file
```bash
steghide extract -sf cat.jpg 
Enter passphrase: 
wrote extracted data to "secret.txt".
```
