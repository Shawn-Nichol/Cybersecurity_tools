There are three specific protocols involvd to facilitate the outgoing and incomgin email messages, and they are briefly listed below. 
- SMTP: It is utilized to handle the sending of emails.
- POP3: is responsible for tarnsferring email between client and a mail server.
- IMAP: Is responsible for transfering email between a client and a mail server.

POP3: 
- Emails are downloaded and stored on a single device
- Sent messages are stored on the sngle device form which the email was sent.
- Emails can only be accessed from the single device the emails were downloaded to.
- If you want to keep messsages on the server, make sure the setting "Keep email on server" is enabled, all messages are deleted from the server once downloaded to the single device's app or software.

IMAP:
- Emails are stored on the server and can be downloaded to multiple devices.
- Sent messsages are stored on the server.
- Messages can be synced and accessed across multiple devices.


## Email Headers
There are two parts to an email. 
- Header: infromation about the email, such as the email servers that relayed the email.
- Body: Text and or HTML formatted text

The syntax for email messages is konwn as the IMF (Internet Message Format)

What to look for when analysing a email header.
- From: the sender's email address
- Subject: The emails subject line
- Date: the date when the email was sent
- To: the recipient's email address

Another method to obtain the email header infromation is to view the raw or orignal data. 


<a href="https://mediatemple.zendesk.com/hc/en-us/articles/204644060-how-do-i-view-email-headers-for-a-message">How to read raw email data. </a>

Fields of interest: 
1. X-Origniating-IP: The ip address of the email was sent from
2. SMTP.maliform/header.from: The domain the email was sent from
3. Reply-TO: This is the email addres a reply email will be sent to instead of the from email address.

<a href="https://mediatemple.zendesk.com/hc/en-us/articles/204643950-understanding-an-email-header"></a>


## Types of phising
- SPAM: unsolicited junk emails sent out in bulk to a large number or recipients.
- Phishing: emails sent to a target puporitng to be from a trusted entity to lure individulas into providing sensitive information
- Spear Phising: takes phising a step further by targeting a specific individulas or orgnaization seeking sensitive infromation
- Whaling: targes specificlly high positions, likes CEO
- Smishing: takes phising to mobile devices by targeting mobile users wit specially crafted text messages.
- Vishing: is similar to smishing, but instead of using text messages for social engineering attack, the attacks are based on voice calls.

Typicall Characteristics of phising emails
- Sender email name/address will masquerade as a trusted entitey.
- Subject line and or body is written with a sense of urgency or uses certain keywords such as Invoice, Suspended
- Body is designed to match a trusting entity
- Body is poorly formatted or written
- Body uses generic content, such as Dear Sir/Madam
- Hyperlinks  uses URL shortening services to hide its true orgin
- Malicious attachment posing as a legitimate document.

  Hyperlinks should be defanged to prevent acciendtly clicking. 

