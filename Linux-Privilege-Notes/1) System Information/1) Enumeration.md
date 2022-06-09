1) System Enumeration
cat /proc/version
cat /etc/issue
uname -a (for gathering kernel version)


ps aux (List of process that are running )


2) User Enumeration 
whoami 
id
sudo -l
history

3) Network Enumeration  
ifconfig 
ip a 
ip neigh
netstat  ano

4) Password hunting
	grep --color=auto -rnw '/' -ie "PASSWORD" --color=always 2> /dev/null