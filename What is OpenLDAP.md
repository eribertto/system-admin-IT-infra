In the last lesson you dove headfirst into the popular directory service Active
Directory. You learned how to add users, password, groups and even modify access
level for groups, using group policies. Another popular directory service that's
used today is the free and open source service OpenLDAP. OpenLDAP, which stands
for lightweight directory access protocol operates very similar to Active
Directory. Using LDAP notation or LDAP data interchange format, or LDIF, you can
authenticate, add, remove users, groups, computers and so on in a directory
service. OpenLDAP can be used on any operating system, including Linux, macOS,
even Microsoft Windows. However, since Active Directory is Microsoft's propriety
software for directory services, we recommend that you use that on Windows
instead of OpenLDAP. But its helpful to know that OpenLDAP is open source so it
can be used on a variety of platforms. There are a few ways you can interact
with an OpenLDAP directory. First, you can use the command-line interface and
passing commands to create and manage directory entries. You can also use a tool
like phpLDAPadmin, which offers you a web interface that you can use to manage
your directory data, much like the Windows Active Directory GUI that you're
familiar with. You can read more about how to set up OpenLDAP and phpLDAPadmin
in the next reading. In this lesson we'll give you a high level overview of the
operations you can do in OpenLDAP via commands and how they work. To begin we'll
just open the OpenLDAP package using this command. I'm going to get into my
Linux environment and type up this command. Sudo apt-get install slapd
ldap-utils. Put my password in and accept. Once you install the packages it'll
prompt you enter in an administrative password for LDAP. So let's go ahead and
do that. And then hit Ok. Then confirm your password, then hit Ok. Now that it's
installed we're actually going to reconfigure the slapd package so that we can
fine tune our setting. To do that we're going to run the following command. I'm
going to clear my window, and then run sudo dpkg-reconfigure slapd. This is
going to ask us a bunch of questions about our new setup. We won't answer all of
these options, but you can learn more about them in, you've guessed it, the
supplemental reading. For now let's just fill out the settings with these
values. So the first option is Omit OpenLDAP server configuration? I'm going to
go ahead and say No. Next, DNS domain name, is similar to Windows AD, this is
our organization domain. Let's use example.com. And then hit Ok. Organization
name, let's use example. Administrator password, let's do the same thing that we
entered before. For the database let's use MBD. Do you want the database to be
removed when slapd is purged? Let's go ahead and say No. Then it's asking us if
we would like to move old database. We're going to say Yes for now. And then
it'll say, Allow LDAP version 2 protocol? I'm going to say No. That's it, now
you have a running OpenLDAP server. We're really cooking now. Let's keep going.