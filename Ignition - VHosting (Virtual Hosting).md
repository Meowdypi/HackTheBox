![[Pasted image 20230913175837.png]]

Getting an error when attempting to access webpage:
	$ curl -v http://10.129.1.93 

Add IP to /etc/hosts to resolve error:
![[Pasted image 20230913180001.png]]
![[Pasted image 20230913180009.png]]
**Virtual hosting** is a method for hosting multiple domain names (with separate handling of each name) on a single server (or pool of servers).[1] This allows one server to share its resources, such as memory and processor cycles, without requiring all services provided to use the same host name. The term virtual hosting is usually used in reference to web servers but the principles do carry over to other Internet services.

![[Pasted image 20230913180445.png]]
![[Pasted image 20230913180513.png]]

### Using Gobuster to brute force directories:
![[Pasted image 20230913181524.png]]
![[Pasted image 20230913181530.png]]

Going to http://ignition.htb/admin:
![[Pasted image 20230913181606.png]]
Try [most common passwords in 2023](https://cybernews.com/best-password-managers/most-common-passwords/):
![[Pasted image 20230913182003.png]]
username: admin
password: qwerty123

![[Pasted image 20230913182147.png]]

## Flag:
![](../../zzImages/Pasted%20image%2020230919153225.png)
![](../../zzImages/Pasted%20image%2020230919153853.png)
