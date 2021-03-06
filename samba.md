#### Install samba

`sudo apt-get install samba samba-common-bin`

#### Configure samba

1. `sudo nano /etc/samba/smb.conf` to do the updates
1. `testparm` to validate your changes
1. `sudo systemctl restart smbd` to restart samba so the updates are in effect

#### Managing samba users

* Use the `smbpasswd` command to add / remove / change samba users. E.G. `sudo smbpasswd -a pi` to add samba user `pi`
* Use the `sudo pdbedit -L -v` command to the current samba users

Linux will map samba users to linux users when taking into account directory persmissions. E.G. If you have a folder in linux
that's owned by a user called `pi`, and you want to interact with it through samba as if you were interacting with it in linux as the user `pi`
, you just create a samba user of the same name and use that samba user/pass when connecting to the file share.

#### Troubleshooting

By default logs will go to `/var/log/samba`.  To update the verbosity of those logs you can add a `log level = 3` line to your `smb.conf` file.

To reset cached network credentials in Windows Explorer do the following

1. Close Explorer
1. Run `net use * /DELETE` in a command prompt
1. on the linux machine run `sudo systemctl restart smbd.service` to restart the samba service

If the windows command doesn't do anything won't work. For some reason connections sometimes don't show up there
