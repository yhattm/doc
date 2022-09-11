# systemd config
* sudo vi /etc/systemd/system/vscodeserver.service
<pre>
[Unit]
Description=vscode server

[Service]
User=pi
Type=simple
ExecStart=code-server
Restart=always

[Install]
WantedBy=multi-user.target
</pre>

# systemctl
* systemctl | grep vscodeserver
* sudo systemctl enable vscodeserver
* sudo systemctl start vscodeserver
* systemctl status vscodeserver
