use autorun.exe to check for autorun process
`C:\Users\User\Desktop\Tools\Autoruns\Autoruns64.exe`

we can see a program named my program.exe shows up 

![](/Windows-Privilege-Escalation-Notes/windows_images/autorun-1.png)

then we use a tool called **Accesschk**  to check what type of access we have 
using command `C:\Users\User\Desktop\Tools\Accesschk\accesschk64.exe -wvu "C:\Program Files\Autorun Program"`
-w = writable 
-v verbose 
-u ignore errors

we can se 
<br><br>
![](/Windows-Privilege-Escalation-Notes/windows_images/autorun-2-accesscheck.png)
<br><br>
that we have full read write acces 

another way of using instead of autorun is using **powerup.ps1** present in our /opt dir

1) poweshell -ep bypass
2) `. .\powerUp.ps1`
3) Invoke-AllChecks


![](/Windows-Privilege-Escalation-Notes/windows_images/autorun-3-program.exe.png)


here we can see that we found our  program.exe as auto run and we can se that it has read write access for us 
