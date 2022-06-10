**System Enumeration**

Commands for basic system enumeration 
1) systeminfo 
2) syteminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"System Type"
3) whoami

WMIC --> for fixes and patches
4) wmic qfe
5) wmic qfe get Caption,Description,HotFixID,InstalledOn

For getting information on disks 

6) wmic logicaldisk get caption , description,ProviderName 


**User Enumeration**
1) whoami
2) whoami /priv
3) whoami /groups
4) net users (show users present in the machine / Box )


**Network Enumeration**
1) ipconfig
2) ipconfig /all
3) netstat -ano


**Password Hunting**
1) findstr /si password *.txt  *.zip *.config 
2) use cmdkey /list

**Firewall A/V Enumeration**
1) sc query windefend (sc = service control )
2) sc queryex type= service
3) netsh firewall show state 
4) netsh advfirewall firewall dump
5) netsh firewall show  config




