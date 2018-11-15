# SSH Tunnel

<pre>
ssh -N -L LocalPort:DestHost:DestHostPort User@ServerPublicIP

for example:
ssh -N -L 8080:www.google.com:80 -i key.pem ubuntu@ServerPublicIP
curl localhost:8080
</pre>

# SSH Reverse Tunnel

<pre>
ssh -N -R ServerLocalPort:DestHost:DestHostPort  User@ServerPublicIP

for example:
到內網的機器去執行ssh reverse tunnel，可以把機器區網裡面的192.168.1.1:80開出來，然後就可以去Server連8080
機器:
ssh -N -R 8080:192.168.1.1:80 User@ServerPublicIP
Server:
curl localhost:8080

for example:
到內網的機器去執行ssh reverse tunnel，可以把機器的ssh port 22開出來，然後就可以去Server用ssh localhost:7070
ssh -N -R 7070:localhost:22 User@ServerPublicIP
</pre>

# Dropbear
mkdir /etc/dropbear

./dropbear -F -R -E -p 2222

# Copy file via ssh without scp
cat file | ssh root@IP "cat > /path/file"

# SSH login with key

<pre>
useradd -m -d /home/username -s /bin/bash username
Create a key pair from the client which you will use to ssh from: 
ssh-keygen -t dsa
Copy the public key /home/username/.ssh/id_dsa.pub onto the ssh server into /home/username/.ssh/authorized_keys
</pre>
