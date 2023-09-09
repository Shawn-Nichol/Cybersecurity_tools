## Preventive measures
- Email Security (SPF, DKIM, DMARC)
- SPAM Filters
- Email Labels (alert users that an incoming email is from an outside source)
- Email Address/Domain/URL Blocking (Based on reputation or explicit denylist)
- Attachment Blocking (Based on the extension of the attachment0
- Attachment  Sandboxing (detonating email attachments in a sandbox environment to detect malicious activity)
- Security Awareness Training

## SPF (Sender Policy Framework)
SPF is used to authenticate the sender of an email. With an SPF record in place, ISPs can verify that a mail server is authorized to send email to a specific domain. An SPF record is a DNS TXT record containing a list of the IP addresses that are allowed to send email on behalf of your domain. 

![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/a4252547-ec4c-4791-881a-6c45215e5e52)

SPF record looks like 
```
v=spf1 ip4:127.0.0.1 include:_spf.google.com -all
```
- v=spf1: This is the start of the SPF record
- ip4: 127.0.0.1: This specifies which IP can send mail.
- include:_spf.google.com: This specifies which domain can send mail
- -all: non-authorized emails will be rejected.

<a href="https://dmarcian.com/spf-syntax-table/">SPF syntax</a>

## DKIM DomainKeys Identified Mail
It is used for the authentication of an email that's being sent. Like SPF, DKIM is an open email authentication standard used for DMARC alignment. A DKIM record exists in the DNS but is a bit more complicated than SPF. DKIM's advantage is that it can survive forwarding, which makes it superior to SPF and a foundation for securing your email. 

```
v=DKIM1; k=rsa; p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAxTQIC7vZAHHZ7WVv/5x/qH1RAgMQI+y6Xtsn73rWOgeBQjHKbmIEIlgrebyWWFCXjmzIP0NYJrGehenmPWK5bF/TRDstbM8uVQCUWpoRAHzuhIxPSYW6k/w2+HdCECF2gnGmmw1cT6nHjfCyKGsM0On0HDvxP8I5YQIIlzNigP32n1hVnQP+UuInj0wLIdOBIWkHdnFewzGK2+qjF2wmEjx+vqHDnxdUTay5DfTGaqgA9AKjgXNjLEbKlEWvy0tj7UzQRHd24a5+2x/R4Pc7PF/y6OxAwYBZnEPO0sJwio4uqL9CYZcvaHGCLOIMwQmNTPMKGC9nt3PSjujfHUBX3wIDAQAB
```

- v=DKIM1: This is the version of the DKIM record.
- k=rsa: This is the key type. The default value is RSA. RSA is an encryption algorithm
- p=: This is the public key that will be matched to the private key created during the DKIM setup process.

Think of DKIM as a watermark for your email.


## DMARC (Domain-Based Message Authentication, Reporting, and Conformance)
An open-source standard uses a concept called alignment to tie the result of two other open-source standards, SPF and DKIM, to the content of an email. If not already developed, putting a DMARC record into place for your domain will give you feedback that will allow you to troubleshoot your SPF and DKIM configurations if needed. 

DMARC looks like
```
v=DMARC1; p=quarantine; rua=mailto:postmaster@website.com 
```

v=DMARC1: Must be in all caps,
p=quarantine: If a check fails, then an email will be sent to the spam folder
rua=mailto:postmaster@wwebsite.com: Aggregate reports will be sent to this email address. 

<a href="https://dmarcian.com/domain-checker/">Domain Checker</a>

## S/MIME
Secure/Multipurpose Internet Mail Extensions
It is a widely accepted protocol for sending digitally signed and encrypted messages.


![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/ebaf2b10-3941-4404-95f5-fff7bc1b0348)

## SMTP 
