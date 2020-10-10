Install samba

`sudo apt-get install samba samba-common-bin`

Configure samba

1. `sudo nano /etc/samba/smb.conf` to do the updates
1. `testparm` to validate your changes
1. `sudo systemctl restart smbd` to restart samba so the updates are in effect

Managing samba users

* Use the `smbpasswd` command to add / remove / change samba users. E.G. `sudo smbpasswd -a pi` to add samba user `pi`
* Use the `sudo pdbedit -L -v` command to the current samba users

Linux will map samba users to linux users when taking into account directory persmissions. E.G. If you have a folder in linux
that's owned by a user called `pi`, and you want to interact with it through samba as if you were interacting with it in linux as the user `pi`
, you just create a samba user of the same name and use that samba user/pass when connecting to the file share.
