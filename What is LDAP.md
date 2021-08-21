Before we jump into directory services, let's talk about the underlying protocol
that's used in directory services called LDAP or lightweight directory access
protocol. LDAP is used to access information in directory services like over a
network. Two of the most popular directory services that use LDAP are active
directory and openLDAP, which we'll talk about more in upcoming lessons. There
are a lot of different operations you can use in LDAP. You can add a new entry
in the directory server database like creating a new user objects called Cristi.
You can delete an entry in the directory server database. You can modify entries
and much, much more. When we say entry, we're reffering to the LDAP entry format
or LDAP notation for records in the directory service. An LDAP entry is just a
collection of information that's used to describe something. Take a look at this
example. Don't worry too much about what this says. The format of LDAP entry
basically has a unique entry name denoted by dn or distinguished name, then
attributes and values associated with that entry. So, CN is the common name of
the object. In this case, since it's a person, we use Devan Sri-Tharan as the
name. OU is the organizational unit such as a group. And in this case, Sysadmin
is used. DC is the main component. So example.com is split into example then
com. Again, it's not necessary to remember these attributes. You can reference
them in the next reading. The takeaway here is that LDAP notation is used for
entries in directory services to describe attributes using values.