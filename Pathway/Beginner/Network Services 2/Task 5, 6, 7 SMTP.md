## What is SMTP
Simple Mail transfer protocol

SMTP server performs three basic functions
- It verifies who is sending emails through the SMTP server
- It sends the outgoing mail
- If the outgoing mail can't be delivered, it returns the message to the sender. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/86567dfe-b1e0-497f-99d8-beaca47500af)

1. Mail user agent, which is either your email client or an external program. Connects to the SMTP server of your domain. This initiates the SMTP handshake. This connection works over the SMTP port, which is usually 25. The SMTP session starts once these connections have been made and validated.

2. Sending mail. The client first submits the sender, the recipient's email address, the body of the email, and any attachments to the server.

3. The SMTP server then checks whether the domain name of the recipient and the sender is the same.

4. The sender's SMTP server will connect to the recipient's SMTP server before relaying the email. If the recipient's server can't be accessed or is not available, the email gets put into an SMTP queue.

5. The recipient's SMTP server will verify the incoming email. It does this by checking if the domain and user name have been recognized. The server will then forward the email to the POP or IMAP server.

6. The E-mail will then show up in the recipient's inbox.

Question: What does SMTP stand for?
Answer: Simple Mail Transfer Protocol

Question: What does SMTP handle the sending of?
Answer: Emails

Question: What is the first step in the SMTP process?
Answer: SMTP Handshake

Question: What is the default SMTP port?
Answer: 25

Question Where does the SMTP server send the email if the recipient's server  is not available?
Answer: SMTP queue

Question: On what server does the Email ultimately end up on?
Answer: pop/imap

Question: Can a Linux machine run an SMTP server?
Answer: Y

Question: Can a Windows machine run an SMTP server?
Answer: Y

## Enumerating SMTP
