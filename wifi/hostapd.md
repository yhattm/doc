* Install
  * apt-get install hostapd
* Config file
  * gunzip /usr/share/doc/hostapd/examples/hostapd.conf.gz
  * cp /usr/share/doc/hostapd/examples/hostapd.conf /etc/
* /etc/hostapd.conf
  * interface=ap0
  * driver=nl80211
  * ssid=AP
  * wpa=2
  * wpa_passphrase=password
  * wpa_key_mgmt=WPA-PSK
  * wpa_pairwise=TKIP
  * rsn_pairwise=CCMP
* /etc/default/hostapd
  * DAEMON_CONF="/etc/hostapd/hostapd.conf"
* Add interface
  * iw phy phy0 interface add ap0 type __ap
  * ifconfig ap0 192.168.0.101 up 