1. sudo apt-get update
1. sudo apt install cups -y
1. ps ax | grep cup
    ```dotnetcli
     1867 ?        Ss     0:00 /usr/sbin/cupsd -l
     1918 ?        Ssl    0:00 /usr/sbin/cups-browsed
     3930 pts/1    S+     0:00 grep --color=auto cups
    ```
1. sudo usermod -a -G lpadmin pi
1. sudo nano /etc/dhcpcd.conf
    ```dotnetcli
    interface wlan0
    static ip_address=192.168.0.99/24
    static routers=192.168.0.1
    static domain_name_servers=192.168.0.1
    ```
1. sudo cupsctl --remote-any
1. Finish following directions in the UI
https://www.tomshardware.com/how-to/raspberry-pi-print-server