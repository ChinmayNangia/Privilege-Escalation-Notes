for checking the startup applications check using 
`icacls.exe "C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup"`
from the output we can see
![[Escalation Path - Startup Applications-1.png]]
F-full access
r -read access
rw - read write


`BUILTIN\Users” group has full access ‘(F)’ to the directory`