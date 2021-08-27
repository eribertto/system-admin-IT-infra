It's easy to manage OpenLDAP through a web browser and tool like phpLDAPadmin,
but you can also use command line tools to achieve the same result. I'd
recommend you look into setting up PHPLDAPadmin, if this is your first set up
with open LDPA. For instructions about how to set up a PHPLDAPadmin, check out
the supplementary readings. In this lesson, we're going to quickly run down a
few other commands that will allow you to add, modify and remove entries in your
directory. To begin using command line tools, you need to use something known as
LDIF files, pronounced LDIF. We've already seen LDIF format or LDAP notation in
action. It's just a text file that lists attributes and values that describe
something. Here's a simple example of an LDIF file for a user. Even without
understanding what the syntax of this file is saying, we can infer that it's
talking about an employee named Cindy who works in the Engineering department at
the company example.com. We've talked a little bit what the attributes are
referring to in an earlier lesson. But you can refer to the supplemental reading
if you want to know what the specific fields mean. For our purposes here,
though, we just want to see a high level overview of how this works. Once you've
written your LDIF files, you're practically done. Depending on what task you
want to do to your directory, you'd run commands like these. Ldapadd, this takes
the input of an LDIF file, and adds the context of the files. ldapmodify, as you
can guess, this modifies an existing object. ldapdelete, this will remove the
object that the LDIF file refers to. ldapsearch, this will search for entries in
your directory database. It's not important to note the syntax of these
commands, you can always look up a syntax on official documentation. But as you
can see, it's not scary to work with OpenLDAP. It operates in a very similar way
to Windows Active Directory, or AD. You can take this knowledge and populate
your directory just like you did in Windows AD. If you're curious about the
syntax of these commands, check out the supplemental reading on using LDIF files
and LDAP commands. Again, if you're considering LDAP as your solution to your
directory service needs, I'd recommend looking into the web manager tool PHPLDAP
admin that we've included a link to in the next reading. Just like Windows AD,
this topic can be pretty extensive. So think about which directory solution best
fits the IT needs for your organization. There are lots of reasons why you might
want to deploy the help of a directory service like OpenLDAP or Active Directory
when working in a systems administration role. Directory services are great for
centralized authentication, keeping track of where computers are in your
organization, who can access them and more. Make sure to play around and
familiarize with OpenLDAP or PHLDAP admin to get a better sense of how these
directory services work. Checking out the official documentation is always a
good place to start. By now, if you've learned about all the essential IT
infrastructure services. The next topic we'll shift to is how to make sure all
the hard work you've put in to your IT infrastructure doesn't go to waste by
learning about disaster recovery and backups. Your hard work is really paying
off, high five to that. Now take a moment to complete the quiz we put together
for you, then we'll meet you back in the next video.