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
Using the NFS protocol, you can transfer files between computers running Windows and other non-Windows OS. A computer running a Windows server can act as an NFS file server for other non-Windows client computers. Likewise, NFS allows a Windows-based computer running Windows Server to access files stored on a non-Windows NFS server.
