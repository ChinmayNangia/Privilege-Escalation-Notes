we are going to look for registrty service and see if we have full control over a registry key

what we can do is compile an executable in C make it to run a command (that is a user(us) to add to admin group )

to do that use the command
`Get-Acl -Path hklm:\System\CurrentControlSet\services\regsvc | fl`



we can see we have full control over the `NT\AUTHORITY Interactive`
![[service escalation registry -1.png]]

we can maliciously add the executable to the service and restart the service
and done that will add user to admin
