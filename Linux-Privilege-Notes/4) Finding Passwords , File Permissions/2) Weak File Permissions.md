1) Able to read shadow file , sudoers file 
2) if we are able to read shadow file , passwd file 
3) If we can take the hash crack it , modify the file permissions then we can either change the UID , GID 
4) finding id_rsa , authorized keys using

		find / -name=authorized_keys 2> /dev/null
		find / -name=id_rsa  2> /dev/null