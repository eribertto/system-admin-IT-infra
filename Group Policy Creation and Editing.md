The most important tool we'll use for creating and viewing group policy object
is called the group policy management console or GPMC. You can find this in the
tools menu of server manager or by running GPMC.MSE from the command line. You
can see that the layer of GPMC is similar to other management tools that we've
used in Active Directory. On the left, we see the structure of Active Directory.
GPMC adds several containers to it's GUI. These aren't AD containers we all use.
There are management interfaces that only show up in GPMC. The group policy
objects container will hold all of the GPOs that are defined in the domain. The
WMI Filters container is used to define powerful targeting rules for your GPOs.
These filters use properties of Windows Management Instrumentation or WMI
objects to decide whether or not a GPO should apply to a specific computer. This
is a more advanced topic, but if you want to dive a little deeper, check out the
link in the supplemental reading. Group policy result is a troubleshooting tool
that's used to figure out what group policies apply to computer and user in your
network. You would use this tool to check on group policies that are already
applied to a computer or user. On the flip side, group policy modeling is used
to predict which group policies will apply to a computer or user in your
network. You use this tool if you wanted to test a change to your GPOs or use or
WMI Filters before making real changes in your Active Directory. We'll go into
each of these in detail as the lesson goes on. You might have also noticed that
there are a couple of things missing. Remember that the users and computer
containers are not organizational units. Group policy objects can only be linked
to domain, sites, and OUs. If computer and user objects are in the default
containers they can only be targeted with GPOs that are linked to domains and
sites. It's a good practice to organize your user and computer accounts in OUs
so they can be targeted with a more specific group policies. Now, let's get
started with group policy objects note in GPMC and take a quick look at a GPO
that already exist. In a brand new Active Directory domain, they'll be two GPOs
that are automatically created: the default domain controller policy and the
default domain policy. The default domain policy is, as you might guess, a
default GPO that is linked to the domain. It applies to all of the computers and
users in the domain. The default domain control policy is linked to the domain
control's OU and applies, you guessed it, to the domain controllers. What we're
looking at here is a settings report for the default domain policy. This GPO is
designed to enforce policy decisions that we want to make for the entire domain.
For example, the minimum password length policy prevents users from setting
passwords that are too short. The audit account log on events policy says that
the computer should create a Windows event for each successful and failed log on
attempt. There are thousands of settings that can be controlled with GPO, so it
can take some research to find the right setting to change in a group policy
object to make a change that you want. Group policy has been around through
several versions of Windows, and sometimes things aren't exactly where you'd
expect to find them. Don't despair. There are lots of documentation online about
group policies and where to find specific settings. Pro tip, something that you
might find super useful are the group policy settings reference that Microsoft
releases with each new version of Windows. This reference is a spreadsheet that
details the GPO policies and preferences that are available and where to find
them. Next, let's try changing one of the settings in our default domain policy.
Before we get started, I'm going to make a backup of the GPO. I'll right-click
on the policy and choose backup. I've created GPO backup for my desktop, but in
a real variant, we'd want to create a network for this lock down to only allow
domain administrators to access it. I can add a description here too to help me
remember why I made the backup. Then I complete the backup wizard and I'm done.
Now, I know that if I make a mistake, I can restore the policy from backup. So
I'll right-click on the policy again but this time, I'm choosing edit. This will
open up the default domain policy into the group policy management editor. You
can see over in the left-hand pane that the GPO is divided into two sections:
computer configuration and user configuration. Each of these is divided into
policies and preferences. Inside this tree of policies and preferences, as every
individual GPO setting that GPMC knows about, whether it's been configured or
not, every GPO has accessed the same settings that every other GPO has access
to. There aren't special GPOs. Even so, it's a good practice to make different
GPOs that each address a specific category of need. For example, you might have
a GPO that handles all of the settings for a specific group of users or one that
handles security policies for the whole domain. With specific GPOs for specific
solutions, you can link your GPOs to only the computer or users that need that
policy. Since you're working with the entire universe of group policy in every
GPO, it can be very difficult to tell from the editor what settings are actually
configured in this GPO. Refer back to the settings report in the GPMC for that
information. It looks different, but you might notice that the settings report
is laid out in the same hierarchical fashion as the GPO editor. I can see that
the account lockout threshold is configured to zero, invalid log on times. Let's
take a look at that policy in the GPO editor. I'm going to use a settings report
as a road map to finding that policy in the editor. So let me show you how. I'm
going to go ahead and right-click, Default Domain Policy, hit edit. And I will
have this to the side so I can look at our road map. So as you can see, computer
configurations, so I click computer configuration, then click policies, click
Windows settings, want to click security settings, and then account policies
because we're interested in the lockout policy. You can see that there are three
policies under account lockout policy. The policy column tells us the name of
the policy and the policy setting tells us the current configuration of the
policy. If a policy is not defined, then this GPO won't make any changes to that
setting on the computers that it's apply to. The policy name is pretty easy to
understand, but I'm not sure that I understand all of the consequences of
changing those values. If I double-click on any of these policies, it will open
up the properties dialog for that policy. Oh, what's this? There's an explain
tab here. Awesome. The explain tab will tell us what the policy configures. It
may also tell us what to expect if the policy is not defined and what the
default value of the policy is if it's enabled but not customized. So looking at
the explanation of the account lockout threshold policy, I see that by having it
set to zero, accounts will never be disabled for failed log-in attempts. That's
not what I want in my domain, so I'm going to change this value. Oh,
interesting. It looks like this policy has some dependencies on other policies.
Okay. I'm going to accept these defaults, and now, I'll see that all three of
these policies in the account lockout policy have been configured. So how do we
save these changes? As soon as you hit apply or OK in a group policy management
editor dialog, the changes made in the GPO immediately. Almost right away,
computers can receive the update and start applying it. That might not be what
you wanted. When you need to make changes to a production group policy, you
should test them first. For example, I was playing around with the default
domain policy which is linked to the whole domain. So I just immediately made it
so all user accounts will be locked if they enter their password incorrectly
once. Whoops. Where's the undo button? Guess what? There isn't one. Don't worry.
This is why we made a backup before starting to work on this policy. Let's
restore the policy from backup and undo this catastrophe waiting to happen. Back
in the group policy management console, I'm going to right-click on default
domain policy in the group policy objects and then select restore from backup.
This wizard remembers the last place that I backed up a GPO, and it seems that's
where I want to restore from. So intuitive. Now, it lists each of the GPO
backups that are in the folder that we choose. The name of the policy and the
time that it was backed up are listed here, along with any descriptions that we
provided when we did the backup. If I click on view settings, it would launch my
web browser with the settings report of the backup. Cool, right? Okay. I need to
get this policy restored so my users don't get locked out of their accounts. The
summary dialog shows me what I'm about to do, so let's go there. This all looks
right. So I'm going to click finish and make sure that my policy has been
restored. Perfect. My backup has been restored, and my mistake has been undone.
As you've seen in this example, before making changes to a GPO, you should
always back it up, but what's another way I could have prevented this mistake?
That's right. I could have tested my changes. There are lots of ways to do this.
I'll summarize some simple steps here and provide additional documentation in
the supplemental reading. Some organizations will have established best
practices for testing GPO changes in their environment. If that's the case, then
you should follow those standards. You might need to follow a change management
process too in order to notify others in the organization about the changes that
you were about to make. What I'm going to show you is just one way of adding
some safety to GPO changes. Let's say, I have a GPO code example policy. Good
name, right? I want to make changes to example policy, but I want to test the
changes first to make sure that I don't break production machines. First, I set
up a testing OU that contains test machines or user accounts. If example policy
is usually linked at example.com, finance, then computers, then I can create
example.com, finance, computers, test, and put testing machines in the test OU.
This lets the test machines keep all of the existing production GPOs but gives
me a place to link a test GPO that'll overwrite production. Let me go and show
you how I do that. So I click example, click new, click OU, and type in finance
and click OK. Thinker another OU from my computers, and then underneath that,
I'm going to go ahead and make a test OU so I can test my GPO, hit OK. Next, I
make a copy of the GPO that I want to change and call it something like test
example policy. Let me show you how I do that. So this is one policy that I
have. I'm going to hit copy, go to my group policy objects, hit paste. Now, it
say, "Use the default permission for the GPOs," because we want to make a copy,
of course, and hit OK. As you can see, its called 'copy of master'. I'm going to
rename this to test example policy, enter. Now, I can make the changes that I
want to test in test example policy and link it to my test OU, and let me show
you how I linked that. I'm going to go into my OU finance, computers, and then
test, right-click test. And now, it'll say, "Link an existing GPO," which is
going to be my test example policy right here and then hit OK. After I confirmed
that my changes work the way that I expected, I can make a backup of the test
policy then import the backup of test example policy to the production example
policy. This makes some extra work for me since I'm a systems administrator, but
I also benefit from added safety and peace of mind. By testing my changes on a
copy of the GPO on test machines, I make it much harder to accidentally break
production with machines. Your organization might be using advanced group policy
management or AGPM, which is a set of add-on tools from Microsoft that give you
some added provision control abilities in GPMC. If you do use AGPM in your
organization, you should follow best practices for GPO version control using
AGPM. I've included a link to those best practices in the next reading. We've
edited the GPO and seen some ways to make editing GPO safe. Now, we need to know
a bit more about how to understand all of the policies that are applied to a
specific machine or user account. Next up, GPO inheritance and precedence. I'll
see you there.