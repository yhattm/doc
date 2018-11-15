<pre>
for example, telnet by expect

#!/usr/bin/expect #Where the script should be run from.
#./telnetExpect server port user password

#If it all goes pear shaped the script will timeout after 20 seconds.
set timeout 20
#First argument is assigned to the variable server
set server [lindex $argv 0]
#First argument is assigned to the variable port
set port [lindex $argv 1]
##Second argument is assigned to the variable user
set user [lindex $argv 2]
#Third argument is assigned to the variable password
set password [lindex $argv 3]
#This spawns the telnet program and connects it to the variable name
spawn telnet $server $port
#The script expects login
expect "login:"
#The script sends the user variable
send "$user"
#Enter
send -- "\r"
#The script expects Password
expect "Password:"
#The script sends the password variable
send "$password"
#Enter
send -- "\r"
#This hands control of the keyboard over two you (Nice expect feature!)

interact
</pre>
