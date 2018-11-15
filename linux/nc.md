# copy file
nc -l port > file

nc IP port < file

# tar folder
nc -l port | tar xvf -

tar cvf - /path | nc IP port

# check UDP port
nc -u -v localhost port

# check TCP port
nc  -v localhost port

# echo msg to UDP port with timeout 1S
echo -n "msg" | nc -u -w 1 IP port

# Receive UDP port to stdout
nc -lu localhost port

# scan port
nc -vnz -w 1 192.168.233.208 1-1000 2000-3000

# webpage http://IP:8000/test.html
while true; do nc -l 8000 < test.html; done

# make unix socket
nc -lU /var/tmp/dsocket