#SSTI #nodejs #web #burp 
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/7fa4ff81-f2dc-4673-85cb-57a2adb53e18)
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/2e31d69c-cdef-46a4-80f8-0934359fe122)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/95a6edbb-55fa-494f-85bb-b09b53fbdf82)


![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/c3489c16-773a-4a40-a650-500b1c4fc5e5)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/551fdd13-f06c-4bbd-95ee-c4007aa8de2d)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/fe6f6d35-198f-4f95-9665-9bba25e95206)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/c8b22a1a-33c9-4a59-821b-2e9c4da2181f)
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/27de5fdf-3e4b-4426-b984-4139de2269ed)
 
 {{7*7}}
 ${7*7}
 <%= 7*7 %>
 ${{7*7}}
 #{7*7}

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/1a35124e-cbc0-4911-ab7e-9a0c39beb863)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/3570c49d-e788-4167-a8d2-0cb9bea8cc71)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/9d9c3312-5bd5-46bd-8f7f-73f1df34e422)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/fe27fa31-774f-4414-bac8-204cc77256d3)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/9696b15b-f18f-4ac7-afd2-24d25a8608e7)


[HackTricks SSTI](https://book.hacktricks.xyz/pentesting-web/ssti-server-side-template-injection)

Turn on FoxyProxy & open Burpsuite/turn on intercept.
Submit a request on the website.
Send the request to repeater:
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/7556bc92-8521-4bfa-b7bd-065a34d8a59b)


Paste the Handlebars payload that can be found in the Hacktricks site into the decoder tab in Burpsuite to URL encode it:
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/a26b6c2b-c395-44da-a88c-1442969b8586)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/a9ed3a15-b070-4515-950c-da8c9e777f04)


Copy the URL encoded payload and paste it in the "email =" field and then hit 'Send':
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/2f946338-d1e8-41a9-ba24-841fedb36456)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/aa59932b-ed46-4185-8554-472a88f4e313)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/1acf32cf-65f3-4355-a526-ff946e729b7d)

 Error occurs because of this in the payload: 
 ![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/40474cb7-b537-4cf9-b606-105d814bb088)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/d74a7d59-de2b-4ee9-8cf9-7c4a63e3b621)


#### Edit {{this.push :
1. Payload 1:
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/71a4b593-1bd0-4cf0-b610-dd7e8b36ebad)

2. Payload 2 (hit backspace to put 'process.mainModule.... on the line above with a space after 'return'). Should return root in response to whoami command:
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/25c8cb27-05b5-48dd-ba57-6e519203ca0b)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/e056526f-2b74-4e36-a981-3f97b73f9120)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/1736dd94-cf91-4e25-bf86-ab69be97059d)


## Flag:
Update payload in the decoder to return 'ls /root'
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/1392ee68-9425-4175-97dd-3b9aa051b340)

![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/f69afe15-40b7-4e44-a901-db410664b2cf)


Update the payload one last time to 'cat /root/flag.txt'
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/089944c6-f9d4-4c55-bf3e-423b8094723f)
![image](https://github.com/Meowdypi/HackTheBox/assets/122643833/3daa6c29-60b3-4414-a0a6-4e7534defac0)

