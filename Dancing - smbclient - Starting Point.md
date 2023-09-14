#SMB #OSI 
### One way to transfer files between 2 hosts on the same network:
*SMB* (Server Message Block)
	usually runs on Windows machines
	port 445 TCP
	runs on the Application or Presentation layer of the OSI Model
	Due to this, it relies on lower-level protocols for transport. 
		The Transport layer protocol that Microsoft SMB Protocol is most often used with is NetBIOS over TCP/IP (NBT). 
		This is why, during scans, we will most likely see both protocols with open ports running on the target.

![Pasted image 20230805104024](https://github.com/Meowdypi/Starting-Point---Tier-0/assets/122643833/0cee8b02-2c64-4b96-bba5-b4faff95f33c)

An SMB-enabled storage on the network is called a *share*
	can be accessed by anyone with the server address and proper credentials
	network administrators can make mistakes and allow guest accounts or anonymous logins to the share

### Enumeration
-sV - determine service/version info
-L - use with the smbclient utility to list the available shares
	$ smbclient -L 10.0.0.1
![image](https://github.com/Meowdypi/Starting-Point---Tier-0/assets/122643833/cb00fa4e-dce7-4e4d-b62b-a655fa6a5c40)



Shares returned when using -L
![image](https://github.com/Meowdypi/Starting-Point---Tier-0/assets/122643833/62a2c8f6-d00d-4316-947b-89e1c6872ffb)


$ smbclient \\\\10.0.0.1\\FILE
	navigate with linux commands (except for cat)
		cd, ls, get, exit

