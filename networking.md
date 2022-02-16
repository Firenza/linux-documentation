#### Getting all devices on a subnet
`echo 192.168.1.{1..254}|xargs -n1 -P0 ping -c1|grep "bytes from"`
`sudo nmap -sn 192.168.1.0/24 | grep Nmap`
