## Task 3 Active Directory
The core of any Windows Domain is the AD Domain Service (AD DS). This service acts as a catalog that holds the information of all of the objects that exist on your network. Amongst the many objects supported by AD, we have users, groups, machines, printers, shares, and many others. 

** Users **
Users are known as security principals, meaning that the domain can authenticate them and can be assigned privileges over resources like files or printers.

Users can be used to represent two types of entities 
- People: users will generally represent two types of entities
- Services: Every service requires a user to run, but service users are different from regular users as they will only have the privileges needed to run their specific service.

** Machines **
Machines are a type of object; for every computer that joins the domain, a machine object will be created. Machines are also considered security principles and are assigned an account just as any regular user. This account has somewhat limited  rights within the domain itself. 

Machine accounts can be identified by the computer name followed by a dollar sign. EX DC01 will have a machine account of DC01$.

** Security Groups **
you can define user groups to assign access rights to files or other resources to entire groups instead of single users. This allows for better manageability as you can add users to an existing group, and they will automatically inherit all of the group's privileges. Security groups are also considered security principals and, therefore can have privileges over resources on the network. 

Several groups are created by default.
- Domain Admins: users have admin privileges over the entire domain. By default, they can administer any computer on the domain, including the DCs.
- Server Operator: Users in this group can administer DC. They cannot change any administrative group memberships
- Backup Operators: Users are allowed to access any file, ignoring their permissions. They are used to perform backups of data on computers.
- Account Operators: Users in this group can create or modify other accounts in the domain
- Domain Users: Includes all existing user accounts in the domain
- Domain computers: Includes all existing computers in the domain.
- Domain Controllers: Includes all the existing DCs on the domain.

A complete list of security groups can be obtained from the [MS documents.](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/understand-security-groups)

To configure users, groups, or machines in AD, log in to the DC and run AD from the start menu. 

Organization Units (OU): All you need to classify users and machines. OU is mainly used to define sets of users with similar policing requirements. The people in the sales department of your organization are likely to have a different set of policies applied than the people in IT. 

Default containers
- Builtin: Contains default groups available to any Windows host.
- Computers: Any machine joining the network will be put here by default. You can move them if needed
- Domain Controllers: Default OU that contains the DCs in your network.
- Users: Default users and groups that apply to a domain-wide context.
- Managed Service Accounts: Holds accounts used by services in your Windows domain.

** Security groups vs OU
- OU is handy for applying policies to users and computers, which include specific configurations that pertain to sets of users depending on their particular role in the  enterprise. Remember, a user can only be a member of a single OU at a time, as it wouldn't make sense to try to apply two different sets of policies to a single user.
- Security Groups, on the other hand, are used to grant permissions over resources.


Question: Which group normally administrates all computers and resources in a domain?
Answer: Domain Admins

Question: What would be the name of the machine account associated with a machine named TOM-PC?
Answer: TOM-PC$

Question: 
Suppose our company creates a new department for Quality Assurance. What type of containers should we use to group all Quality Assurance users so that policies can be applied consistently to them?
Answer: Organization Units
