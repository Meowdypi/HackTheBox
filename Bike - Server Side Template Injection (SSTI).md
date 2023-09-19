#SSTI #nodejs #web #burp 
![](../../zzImages/Pasted%20image%2020230916121843.png)
![](../../zzImages/Pasted%20image%2020230916122033.png)
![](../../zzImages/Pasted%20image%2020230916122157.png)

![](../../zzImages/Pasted%20image%2020230916122145.png)
![](../../zzImages/Pasted%20image%2020230916122444.png)
![](../../zzImages/Pasted%20image%2020230916122532.png)
![](../../zzImages/Pasted%20image%2020230916122420.png)
![](../../zzImages/Pasted%20image%2020230916122607.png)
![](../../zzImages/Pasted%20image%2020230916123524.png)
![](../../zzImages/Pasted%20image%2020230916123545.png)
![](../../zzImages/Pasted%20image%2020230916123647.png)
![](../../zzImages/Pasted%20image%2020230916123700.png)
![](../../zzImages/Pasted%20image%2020230916123824.png)
![](../../zzImages/Pasted%20image%2020230916123937.png)
![](../../zzImages/Pasted%20image%2020230916124104.png)
![](../../zzImages/Pasted%20image%2020230916124037.png)

[HackTricks SSTI](https://book.hacktricks.xyz/pentesting-web/ssti-server-side-template-injection)

Turn on FoxyProxy & open Burpsuite/turn on intercept.
Submit a request on the website.
Send the request to repeater:
![](../../zzImages/Pasted%20image%2020230917134158.png)

Paste the Handlebars payload that can be found in the Hacktricks site into the decoder tab in Burpsuite to URL encode it:
![](../../zzImages/Pasted%20image%2020230917134246.png)
![](../../zzImages/Pasted%20image%2020230917134530.png)

Copy the URL encoded payload and paste it in the "email =" field and then hit 'Send':
![](../../zzImages/Pasted%20image%2020230917134654.png)
![](../../zzImages/Pasted%20image%2020230917134859.png)
![](../../zzImages/Pasted%20image%2020230917135907.png)
 Error occurs because of this in the payload: ![](../../zzImages/Pasted%20image%2020230917140418.png)
 ![](../../zzImages/Pasted%20image%2020230917140907.png)

#### Edit {{this.push :
1. Payload 1: ![](../../zzImages/Pasted%20image%2020230917140526.png)
2. Payload 2 (hit backspace to put 'process.mainModule.... on the line above with a space after 'return'). Should return root in response to whoami command: ![](../../zzImages/Pasted%20image%2020230917141904.png)![](../../zzImages/Pasted%20image%2020230917142754.png)
![](../../zzImages/Pasted%20image%2020230917141003.png)

## Flag:
Update payload in the decoder to return 'ls /root'
![](../../zzImages/Pasted%20image%2020230917143008.png)
![](../../zzImages/Pasted%20image%2020230917143024.png)

Update the payload one last time to 'cat /root/flag.txt'
![](../../zzImages/Pasted%20image%2020230919152919.png)
![](../../zzImages/Pasted%20image%2020230919153745.png)
