Managing Active Directory isn't just a big topic, it's a huge topic. There are
system administrators who spend all their time just managing AD. We're going to
spend some time showing you some of the most common tasks that a sysadmin would
need to do in an Active Directory environment. When an Active Directory domain
is first set up, it contains a default user account, administrator, and several
default user groups. Let's do a rundown of the most important groups. So, I want
to first get into my Active Directory window. And as you can see, I'm an
example.com. I'll run through the users. Domain admins are the administrators of
the Active Directory domain. The Administrator account is the only member of
this group in a new domain. Remember, how a local administrator or root on a
computer is able to make any changes they want to the operating system. Users in
the Domain Admins group can make any changes they want to the domain. Since a
domain can control the configuration of all of the computers that are bound to
it, domain admins can become local administrators of all of those machines too.
This is a huge amount of power and responsibility. So don't add accounts to this
group lightly. Enterprise Admins are administrators of the Active Directory
domain. They also have a permission to make changes to the domain that affect
other domains in multi-domain forest. The administrator account is the only
member of this group in a new domain. Enterprise Admin accounts should only be
needed on a very occasion like when Active Directory Forest is being upgraded to
a new version. Domain Users is a group that contains every user account in the
domain. If you want to give access to a network resource to everyone in the
domain, you don't need to grant access to every individual account. You can use
to Domain Users. Each computer that's joined to the domain has an account too.
So, we have a default group for them also. Domain Computers contains all
computers joined to the domain except domain controllers. Domain Controllers
contains all domain controllers in the domain. I'm going to be able to do
everything in this lesson because I'll be playing the role of a domain admin in
my example organization. As a systems administrator, or IT support specialist,
you might also be a domain admin or enterprise admin because of the power they
give you to make changes in Active Directory. You should never use a domain
admin account as your day to day user account. It's too easy to make a mistake
that affects the entire organization. Domain admin accounts should only be used
when you deliberately making changes to Active Directory. Got it? Your normal
user account should be very much like other user accounts in the domain, where
your permissions are restricted just to those resources that you need to have
access to all the time. If there are some administrative tasks that you need to
perform a lot as a part of your day to day job but you don't need to have broad
access to make changes in AD, then delegation is for you. Just like you can set
NTFS DACLs to give accounts permission in the file system. You can set up ACLs
on Active Directory objects. If you'd like to learn more about this, more
advanced topic, check out the next reading. Let's start administering Active
Directory. First up, we'll take a look at user account administration.