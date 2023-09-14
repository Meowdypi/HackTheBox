FTP is old and slow so rsync is preferred in scenarios where a few changes need to be sent to a few files instead of every file every time.
	Changes are called **deltas**
		using deltas to update files is an efficient way to reduce bandwidth & time
![[Pasted image 20230905175410.png]]

The main stages of an rsync transfer are the following:  
1. rsync establishes a connection to the remote host and spawns another rsync receiver process.  
2. The sender and receiver processes compare what files have changed.  
3. What has changed gets updated on the remote host

![[Pasted image 20230905175153.png]]
![[Pasted image 20230905175556.png]]
![[Pasted image 20230905175617.png]]
![[Pasted image 20230905175827.png]]

### Flag:
![[Pasted image 20230905180031.png]]
