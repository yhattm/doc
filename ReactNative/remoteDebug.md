<pre>
netsh interface portproxy add v4tov4 listenport=8081 listenaddress=127.0.0.1 connectport=8081 connectaddress=54.183.177.64

netsh interface portproxy delete v4tov4 listenport=8081 listenaddress=127.0.0.1

http://localhost:8081/debugger-ui
</pre>