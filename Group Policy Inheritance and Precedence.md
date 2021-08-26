If you follow the practice of creating specific GPOs to address specific
categories of needs, you can end up with a whole lot of policies linked at many
levels of your Active Directory hierarchy. Group Policy Objects that control
security settings are a really common place where this can happen. Systems
administrators are responsible for protecting the security of the IT
infrastructure. So, it's a good practice to create a very restrictive GPO that
uses very secure conservative security policies and link that to the whole
domain. This gives you a secure default policy but some users or computers may
not be able to do what they need to with those very conservative policies in
place. The finance department might need to use Excel macros that are disabled
in your default security policy for example. So, we can create GPOs that relax
some of the security settings or policies in the OUs that contain those
computers or users. Another example might be that we have a Group Policy Object
that standardize the desktop wallpaper of all computers. But we have computers
that are public access kiosks that need to have a different wallpaper. In any of
these cases, you can have computers or user accounts with multiple GPOs assigned
to them that contradict one another by design. So, what happens when there are
two or more contradictory Group Policy Objects that apply to the same compute?
When computers processing the Group Policy Objects that apply to it, all of
these policies will be applied in a specific order based on a set of precedents
rules. GPOs are applied based on the containers that contain the computer and
user account. GPOs that are linked to the least specific or largest container
are applied first. GPOs that are linked to the most specific or smallest
container are applied last. First, any GPOs linked at the AD site are applied
then any link at the domain. And then any OUs in order from parent to child. If
more than one policy tries to set the same policy or preferences, then the most
specific policy wins. To see what I mean, let's look at this AD structure. As
you can see my structure, I have multiple OUs. We have my IT OU, we have my
sales OU, I also have my research OU. And I also have my sites in Australia,
India, and North America. If you have a computer in the India site and the
example.com sales computer OU then Active Directory would apply Group Policy
Objects that are linked to the India site, the example.com domain, the sales OU,
and the computers OU in that order. That's not all though. You can actually link
multiple GPOs to the same container. How does AD decide which order to apply the
GPOs in if there are more than one in a container? Each container has a link
order for the GPOs that are linked to it. So, let's look at our sales OU. The
sales OU in our example domain has a GPO for a network drive mapping and a GPO
for configuring network printers. The link order of each policy determines which
GPO takes precedence. The highest number is the lowest ranked GPO, so its
settings are applied first. Network printers, sales is applied first and network
drives, sales is applied last. If anything the network drive policy contradicts
the network printer policy and the drives policy wins out. Let's summarize this
so far. The highest numbered link order in the least specific container is
applied first. And the lowest numbered link order in the most specific container
is the last GPO applied. The last GPO to modify any specific setting wins. And
the group policy management console, we can see the precedence rules in action.
I'm going to switch to the computers OU in group policy management. I can see
that there is a policy linked here called Computer Security Policy, I want to
increase this. By switching from the link Group Policy Objects tab to the Group
Policy Inheritance, like so, I can see that objects in this OU will actually
have quite a few policies applied. The precedence column tells us which policy
will win if there are conflicting settings, and the location column tells us
where the policy was linked. You might have noticed that there are no site link
policy listed here. That's because you can have computers from many different AD
sites in the same OU. So, site based GPO links aren't represented in this
summary. When you add all of the group policies together for a specific machine
and apply precedence rules to them, we call that the Resultant Set of Policy or
RSoP for that machine. When you're troubleshooting group policy, you often
compare an RSoP report, pronounced "Haar sope" to what you expect to be applied
to that computer. There are a lot of ways to get RSoP report. We will use the
group policy management console for now and look at the other method when we
start troubleshooting. Let's check on what Group Policy Objects will apply when
one of our sales staff logs onto their computers or right click on the group
policy results node in GPMC and select group policy result wizards. Let me go
and do that. This wizard will walk me through generating a Resultant Set of
Policy report for the computer and user my choice. The computer that I'm using
to run this report will make a remote connection to that computer and ask it to
run the report. The report would then be visible in my local GPMC. I'd like to
see that RSoP when Emmett is logged into his computer which is EMMETPC01. Let me
go and do that, so I'm going to hit next. I want to search for his computer. So,
I hit another computer, hit browse and type in EMMETPC01 and hit okay. The group
policy results in wizard it's super simple. First, I enter EMMETPC01 as a
computer that I want to run the report on. By default, the wizard will only run
an RSoP report for computer configuration. Since I want to see the user
configuration for EMMET2, I will select display policy setting for him which is
actually always selected by default. So, what we going to do is we going to hit
next and it's going to take us to the summary of selections. And then we going
to hit next and to generate the report, we hit Finish. I will hit close. You can
only select users from this list who've already logged onto this computer in the
past. That's it. I review my selection in the summary dialog then finish the
wizard. I'm left with a new item under the Group Policy resultant node in GPMC
and it contains a Resultant Set of Policy report that I just requested. Great.
This RSoP report contains everything that we need to understand what policies
apply to a computer or user. It includes a whole lot of detail about where the
computer and user are located in AD, what their security group memberships are
and more. I'm going to set that aside for the moment and focus on the setting
sections of the report. Which I am going to scroll down to. This looks a lot
like the information you see in the settings tab of a GPO but instead of only
showing you the settings modified by a single GPO, you can see the combined
effect of all of the applied GPOs. The winning GPO column tells you which GPO
ultimately took precedence for each policy and preference. Amazing, right?
Remember, I am making a remote request for my group policy management console to
EMMETPC01 to run this report. There are a bunch of reasons that this could fail
to work. EMMETPC01 may be powered off, it could be disconnected from the network
or have firewalls that prevent me from running the report remotely. If I'm not a
local administrator on the machine, I won't be able to run the report. In any of
these cases, if I need that RSoP report for troubleshooting, I might have to run
commands locally on Emmett's PC01. Will cover additional troubleshooting
techniques in a future lesson.