As a systems administrator, or IT support specialist, you might be called on to
troubleshoot issues related to Active Directory. Let's go through some of the
most common troubleshooting tasks that you may encounter. This lesson will
introduce you to tools that will help you troubleshoot these scenarios. Keep in
mind, these are only examples. Since we're working with complex systems, there
are lots and lots of ways for things to not work. Your greatest tool is to learn
about these systems and understand how they function. Thoughtful troubleshooting
and research are your friends. One of the most common issues you might encounter
is when a user isn't able to log into their computer or isn't able to
authenticate to the Active Directory domain. There are many reasons this might
happen. They may have typed the password with caps lock button on. They may have
locked themselves out of their computer, actually changed a system setting, or
it could be a software bug. It's important to think about the steps to
troubleshoot and remember to ask questions about what happened. Make sure to
look at the exact conditions under which the failure occurs and any error
message that accompany the failure. This should be enough information to get you
started down the right path to troubleshoot. Let's just talk for a moment about
the most common types of failures that can lead to a user account authentication
issue. As we discussed in the earlier lesson, if a user enters a wrong password
several times in a row, their account may be locked out. People sometimes just
forget their passwords and need a systems administrator to sort things out. Make
sure to review our earlier lesson on managing user and groups in Active
Directory if you need a refresher on resetting user passwords. If a domain
computer isn't able to locate a domain controller that it can use for
authentication, then nothing that relies on Active Directory authentication will
work. If you remember, from the customer support module in the first course, any
time you troubleshoot an issue, start with the simplest solution first. This
could be a network connectivity issue and nothing specific to Active Directory
at all. If the computer isn't attached to a network that can route
communications to the domain controller, then this must be fixed. You also
learned about network troubleshooting techniques in an earlier module, so we
won't repeat any of them here. Any networking issue that would prevent the
computer from contacting the domain controller or its configured DNS servers,
which is used to find domain controller, could be an issue. Now, why is DNS so
important? In order for the computer to contact a domain controller, it needs to
find one first. This is done using DNS records. The domain computer will make a
DNS request for the SRV records matching the domain that it's been bound to. If
a computer can't contact its DNS servers, or if those DNS servers don't have the
SRV records that the computer is looking for, then it won't be able to find the
domain controller. The SRV records that we're interested in are
_ldap._tcp.dc._msdcs.DOMAIN.NAME, where domain name is the DNS name of our
domain. So I'm going to go ahead to my PowerShell, and I want to go ahead and
type in Resolve-DNSName -Type SRV -Name _ldap._tcp.dc._msdcs.example.com. That
looks good. I should see an SRV record for each of my domain controllers. And I
do. Perfect. Now, if I can't resolve the SRV records for my domain controllers,
then my DNS servers may be misconfigured. How might they be misconfigured? Well,
my domain computers need to use the DNS servers that host my active directory
domain records. This will often be one or more of my domain controllers, but it
can be a different domain server. Either way, the appropriate DNS servers to use
for your domain computers should be known and documented. Compare the
configuration of the machine to the known good configuration and see if it needs
to be adjusted. On the flip side, if you're resolving some SRV records, but they
appear to be incomplete or incorrect, then in-depth troubleshooting may be
required. I've included a link to more information about this in the next
reading. One more thing to call out. Depending on the configuration of your
domain and your computers, it's common that local authentication will continue
to work, for a little while least. Once someone logs into a domain computer,
information required to authenticate that user is copied to the local machine.
This means that after the first login, you'll be able to log in to the computer,
even if the network is disconnected. You won't be authenticated to the domain or
authorized access to any domain resources like shared folders. Just because
someone is able to log in doesn't mean that they're able to find a domain
controller. Another issue that can prevent users from authenticating has to do
with the clock. Kerberos is the authentication protocol that AD uses, and it's
sensitive to time differences. I'm not talking about local time zones here. I
mean the relative UTC time. If the domain controller and computer don't agree on
the UTC time, usually within five minutes, then the authentication attempt will
fail. Domain computers usually synchronize their time with domain controllers
with the Windows Time service, but this can sometimes fail. If the computer is
disconnected from a domain network for too long, or if the time is changed by
software or a local administrator to be too far out of sync, then the computer
may not automatically re-sync with a domain controller. You can manually force a
domain computer to re-sync by using the w32tm/rsync command. I've included links
with more information about this in the next reading. Now, let's talk a bit
about troubleshooting group policy issues. A common issue that you might have to
troubleshoot is when a GPO-defined policy or a preference fails to apply to a
computer. You might learn about this failure in a number of ways, like a person
in your organization telling you that something on their computer is missing or
not working. If you're using GPO to manage configuration on your machines, then
maybe there will be a piece of software that should be present, or there may be
a mapped network drive that's missing or a number of things. The common factor
will be that something that you created a GPO to configure won't be configured
on one or more computers. Let's look at the three most common reasons that this
might happen. The first, and possibly most common type of GPO failure, has to do
with the way group policies are applied. Depending on how your domain is
configured, the group policy engine that applies policy settings to a local
machine may sacrifice the immediate application of some types of policies in
order to make logon faster. This is called Fast Logon Optimization, and it can
mean that some GPO changes take much longer to be automatically applied than you
might expect. Also, the group policy engine usually tries to make GPO
application faster by only applying changes to a GPO instead of the whole GPO.
In either of these examples, you can force all GPOs to be applied completely and
immediately with gpupdate/force. If you want to be really thorough, you can run
gpupdate/force/sync. Adding the /sync parameter will make you log off and reboot
the computer. Some types of group policy can only run when the computer is first
booted or when a user first logs on. So a log off and reboot is the only way to
make sure that a forced updated GPO has a chance to apply all of the settings.
Replication failure is another reason that a GPO might fail to apply as
expected. Remember that when changes are made to Active Directory, those changes
usually take place on a single domain controller. Those changes then have to be
replicated out to other domain controllers. If replication fails, then different
computers on your network can have different ideas about the state of directory
objects, like group policy objects. The logon server environment variable will
contain the name of the domain controller that the computer used to log on.
Remember that you can see the contents of the variable with this command in
PowerShell, which is $env:LOGONSERVER. It shows me DC 1. You could also get the
same results using command prompt which uses %LOGONSERVER%. Knowing which domain
control you're connected to is useful information to have if you suspect a
replication issue. From the group policy management console, we can check on the
overall health of the group policy infrastructure. I'm going to select my domain
and take a look at the status tab. This tab will summarize the Active Directory
and assist all replication status for the domain. It may be showing result from
a recent test so I'm going to force it to run a new analysis by clicking on
Detect Now. What we want to see is that all of our domain controllers are listed
under domain controllers with replication in sync. If they are, then we can be
sure that there are no replication issues that will affect our group policy
objects. If we do see any domain controllers in the domain controller with
replication in progress list, then we may have a replication issue. Depending on
the size and complexity of your Active Directory infrastructure and the
reliability and throughput of the network links between your AD sites, it's
possible for a replication to take a few minutes to complete. If replication
doesn't complete in a reasonable amount of time, you may need to troubleshoot
Active Directory replication. In the supplemental reading, you'll find a handy
guide to help you through this more advanced topic. We've focused on the
simplest cases for managing group policy. But the reality is that controlling
the scope of a group policy object can get super complicated. Take a look at the
supplemental reading to learn more about this topic, too. If you're trying to
work out why a particular GPO isn't applying to a computer, the first thing to
do is to run the resultant set of policy, or RSOP. You can use the group policy
management console, like we did in an earlier lesson, or you can run a command
on a computer directly to generate the report. The GP result command will help
us out there. If I run gpresult /R, you can see that I get a summary report in
my terminal. Let me go and show you that. So I'm switching to my PowerShell,
gpresult /R. Report being created, and I get this report. If I want the full
report, like I get from my GP MC, I can run gpresult /H FILENAME.html. I'm going
to do gpresult /H and then test.html. This will give me a report that's an HTML
web page that I can open in my browser, so let me go and get that. Okay, so with
this report in hand, I want to look for some things. Is the GPO that I want to
apply listed? Was it linked to an OU that contains a computer that I'm
troubleshooting? Is the GPO that I care about listed under applied GPOs or under
denied GPOs? If it was denied, what was denied reason? Did another GPO win for
the policy or preference that I'm trying to configure? Each GPO can be
configured with an actual called a security filter. Is the security filter set
to something besides authenticated users? If so, then that may mean that you
have to be in a specific group in order to read or apply the GPO. Each GPO can
also be configured with the WMI filter. A WMI filter lets you apply GPO based on
the configuration of the computer. WMI filters are powerful, but expensive, and
easy to misconfigure. This is because they look at Windows management
instrumentation values to decide if a policy should apply or not. For example,
if you could create a GPO that installs a piece of software, but only if a WMI
reports that a specific piece of hardware is present. These filters are
expensive because they require the group policy engine to perform some sort of
query or calculation on every computer that's linked to the policy, but then
only apply the GPO to computers that match the filter. Many policies and
preferences can be configured to apply to the computer or to users as they log
on. Did you mean to configure a computer setting but accidentally configure a
user setting, or the reverse? There's a really in-depth group policy
troubleshooting guide in the supplemental reading that you should refer to if
you get into a really tricky GPO troubleshooting session. We've really covered a
lot out here. If you aren't clear on any of the concepts we've covered, that's
okay. Just make sure to re-watch the lessons. Remember though, that the more you
work with Active Directory and the group policy, the more familiar you become
with them. If you use what you've learned about these systems combined with your
research skills, you can troubleshoot just about anything.