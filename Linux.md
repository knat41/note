

## รวมคำสั่งที่อาจจะจำเป็น เมื่อต้อง upgrade 14.04 to 20.04
## ubuntu
```linux
do-release-upgrade --proposed
```  
### add user แบบมี home directory
```linux
useradd -s /bin/bash -d /home/{user}/ -m -G sudo {user}
```
### Disabling the root account password
```linux
sudo passwd -l root
```  
### Enabling the root account
```linux
sudo passwd
```
### Add a user
``` 
sudo adduser username
```
### Link
* https://ubuntu.com/server/docs/user-management
* 
# เมื่อกระทำผ่าน ssh
* https://krystal.io/blog/post/upgrading-ubuntu-20-04-to-22-04-lts-using-the-command-line

Command
https://unix.stackexchange.com/questions/277203/whats-the-fastest-way-to-remove-all-files-subfolders-in-a-directory
