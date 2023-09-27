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
