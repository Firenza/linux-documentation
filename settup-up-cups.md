sudo apt-get update
sudo apt install cups -y
ps ax | grep cup check its running should see
```dotnetcli
 1867 ?        Ss     0:00 /usr/sbin/cupsd -l
 1918 ?        Ssl    0:00 /usr/sbin/cups-browsed
 3930 pts/1    S+     0:00 grep --color=auto cups
```
sudo usermod -a -G lpadmin pi
sudo cupsctl --remote-any
Finish following directions in the UI
https://www.tomshardware.com/how-to/raspberry-pi-print-server