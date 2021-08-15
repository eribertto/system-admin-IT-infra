One communication service that you're
almost guaranteed to use today is email. We use email for
a wide range of communication. In an enterprise setting, it's important
for a sysadmin, or a sole IT support specialist, to be able to configure
email services for the company. To do this,
you need to have a domain name set up for your company that you can use as your
email domain, like devan@example.com. When you send or receive email,
you want to use this email address. There are two ways to set up email for
a company. The first is to run your
own managed server. Using this option, you set up the email
service software on a server, then you create a DNS record for
your mail server. There are different DNS records. Remember that the A record is used for
hostnames, but for email servers we use MX,
for the mail exchange record. Email server setup can be one of the most
complicated service to setup for a sysadmin. You have to get the email
to actually work, protect your email addresses from spam,
filter out viruses and more. If you'd like to learn more about
setting up an email server, check out the next reading. An alternative approach to setting
up your own email service is to use an email service provider,
like Google Suite. These service providers allow
you to create email inboxes and more by paying a monthly fee for
every user in your organization. This ties you into the Gmail webmail
client, and allows you to access your email from anywhere, as long as
you're connected to the Internet. Whatever option you choose, you'll have to
understand the differences between email protocols when you setup
your email accounts. There are lots of email protocols out
there, but we'll only do a rundown of the more common ones you'll hear about,
POP3, IMAP, and SMTP. Post Office Protocol, or POP version 3,
is an email protocol that downloads email from an email
server onto your local device. It then deletes the email
from the email server. If you want to retrieve
your email through POP3, you can only view it from one device. There are a few reasons why you might
want to use POP3 to get your email. If you need to keep your email
storage under a certain quota, POP3 is a good way to maintain
that storage limitation. Another benefit of POP3 is privacy. Your email can only be seen
from your local device. If storage limitations and
security are a concern for you, you might want to consider
using POP3 over something like IMAP. Speaking of IMAP, or
internet message access protocol, allows you to download emails from your
email server onto multiple devices. It keeps your messages
on the email server. This email protocol is one of the more
popular ways to retrieve email. Last up is simple mail transfer protocol,
or SMTP, which is a protocol used for
sending emails. While POP3 and IMAP and other protocols
can be used to retrieve email, there's only really one email protocol for
sending email, SMTP. So there are lots of different email
protocols that can be implemented, depending on the email
software of you choose. You can read more about them
in the supplemental reading. Email service is critical for
any organization. Companies needs to be able to contact
clients and business partners and communicate internally. If you work in an IT support specialist
role, where you're handling system administration tasks, you will need to
weigh the pros and cons of a dedicated email server or a cloud email service,
decisions, decisions, decisions.