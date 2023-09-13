## Understanding NFS (Network File System)
Allows a system to share directories and files with others over a network. Using NFS, users, and programs can access files on remote systems almost as if they were local files. It does this by mounting all or a portion of the file system on a server. The portion of the mounted file system can be accessed by clients with whatever privileges are assigned to each file.




How does NFS work
The client will request to mount a directory from a remote host on a local directory just the same way it can mount a physical device. The mount service will then act to connect the relevant mount daemon using RPC
An RPC call is placed to NFSD on the server if someone wants to access a file using NFS. This call takes parameters such as.
- File handle
- Name of the file to be accessed
- User ID
- Group ID

What runs NFS
Using the NFS protocol, you can transfer files between computers running Windows and other non-Windows OS. A Windows server computer can act as an NFS file server for other non-Windows client computers. Likewise, NFS allows a Windows-based computer running Windows Server to access files stored on a non-Windows NFS server.

Question: What does NFS stand for?
Network File System

Question: What process allows an NFS client to interact with a remote directory as though it were a physical device? 

Action: mounting

Question: What does NFS use to represent files and directories on the server?
Answer file handle

Question: What protocol does NFS use to communicate between the server and client?
Answer: RPC

Question: What two pieces of user data does the NFS server take as parameters for controlling user permissions?
Answer: user id /guest id

Question: Can a Windows NFS server share files with a Linux client?
Answer: Y

Question: Can a Linux NFS server share files with a MacOS client?
Answer: Y

Question: What is the latest version of NFS?
Answer: 4.2


## Enumerating NFS
10.10.48.101
Nmap -A -p- -T4 

Conduct a thorough port scan of your choosing; how many ports are open?
Answer:

Question: Which port contains the service we're looking to enumerate?
Answer:

Question: Now, use "/usr/sbin/showmount" -e [IP] to list the NFS shares; what is the name of the visible share?
Answer:

Question: Use the mount command we broke down earlier to mount the NFS share to your local machine. Change the directory to where the share. What is the name of the folder inside?
Answer:

Question: Interesting! Let's do a bit of research now and have a look through the folder. Which folders could contain keys that would give us remote access to the server?
Answer:

Question: Which of these keys is most useful to us?
Answer:

Question: Can we log into the machine using ssh -i <key-file> <username>@<IP>?
NFS-Common

