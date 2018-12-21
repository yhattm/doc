<pre>
wpa_cli -i wlan0 scan
wpa_cli -i wlan0 scan_result
wpa_cli -i wlan0 list_networks
wpa_cli -i wlan0 add_network
wpa_cli -i wlan0 remove_network 0
wpa_cli -i wlan0 set_network 0 ssid '"MyWifiAP"'
wpa_cli -i wlan0 set_network 0 key_mgmt WPA-PSK
wpa_cli -i wlan0 set_network 0 psk '"Password"'
wpa_cli -i wlan0 enable_network 0
wpa_cli -i wlan0 select_network 0
wpa_cli -i wlan0 status
</pre>
