Three specific protocols are involved to facilitate the outgoing and incoming email messages, which are briefly listed below. 
- SMTP: It is utilized to handle the sending of emails.
- POP3: is responsible for transferring email between a client and a mail server.
- IMAP: Is responsible for transferring email between a client and a mail server.

POP3: 
- Emails are downloaded and stored on a single device
- Sent messages are stored on the single device from which the email was sent.
- Emails can only be accessed from the single device the emails were downloaded to.
- If you want to keep messages on the server, make sure the setting "Keep email on server" is enabled; all messages are deleted from the server once downloaded to the single device's app or software.

IMAP:
- Emails are stored on the server and can be downloaded to multiple devices.
- Sent messages are stored on the server.
- Messages can be synced and accessed across multiple devices.


## Email Headers
There are two parts to an email. 
- Header: information about the email, such as the email servers that relayed the email.
- Body: Text and or HTML formatted text

The syntax for email messages is known as the IMF (Internet Message Format)

What to look for when analyzing an email header.
- From the sender's email address
- Subject: The email subject line
- Date: the date when the email was sent
- To the recipient's email address

Another method to obtain the email header information is to view the raw or original data. 


<a href="https://mediatemple.zendesk.com/hc/en-us/articles/204644060-how-do-i-view-email-headers-for-a-message">How to read raw email data. </a>

Fields of interest: 
1. X-Originating-IP: The IP address of the email was sent from
2. SMTP.maliform/header.From: The domain the email was sent from
3. Reply-TO: This is the email address a reply email will be sent to instead of the email address.

<a href="https://mediatemple.zendesk.com/hc/en-us/articles/204643950-understanding-an-email-header"></a>


## Types of phishing
- SPAM: unsolicited junk emails sent out in bulk to a large number of recipients.
- Phishing: emails sent to a target pretending to be from a trusted entity to lure individuals into providing sensitive information
- Spear Phishing: takes phishing a step further by targeting specific individuals or organizations seeking sensitive information
- Whaling: targes specifically high positions, like CEO
- Smishing: takes phishing to mobile devices by targeting users with specially crafted text messages.
- Vishing: is similar to smishing, but instead of using text messages for social engineering attacks, the attacks are based on voice calls.

Typically Characteristics of phishing emails
- Sender email name/address will masquerade as a trusted entity.
- Subject line and or body is written with a sense of urgency or uses certain keywords such as Invoice, Suspended
- Body is designed to match a trusting entity
- Body is poorly formatted or written
- Body uses generic content, such as Dear Sir/Madam
- Hyperlinks use URL shortening services to hide their true origin
- Malicious attachment posing as a legitimate document.

  Hyperlinks should be defanged to prevent accidental clicking. 

