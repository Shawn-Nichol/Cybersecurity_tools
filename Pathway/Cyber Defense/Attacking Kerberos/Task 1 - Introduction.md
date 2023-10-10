This will cover 
- Initial enumeration using tools like Kerbrute and RRubeus
- Kerberoasting
- AS-REP Roasting with Rebeus and Impacket
- Golden/Silver Ticket attacks
- Pass the Ticket
- Skeleton key attacks using mimikatz

## What is Kerberos
Kerberos is the default authentication service for MS domains. It is intended to be more secure than NTLM by using third party ticket authorization as well as stronger encryption. Even though NTLM has a lt more attack vectors to choose from Kerberos still has a handful of underlying vulnerabilities just like NTLM that we can use to our advantage. 

## Common Terminoloyg
- Ticket Granting Ticket (TGT): A ticket-granting ticket is an authentication ticket used to request service tickets from the TGS for specific resources from the domain.
- Key Distribution Center (KDC): The KDC is a service ofr issuing TGTs and service tickets that consist of the Authetnication Service and the Ticket Granting Service
- Authentciation Service (AS): The Authentication Service issues TGTs to be used by the TGS in the domain to request access to other machiens and service tickets
- Ticket Granting Service (TGS): The ticket Granting Service takes the TGT and returns a ticket to a machine on the domian.
- Service rpincipal Name (SPN) A service RPincipal Name is an identifier given to a service instance to associate a service instance with a domain service account. Windows requires that services have a domain service account which is why a service needs an SPN set.
- KDC Long Term Secret Key (KDC LT Key): The KDC key is based on the KRBTTGT service account. I t is used to encrypt the TGT and sign the PAC
- Client Long Term Secret Key (Client LT key): The client key is based on the computer or service account. It is used to check the encrypted timestamp and encrypt the session key.
- Service Long Term Secret Key (Service LT Key): The service key is based on the cmoputer or service account. It is used to check the encrypted timestamp and encrypt the session key
- Service Long Term Secret Key  (Service LT Key): The service key is based on the service account. It is used to encrypt the service portion of the service ticket and sign the PAC.
- Session Key: Issued by the KDC when a TGT is issued. The user will provide the session key to the KDC along with the TGT when requesting a service ticket.
- Privilege Attribute Certificate (PAC): The PAC holds all the of the user's relevant information, it is sent along with the TGT to the KDC to be signed by the Target LT key and the KDC LT key in order to validate the user.

## AS_REQ w/ Pre-Authentication in Detail
The AS-REQ step in kerberos authentication starts when a user requests a TGT from the KDC. IN order to validate the user and create a TGT for the user, the KDC must follow these exact steps. THe first step is for the user to encrypt a timestamp NT hash and send it to the AS. The KDC attempts to decrypt the timestamp using the NT hash from the user, if successful the KDC will issue a TGT as well as a session key for the user. 

## TGT contents
TGT is provided by the user to the KDC , in areturn, the KDC validates the TGT and returns a service ticket. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/6b3b75d0-41a3-4493-82d3-da969e741f60)

## Servic3e Ticket Content
A service ticket contains two portions: the service portion and the user-provided portion. 
- Service Portion: User Details, Session, Key, Encrypts the ticket with the service account NTLM hash.
- User Portio: Validity Timestamp, Session Key, Encrypts with the TGT session key.

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/c7bed18b-bfec-4f0d-af86-af6672f3af4b)


## Kerberos Authwentication Overview

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/d9c058d4-f48a-49c7-82ae-571e3bcdf339)

AS-REQ 1) The client requests an Authentication Ticket or Ticket Granting Ticket
AS-REP 2) The KDC verifies the client and sends back an encrypted TGT. 
TGS-REQ 3) THe client sends the encrypted TGT to the TGS with the SPN of the service the client wants to access. 
TGS-REP 4) The KDC verifies the TGT of tthe user and that the user has access to the service, then sends a vvalid session key for th eservice to the client. 
AP-REQ 5) The client requests the service and sends the valid session key to prove the user has access. 
AP-REP 6) The service grants access

## Kerberos Tickets Overview
The main ticket that you will see is a TGT these can come in various forms such as a .kirbi for Rebeus .ccache for Impacket. THe main ticket that you will see is a kirbi ticket. A ticket is typically base64 encoded and can be used for various attacks. The ticket-granting ticket is only used with the KDC in order to get service tickets. Once you give th TGT the server then gets the User details, session key, and then encrypts the ticket with the service account NTLM hash. Your TGT then give sthe encrypted timestamp, seesion key, and the encrytped TGT. The KDC will then authentciat the TGT and give back a service ticket for the requested service. A normal TGT will only work with that given service account that is connected to it however a KRBTGRT allows you to get any service ticket that you want tallowing you to access anything on the domain that you want.

## ATtack Privilege Requirements
- Kerbrute Enumeration - No domain access required
- Pass the Ticket -Access as a user to the domain required.
- Kerberoasting - Access as any user required
- AS-REP Reoasting -Accesss as any user required
- Golden Ticket - Full doamin compromise required.
- Silver Ticket -Service hash required.
- Skeleton Key - Full domain comparomise required.

Quesiton
What does TGT Stand for?
Answer: Ticket Granting Ticket

Question
What does SPN stand for?
Answer: Service Principal Name

Question
What does PAC stand for
Answer: Privilege Attribute Certificate

Question
What two services make up the KDC?
Answer: AS, TGS










