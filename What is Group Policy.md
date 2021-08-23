All right, now that we've joined all these computers to our domain, what are we
going to do with them? In this lesson, we're going to talk about how to use
Active Directory group policy to configure computers and the domain itself. Like
we mentioned before, directory services are databases that are used to store
information about objects. The objects represent things in your network that you
want to be able to reference or manage. One of these object types in AD is group
policy object, or GPO. What's a GPO? It's a set of policies and preferences that
can be applied to a group of objects in the directory. GPOs contain settings for
computers and user accounts. You may want different software preferences for the
marketing team, the legal team, and the engineering team. Using group policy
would help standardize the user preferences for each of these teams and help
make it more manageable for you to configure. Using group policies you can
create log in and log off Scrubs and apply them to users and computers. You can
configure the event log telling the computer what events should be logged and
where the logs should be sent. You can say how many times someone can enter the
wrong password before their account is locked. You can install software that you
want to be available, and block software that you don't want to run. You heard
the boss, and this is just the beginning. You can create as many group policy
objects as you want. But they don't do anything until they're linked to domain
sites or OUs. When you link a GPO, all of the computers or users under that
domain, site, or OU will have that policy applied. You can use other tools like
security filtering and WMI filters to make group policies apply more
selectively. We'll get in to that a bit. A Group Policy Object can contain
Computer Configuration, User Configuration, or both. These are applied at
different times. Computer Configuration is applied when the computer signs into
the Active Directory domain. This will happen each time the computer boots into
windows, unless it's disconnected from the network at the time it's booted up.
User configuration is applied when a user account is logged onto the computer.
In each case, once a GPO is in effect, it's checked and enforced every few
minutes. Remember when I said that GPOs contain pauses and preferences? What's
the difference? Policies are settings that are reapplied every few minutes, and
aren't meant to be changed even by the local administrators. By default,
policies in the GPO will be reapplied on the machine every 90 minutes. This
ensures that computers on the network don't drift from the configuration that
systems administrators define for them. Group policy preferences, on the other
hand, are settings that, in many cases, are meant to be a template for settings.
System administrators will choose settings that should be the default on
computers that apply the GPO. But someone using the computer can change the
settings from what's defined in the policy, and that change won't be
overwritten. How do domain-joined computers actually get their GPOs? When a
domain-joined computer or user signs into the domain by contacting a domain
controller, that domain controller gives the computer a list of group policies
that it should apply. The computer then downloads those policies from a special
folder called Sysvol, that's exported as a network share from every domain
controller. This folder's replicated between all of the domain controllers and
can also contain things like log in and log off scripts. Once the computer has
downloaded it's GPOs, it applies them to the computer. We won't get into too
much detail about the Sysvol folder, but I've included links to more information
in the next reading. Lastly, many policies and preferences in GPOs are
represented as values in the Windows Registry. The Windows Registry is a
hierarchical database of settings that Windows, and many Windows applications,
use for storing configuration data. The GPO is applied by making changes to the
registry. The Windows Operating System and Windows applications read the
registry settings to determine what their behavior should be. You can read more
about the Windows Registry in the supplemental reading. Group policy management
is another huge topic. We'll only cover the basics of it in this course. Now
that you understand a little bit about what group policy objects are, let's dig
in and see how you use them to manage Active Directory and AD joined computers.