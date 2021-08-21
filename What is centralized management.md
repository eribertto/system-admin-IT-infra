The job of the systems administrator is to, well, administer systems. Sysadmins
have a set of systems they're responsible for. And they have to manage those
systems so they're available to serve their function to the organization. For
example, as a sysadmin, I might be responsible for making sure that all of the
servers in my network are kept up to date with security patches and application
updates. Should I go around and log into each server, checking each one at a
time? What if I need to manage user accounts on end user devices? Should I go to
each employee's desk and set their account up that way? I guess I could, but
that would be super time-consuming, and probably inconsistent. Instead, what I
want to do is use centralized management, a central service that provides
instructions to all of the different parts of my IT infrastructure. Directory
services are one of these services. Remember in earlier lessons when you created
accounts and gave them access to resources on your computer? Imagine that you
worked for an organization that has dozens, hundreds, or even thousands of
computers and people who use them. You can't possibly go into each of those
computers to set them up. Directory services provides centralized
authentication, authorization, and accounting, also known as AAA. When computers
and applications are configured to use directory services, or AAA services,
decisions about granting or denying access to computers, file systems, and other
IT resources are now centralized. Now you can create a user account once, and
it's available for the entire network at once. Easy, well, sort of. You will
learn a lot more about AAA services in an upcoming course. For now you should
understand that your directory service will be responsible for granting or
denying access to computers, file systems, and other IT resources. Now let's go
one step further. Let's say you have a network file system that you need to give
everyone in the IT department access to. You could set up the network share,
then give it a list of user accounts to grant access to the share. But what
happens when someone new joins the IT department? What about when someone
leaves? Instead of granting access based on who you are, what if you granted
access based on what you do? In most organizations, access to computer and
network resources is based on your role in the organization. When you manage
access to resources on a computer and on the network, you'll often grant and
deny access based on user groups. User groups can be used to organize user
accounts in all sorts of ways. You might create groups of buildings that people
work out of, or the person's role in the organization, or really almost anything
else. What's important is that you use groups to organize accounts based on the
way that you'll manage them. If you are a systems administrator, then you might
have permission to do things like creating user accounts and resetting
passwords. You are allowed to do that because of your role as a systems
administrator. If you add another systems administrator to your organization,
you don't want to have to find out all of the things that a sysadmin should have
access to, then grant them individual account access to each of those resources.
That would just take forever. Instead, we'll create a group of sysadmins and add
all system administrators to that group. Then we can give the systems
administrators' group access to any resources they need. If you or another
person change roles in the company, then all you have to do is change the groups
that you are a part of, not the rights that you have to directly access
resources. We call this role-based access control, or RBAC. Controlling access
to resources isn't all you can do. You can also centralize configuration
management. Just like you don't want to run around to every computer to
configure user accounts, you wouldn't want to do that to setup printers,
configure software, or mount network file systems. By centralizing the
configuration management of your computers and software, you can create rules
about how things should work in your organization. There are many ways to
centralize your configuration management. And an easy way to get started is with
as simple a tool as logon scripts that run each time someone logs on to a
computer. Later in this module, we'll look at Active Directory and its group
policy objects, which are a way to manage the configuration of Windows machines.
There are also dedicated configuration management frameworks, like Chef, Puppet
or SCCM, that can be used for super simple or super powerful configuration
management. These are outside the scope of this module, so check out the
supplemental reading right after this video for more information.