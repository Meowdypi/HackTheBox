FTP is old and slow so rsync is preferred in scenarios where a few changes need to be sent to a few files instead of every file every time.
	Changes are called **deltas**
		using deltas to update files is an efficient way to reduce bandwidth & time
![image](https://github.com/Meowdypi/Starting-Point---Tier-0/assets/122643833/917b5a94-8faa-4ea8-8fb8-50f87f72c894)

The main stages of an rsync transfer are the following:  
1. rsync establishes a connection to the remote host and spawns another rsync receiver process.  
2. The sender and receiver processes compare what files have changed.  
3. What has changed gets updated on the remote host

![image](https://github.com/Meowdypi/Starting-Point---Tier-0/assets/122643833/ae7179bb-9b0a-4d84-8fba-bf37d66c5f47)
![image](https://github.com/Meowdypi/Starting-Point---Tier-0/assets/122643833/1161004d-b7e6-4404-bdf2-42982d776779)
![image](https://github.com/Meowdypi/Starting-Point---Tier-0/assets/122643833/58741a45-1f4a-4fcc-8eb0-26a02a336052)

### Flag:
![image](https://github.com/Meowdypi/Starting-Point---Tier-0/assets/122643833/d405f8fd-9911-490e-83e9-e16509288433)
