* Install
  * apt-get install udhcpd
* /etc/default/udhcpd
  * comment the line that says DHCPD_ENABLED="no"
* /etc/udhcpd.conf
  * start 192.168.0.102         #These IPs must to be in the same subset as your current default route
  * end 192.168.0.117
  * interface ap0
  * opt dns 192.168.0.1         #Your current default route (Gateway)
  * option subnet 255.255.255.0
  * opt router 192.168.0.101    #This IP must to be in the same subset as your current default route
  * option  domain  localhost