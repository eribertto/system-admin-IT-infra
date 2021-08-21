If were around when phone books were used, you might remember that these big old
books contained the names, addresses, and phone numbers of people in your
neighborhood or community, who wanted the information to be publicly listed.
This is way different from the phone book or contact list you have in your
mobile phone. The people who are in your contacts directory gave you their phone
numbers for your use only. When using LDAP, there are different authentication
levels that can be used to restrict access to certain directories, similar to
those big public phone directories or those private mobile phone directories.
Maybe you have a directory that you want to make public so anyone can read the
entries in the directory or maybe you just want to keep that data private to
only those who need it. We'll discuss how LDAP does this authentication and what
methods it uses. We talked about the different operations you can do with LDAP,
like add, remove or modify entries in a directory. Another operation that you
can perform is the Bind operation, which authenticates clients to the directory
server. Let's say you want to log in to a website that uses a directory service.
You enter your account login information and password, your information is then
sent back to the website. It will use LDAP to check if that user account is a
user at the directory and that the password is valid. If it's valid, then you
will be granted access into that account. You want your data to be protected and
encrypted when it's completing this process. There are three common ways to
authenticate. The first is anonymous, then simple, and the last is SASL, or
simple authentication and security layer. When using anonymous binding, you
aren't actually authenticating at all, depending on how it's configured anyone
could potentially access that directory, just like our public phone book
example. When you use simple authentication you just need the directory entry
name and password, this is usually sent in plain text, meaning it's not secure
at all. Another authentication method that's commonly used is SASL
authentication. This method can employ the help of security protocols like TLS,
which we've already learned about in Kerberos, which we'll discuss in a minute.
SASL authentication requires the client and the directory server to authenticate
using some method. One of the most common methods for this authentication is
using Kerberos. Kerberos is a network authentication protocol that is used to
authenticate user identity, secure the transfer of user credentials, and more.
Kerberos by itself can be a complex topic that we'll revisit in the IT security
course. If you want to learn more about Kerberos right now, you can check out at
the supplemental reading right after this lesson. Once the client has
successfully authenticated with LDAP server or directory service, the user will
be authorized to use whatever access levels they have. In the next few lessons
we're going to dive deeper into two of the most popular directory services that
use LDAP, Active Directory and OpenLDAP.