There are packages from windows called MSI packages , they are basically windows installers , we have a registry features we can automatically installed elevated (basically installed as admin user)

in CMD type 
`reg query HKLM\Software\Policies\Microsoft\Windows\Installer`

and we can se 
![[always_installed_Elevated-1.png]]
Always installed Elevated = 1 this means we can abuse that 


