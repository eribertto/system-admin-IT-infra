Welcome back. In this lesson, we'll learn more about Active Directory, or AD,
the native directory service for Microsoft Windows. Active Directory has been
used to centrally manage networks of computers since it was introduced with
Windows Server 2000. If there are computers running Windows in your organization
then AD probably plays a huge role. Active Directory works in a similar fashion
to open LDAP. It actually knows how to speak the LDAP protocol and can
interoperate with LINUX, OS X, and other non-Windows hosts using that protocol.
When you use Active Directory to manage a fleet of Windows servers and client
machines, it does a lot more then just provide directory services and
centralized authentication. It also becomes the central repository of group
policy objects, or GPOs, which are ways to manage the configuration of Windows
machines. We'll show you how to do this later in this lesson. Now let's take a
look at a typical Active Directory domain and see what it contains. Active
Directory Administration relies on a whole suite of tools and utilities. We're
going to use a tool called the Active Directory Administrative Center, or ADAC.
ADAC is a tool that we'll use for lots of the everyday tasks that you'll learn
in this course. It's great for getting work done, and for learning how things
work behind the scenes, as you'll see. Remember that, much like file systems,
directory services are hierarchical. Everything that you see in Active Directory
is an object. Some objects are containers, which can contain other objects.
Several of the default containers are just called containers, and they serve as
default locations for certain types of objects. Another type of container is
called an organizational unit, or OU, which we talked about in an earlier
lesson. You can think of an OU like a folder or a directory for organizing
objects within a centralized management system. Ordinary containers can't
contain other containers, but OUs can contain other OUs. That's a little
confusing, so to show you the hierarchical structure of AD better, I've clicked
this button of the left-hand pane to switch ADAC to tree view. There are lots of
things listed here. ADAC tells us what kind of object each of these are and
gives us a description for some of them. We're not going to work with all of
these, but we want to call out some parts of the directory that are more common
to work with. The very first node in this tree is our domain. A domain will have
a short name like example, and a DNS name like example.com. Objects,
particularly computers in the domain, will be given a DNS name that lives in the
domain's DNS zone. There's actually one level of hierarchy above a domain that
we don't see in this tool, and that's a Forest. If you look at the logical shape
of a domain, it looks like a tree, so the name even makes sense. A forest
contains one or more domains. Accounts can share resources between domains in
the same forest. In our example environment, example.com is the only domain in
the forest. The next example that we'll look at is computers. This container is
where new AD computer accounts are created. So if I go here, you can see my
computers. Computer accounts are created when a computer is joined to the AD
domain. The next thing that we'll look at is domain controllers. This container
is where domain controllers are created by default. Next we'll look at users.
This container is where new AD users and groups are created by default. The
service that hosts copies of the Active Directory database are called domain
controllers, or DCs. Domain controllers provide several services on the network.
They host a replica of the Active Directory database and group policy objects.
DCs also serve as DNS servers to provide name resolution and service discovery
to clients. They provide central authentication through a network security
protocol called Kerberos. As I mentioned, we'll talk more about Kerberos in the
IT security course. For now, what you should understand is that domain
controllers get to decide when computers and users can log onto the domain. They
also get to decide whether or not they have access to shared resources like file
systems and printers. This allows system administrators to make changes to the
network really quickly and easily. If someone new joins the organization, sys
admins can create a user account for them, and almost immediately every device
in the network knows who that person is. If someone changes jobs in the org or
leaves, a sys admin can disable or delete their account, and within seconds,
their access to devices adjust. It's common for most domain controllers in the
Active Directory network to be the read-write replicas. This means that each
have a complete copy of the AD database and are able to make changes to it.
Those changes are then replicated to all other copies of the data basis on other
DCs. Replication is usually quick and the last change wins in almost all cases.
This isn't perfect, but it works for most tasks. Some changes to the AD database
can only be safely made by one DC at a time. We task those changes to a single
domain controller by granting it a flexible single-master operations, or also
known as FSMO role. We won't go into depth here on the nitty gritty details
around what each of these FSMO roles are responsible for and how they operate,
but you can check out the next reading for more. If your job will involve domain
control and management, you'll need to understand how to assign FSMO roles and
recover from DC failure. In order for computers to take advantage of the
essential authentication services of AD, they have to be joined or bound to
Active Directory. Joining a computer to Active Directory means two things. The
first is that AD knows about the computer and has provisioned a computer account
for it. The second is that the computer knows about the Active Directory domain
and authenticates with it. From that point forward, the computer can
authenticate to Active Directory just as any user who log onto the computers are
able too.