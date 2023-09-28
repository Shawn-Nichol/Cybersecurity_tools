## Task 2 Windows domain
Domain Contoller: The server that runs the Active Directory service.
Active Directory: stores credentails
Main advantages
-  Centralised identity management: All users across the network can be confirrgured from Active Directory with minimum effort
-  Managing security policies: You can configure securtiy policies directly fromActive Directory and apply them to users and comptuers across the network as needed.

Question: In a windows domain, credentials are stored in a centralised repository called?
Answer: Active Directory 

Question: The server in charge of running theActive Directory services is called?
Answer: Domain Controller


## Task 3 Active Directory
The core of any Windows Domain is the AD Domain Service (AD DS). This service acts as a catalogue that holds the information of all of the objects that exist on your network. Amongst the many objects supported by AD, we have users, groups, machines, pritners, shares, and many others. 

** Users **
Users are known as security principals, meaning that they can be authenticated by the dmoain and can be assigne d privileges over resrouces like fiels or printers.

Users can be used to represent two types of entities 
- People: users will generally represent two types of entities
- Services: Every single service requires a user to run, but service users are differnet from regular users as they will only have the privileges needed to run their specfic service.

** Machines **
Machiens are a type of object, for every computer that joins the domain, a machine object will be created. Machines are also cnsidered security principles and are assigned an account just as any regular user. This account has somewhat limited  rights within the domain itself. 

Machine accounts can be identifyed by the computer name followed by a dollar sign. EX DC01 wil have a machine account DC01$

** Security Groups **
you can define user groups to assign access rights to files or other resouces to entire groups instead of single users. This allows for better manageability as you can add users to an existing group, and they will automatically inherit all of the group's privilleges. Security groups are also considered security principals and therefor can have privileges over resources on the network. 

Several groups are created by default
- Domain Admins: users have admin privileges over the entire domain. By default, they can administer any compter on the domain including the DCs
- Server Operator: Users in this gorup can administer DC. They cannot change any adminsistrative group memeberships
- Backup Operators: USers are alloowed to access any file, ignoring their permissions. They are used to perfrom backups of data on computers.
- Account Operators: Users in this group can create or modify other accounts in the dmoain
- Domain Users: Includes all existing user accounts in the domain
- Domain computers: Includes all existing computers in the domain.
- Domain Controllers: INcludes all the existing DCs on the domain.

A complete list of security groups can be obtain from the [MS documents.](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/understand-security-groups)

To configure users, group or machiens in AD, you need to log in to the DC and run AD from the start menu. 

Organization Units (OU): All you to clssify users and machines. OU are mainly used to define sets of users with similar policing requirements. THe pople in the sales department of your organisation are likely to have a different set of policies applied than the poeple in IT. 

Default containers
- Builtin: Contains default groups available to any windows host
- Computers: Any machien joing the network will be put here by default. You can move them if needed
- Domain Controllers: Default OU that contains the DCs in your network.
- USers: Default users and groups that apply to a domain-wide context.
- Managed Service Accounts: Holds accounts used by services in your windows domain.

** Security groups vs OU
- OU are handy fo r applying policies to users and computers, which includ specific configurations that pertain to sets of users depending on teir particular role in the  enterprise. Remeber, a user can only be a member of a single OU at a time, as it wouldn't make snes to try to apply two different sets of policies to a single user.
- Security Groups, on the other hand, are used to grant permissions over resources.


Question: Which gorup normally administrates all computers and resources in a domain?
Answer: Domain Admins

Question: What would be the name of the machine account associated with aa machine named TOM-PC?
Answer: TOM-PC$

Question: 
Suppose our company creates a new department for Quality Assurance. What type of containers should we use to group all Quality Assurance users so that policies can be applied consistently to them?
Answer: Organization Units

## Task 4 Managing Users in AD
How to delete an OU, AD has a safety built in to prevent accidentally deleting OUs. To turn off this safety, go to View-> Advanced features, next right-click the OU select properties->Object and disable Protect object
from accidental deletion.

Delegation
You can give specific users com control over some OUs, to perfrom advanced tasks on OUs without needing a Domain Administrator to step in.

How to RDP to Windows computer from Linux install remmina
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/beca0304-fadc-453f-a3a4-6a723f3d8ce0)

Then enter the computer info, this will open up windows login screen where you can enter the user credentials. 
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/9ca75e9f-3030-4ce6-87dc-d7cdc1805809)



Question: What was the flag found on Sophie's desktop?
Step one RDP into the computer with phillip and perform the following password reset command in AD
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/8115fac7-6e6e-4650-906f-2fa47f59a2cc)

Note the password requirements can be found on DC in group policies. 
Select "Default Domain Policy" and work your way to the password policy. Computer Configuration -> Policies -> Windows Settings -> Security Settings -> Account Password Policy -> Password Policy
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/ff5bac1f-0d5c-4ef8-b9bc-765b76ead85a)

After setting the password, you'll be able to remote into Sophie's desktop with the newly reset password.

Answer: THM{thanks_for_contacting_support}

Question: The process of granting privileges to a user over some OU or other AD object is called? 
Answer: Delegation

## Task 5 Managin Computers in AD
By default all computers that join a domina will be put  in the contaier called "Computers"

Devices should be divide  into at least the following three groups.

** Work Stations**
Workstations are one of the most common devices within an AD. Each SUsers in the domain will likely be logging into a workstations. This is the device they will use to doe their work or nomral browsing activities. These devices should never have a priviledged user signed into them. 

** Servers **
Servers are the second most common device within an AD. Servers are generally used to provide services to users or other servers

** Domain Controllers
DC are the third most common device within an AD. DC allow you to manage the AD. These devices are often deemed the most sensitive devices within the network as they contain hashed passwords for all users accounts within the environemnt. 

Question: After organising the available computers, how many ended up in the Worstations OU?
Answer 7

Question: Is it recommendable to create separaate OUs for servers and workstations? (yay/nay)
Answer: yay

## Task 6 Group Policies
GPO Group Policy Objects are simply a collection of settings that can be applied to OUs. GPOs can contain policies aimed at either users or computers, allowing you to set a baseline on specific machiens and identities. 

GPO will apply to the linked OU and any subOUs under it. 

The first tab you see when selecting a GPO is scope, which is where the GPO is linked in the AD. </br>
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/6a82961f-23b8-420c-a22c-efd00a7c87f1)

You can also apply Security Filtering to GPOs so tahat  they are only applied to specific users/computesr under an OU. By default, they will apply to the Authenticated Users group, whcih includes all user/PCs.
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/d3d3a9d0-344c-4487-8147-3cfc8018dcc1)


The setting tab includes the actual contents of the GPO and lets us know what specific configurations it applies. As stated before each, GPO has configurattions that apply to computers only and configurations that apply to users only.
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/d657c768-c3e7-4e85-a840-b15f87194cf9)

GPOs are distributed to the network via a network share called **SYSVOL**, which is stored in teh DC. All users in a domain should typically have access to this share over the network to sync their GPOs periodically. The SYSVOL share points by default to the """C:\Windows\SYSVOL\sysvol\""" directory on each of the DCs in our network. 

Once a change is made, it could talk computers up to 2 hours to sync up. You can force updates with the following command in a termianl.
```
gpucpdate /force
```

Question: What is the name of the network share used to distriburte GPOs to domain machiens?
Answer: SYSVOL

Question: Can GPO be used to apply settting to users and computers?(yay/nay)
Answer: yay

## Task 7 Authentication Mehtods
All credentials are stored in the DC. Whenever a user tries to authenticate to a service using domain credentials, the service will need to ask the DC to verify if they are corect. Two protocols can be used for network authentication in windows domains

- Kerbos: Used by an recent versions of windows. This is the derfault protocol in any recent domain.
- NetNTLM: Legacy authentication protocol kept for compatibility purposes.

Kerbos
Step 1
The user sends their username and a timestamp encrypted using a key dervied from their password to the Key Distribution Center (KDC), a service suusually installed on the DC in charge of creating Kerberos tickets on the network. 

The KDC will create and send back a Ticket Granting Ticket (TGT), which will allow the user to request additional tickets to access specific services. The need for a ticket to get more tickets may sound a bit weird, but it allows users to request service tickets without passing their credentials every ttime they want to connect to a service. Along with the TGT, a Session Key is given to the user, which they will need to generate the follwoign request.
![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/ef19fa89-45a6-4106-908a-4a204aee3da3)

Step 2
When a user want to connect to a service on the newtork like a share, website or database, they will use their TGT to ask the KDC for a Ticket Granting SErvice(TGS). TGS are tickets that allow connection only oto specific service they were created for. TO request a TGS, the user will send tehir username and a timestamp encrypted using the Session Key, along with the TGT and a Service Principal Name (SPN), which indicates the service and server name we intend to access.

As a result, the KDC will send us a TGS along with a Service Session Key, which we will need to authenticate to the service we want to access. The TGS is encrypted using a key dervied from the Service OWner Hash. The service OWner is the user or machine account that the service runs under .. THE TGS contrain a copy of the service Sesion Key on its encrypted contents so that the Servie Owwner can access it by decryption the TGS

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/cb5c7f7f-ef16-4c29-ad1e-2d8d36058be8)

Step 3 
The TGS  can then be sent to the desired service to authenticate and establish a connection. The service  will use its confiured account's password hash to decrypt the TGS and validate the SAervice Seesion key. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/e01b3eb1-cc0e-48c0-a79b-44946780816a)


NetNTLM Authebnticaion

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/92b67752-0173-45e3-a15b-73e435017b68)

1. The client sends an authentnciation request to the server they want to access.
2. The server generates a readom number and sends it as a challenge to the client.
3. The client combines their NTLM password hash with the challenge to generate a response to the challenge and sends it back to the server for verfication.
4. The server forwards the challenge and the response to the DC for verfication
5. The domain contoller uses the challenge to recalculate the response and cmopares it to the orginal response sent by the client. If they both match, the client is authenticated; otherwise access is denied. The autentication result is sent back to the server.
6. The server forwards the authentciation result to the client.


Question:: Will current version of Windows use NetNTLM as the preferred authetnciation protocol by default
Answer: nay

Question: When referring to Kerberos, what type of tticket allows us to request further tickets known as TGS?
Answer: Ticket Granting Ticket

Question: When using NetwNTLM, is a user's password transmitted  over the network at any point?
Answer: nay

## task 8 Trees, Forests and Trusts
Domain can be split in subdomains for example if there was branch in the US and UK, you could build a tree with a root domain and then two subdomains, so you distributre unique OUs. 


![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/d3356401-abe9-4a76-9a0f-2e33058aa79c)

The union of several tress with different namespace into the same network is known as a forest. 


![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/c4597714-aabb-4d77-b55a-81c6e7d3d090)

**Trust Relationships**
Having a trust relationship between domains allows you to authoise a user from domain 1 to access resoucres from domain 2.


Question: What is a group of windows domains that share the same namesspace called?
Answer: tree

Quesiton: What should be configured between two domains for a user in Domain A to acces a resource in DOmain B?
Answer: A trust Relationship.

