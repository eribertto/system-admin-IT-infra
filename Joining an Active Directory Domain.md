If you have systems administrative responsibilities, you might be involved in
joining machines to the Active Directory domain. Remember from our introduction
to AD that computers can be joined or bound to Active Directory? Joining the
computer to Active Directory means two things: that AD knows about the computer
and has provisioned a computer account for it, and that computer knows about the
Active Directory domain and authenticates with it. Over here, I'm logged in to a
Windows computer that isn't joined to domain. This is called a workgroup
computer. The name comes from Windows workgroups which are a collection of
standalone computers that work together. Windows workgroups aren't centrally
administered so they become harder and harder to manage as the size of the
network grows. We want central administration and authentication in our network.
So let's join this computer to the domain. Let's look at the GUI for this first,
then PowerShell. So we'll go ahead and click Computer, then System Properties.
As you can see, this computer is under a workgroup. So what we need to do is we
need to join this machine to the domain. To do that, I'm going to go ahead and
click Change settings, click on Change. In the computer name and domain changes
window, you can see the computer can either be a member of the domain or
workgroup, but not both at the same time. So I'm going to go ahead and select
the domain right here. And I'm going to go ahead and enter our domain name which
is example.com. Now, when I click OK, this computer will reach out on the
network to find the domain controller for my AD domain. Once it finds a DC, I'll
be asked for a username and password to authorize the computer to be joined to
the domain. So I put in my domain admin, username, and password. Which I am
going to do right now. Voila, there you go. My machine is now joined to my
domain. The Domain Controller creates a computer account in the domain for this
computer, and this computer reconfigures itself to use AD authentication
services. This will require a reboot, so let's jump over to the Active Directory
administrative center to see what it looks like on that end. All right, so I'm
at my Active Directory window and I'll go ahead and click Computers. All right,
there it is. I can see my computer in the computer's container. Now, my new
computer will use this Active Directory domain for authentication and I can use
group policy to manage this machine. We can join computers to the domain from
PowerShell, too. I've got this computer over here that also needs to be joined
to the domain. So let's use the CLI this time. So I am going to go ahead and
type in AD computer and domain name, example.com, and server, connect to dcl.
That's nice and simple. Now, I'm prompted for my credentials again, which I'm
going to enter. And that's it. By default, this command won't automatically
reboot the machine to complete the domain join. If I add the restart parameter,
the command will take care of that, too. One final thing, over the years, there
have been several versions of Active Directory. We refer to these versions as
functional levels, and Active Directory domain has a functional level that
describes the features that it supports. If you're interested in seeing some of
these changes to Active Directory over time, take a look at the next reading on
AD functional levels. If you administer Active Directory, you'll need to know
what your domain and forest functional levels are, and may some day need to
upgrade your Active Directory forest or domains, or new features. So let's look
at the properties on this domain. So this domain is at version 2016. We can also
find this from PowerShell like this. So type in Get-AdForest, and then
Get-AdDomain. See the forest mode and domain mode properties? Now that you know
what your domain's functional level is, you can find out what AD features it
supports. Check out the supplemental reading for a whole lot of additional
documentation and training materials if you want a deeper dive into AD
administration.