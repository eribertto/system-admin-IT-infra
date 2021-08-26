As we mentioned in an earlier, lesson a common sys admin task, is managing the lifecycle of user accounts. User accounts are an important part of IT. They identify who you are, and they're used to control what kind of access you have to IT resources in your organization. Poorly managed user accounts can prevent people from doing what they need to do, which can waste time and get really frustrating. User accounts that have too much access or are no longer needed, create risks for the organization. All of this together, means are making sure that user accounts are created, maintained, and eventually deleted is one of the most important tasks, that a system administrator can have. So, let's dig in. Let's create a user account for Kristi using the Active Directory Administrative Center and put it in the default user container. If we right-click on users, right here and then click on user, we get this dialogue to create a user. There's a whole bunch of stuff here. Do we really have to fill all of these in? Thankfully not. Only the fields that had a red asterisk next to them are required. Let's go ahead and enter a full name and account name for Kristi. The full name is a person's real name, but what's user SamAccountName log on? That's a very long way of saying username. The security count manager or SAM, is a database in windows that stores user names and password. This is where SamAccountName comes from. So, let me go ahead and type in Kristi first. I'm going to type in her user account, we will also name her Kristi. You can see that the domain is going to be part of the accounts full name. Each user account has to have a unique username within the domain. We're just going to use Kristi's first name here. Now, let's set a password for the new user account. We don't want to know Kristi's password, so we're going to make sure the option user must change password at the next login is checked, and then choose a random password for her, like so. All right. The AD Administrative Console, lets us create user accounts one at a time, but eventually, we're going to need to create a whole bunch of accounts at once. Imagine registration time at school or university, when hundreds or thousands of new user accounts will need to be created in just a few days. You wouldn't want to do that by clicking through ADAC forms. If you know how to create a user account in the command line interface, then you can learn how to write a script that will run those commands for you over and over again. For now, we just want to be able to see the commands that we'll need to do what ADAC does for us. It turns out that everything that you do in ADAC, is actually done in PowerShell. Down at the bottom of the console is a Windows PowerShell history pane that we can expand to see the commands that are being run by ADAC. It looks like ADAC run a few commands, when we created Kristi's user account. You can take an example like this and generalize it to create a script, that can be used to repeat this process hundreds of thousands of times. There's one other thing that I like to call out. When we need to describe the full path of an object in AD, we'll often use LDAP notation. You can see that in several other parameters in this PowerShell history. Okay. Next, let's look at active directory groups. Remember our early discussion about groups used to grant permissions to roles. Let's create a group based on Kristi's role, in this fictional org. Kristi is a researcher in the Active Directory Administrative Center, right-click on the user's container, and select new group. We're going to call this group researchers. So, let's enter that into the group name field. See the SAM account name field again. It fills automatically with the name as we type it. You can create a group with different full name and SAM account name, but it's usually not useful to do that. What is a good idea, is to provide a description of the group. That way, everyone understands what the group's for. We can also add an initial set of users from the screen, but we're going to save that for the next step. For now, let's click "Okay" and the group will be created. The group now shows up in ADAC, and the description is right there to remind us of what the group's used for. Excellent. Now, let's check ADAC's work and see how to do this in PowerShell. So, I'm going to go ahead, and open PowerShell and paste my command. There it is. You can see all of the settings, that we filled in fields for in the create group dialogue in ADAC, but what are group category and group scope? If you look back at the new group window, you'll see that there are two mandatory settings, that we just left as default, group type and group scope. So, what are they? They are two categories of group in active directory. The most common one and the only one that we'll deal with in this module, is called a security group. Security groups can contain user accounts, computer accounts or other security groups. The default groups, that we talked about before, like domain users and domain admins are security groups. They're used to grant or deny access to IT resources. Let's say you create a human resource group and then give that group access to a shared folder specifically for folks in human resources. The other type of group is called a distribution group. A distribution group, is only designed to group accounts and contacts for email communication. You can't use distribution groups for assigning permission to resources. One reason you might use a distribution group instead of a security group, is to create an email list that included people from outside of your domain. What about group scope? Group scope has to do with the way that group definitions are replicated across domains. Keeping a lot of large groups synchronized in very large network is a complicated problem. So, Active Directory gives us different types of groups to manage that complexity. Most commonly, group scopes are used like this. Domain local. This is used to assign permission to a resource. An example of this would be to create a domain local group, that has read access to a network share called ResearchShareReaders, and another with write access called ResearchShareWriters. Global. This is used to group accounts into a role. Our example, researcher's group, is a global group. You could have other role-based groups like sales or management. Universal. This is used to group global roles in a forest. Domain local and global groups aren't replicated outside of the domain that they're defined in, but universal groups are. In a multi-domain forest, you might have a global ResearchShareReaders group in each domain, and all ResearchShareReaders universal group that contains each global group has members. Universal groups are replicated to all domains in a forest. The details of AD group scope are a bit more complicated, than we have time to get into. So, check out the supplemental reading if you want to know more. For now, we'll stick to creating domain local resource groups and global role groups. With domain local resource groups and global role groups, you can create very easy to understand group memberships. They very clearly describe what kind of access each role is supposed to have to each resource. So, I can add matches to the ResearchShareReader group and researchers to the ResearchShareWriters group. That's all very easy to understand. Now, if we add Kristi to our new researcher's group, she can write to the ResearchShare folder. It's not because her user account was given direct access to the files there, but because she's a researcher. All right. Let's add user accounts to our new researchers group. We can do this from the user account or from the group. Let's start from Kristi's user account. In the Active Directory Administrative Center, right-click on her account and select add to group. So, I'm going to do that right now. Now, in the enter the object names to select field, type researchers. So, let's do that right now, and then click "Okay". That's it. What did ADAC do in the background? ADAC used a PowerShell command that takes an Active Directory security principle, like a user account or security group and added to its group membership. I've included a link to more info about security principles in the next reading. Now, what if we want to make changes from the group instead? Let me add myself to the researchers group and see how that works. I'll right click on the researcher's group and then click on properties. Okay. If I click on members, I can see that Kristi is a member of this group. Now, if I click on this add button off to the right, it'll bring up a similar dialog windows you saw before. Now, I enter my account name and click "Okay". So, some administrator, okay. Just like we made changes from the group instead of the user, so did ADAC in PowerShell. This time around, we used a PowerShell command to set or make changes to an existing AD group. We added my account to the researchers group. Now, I'm not really a researcher in this org, so let's go ahead and remove my account using ADAC. This time of course, I use the remove button instead of the add button and we're done. As you can see, the only thing that changed in the PowerShell command was a single parameter to remove instead of add a member. Most people in an organization have more than one role. In our fictional company, researchers are part of the research and development department. Some network resources will be shared with all of R and D, while some resources will only be made available to researchers. It makes sense for us to create a parent group for the R and D department. Let's create a global security group for this. What we're going to do is we're going to go ahead and right-click users, click new group and then we're going to go ahead and name our group named research and development. The description we're going to go ahead and write all of the members of the research and development group, and then we're going to hit "Okay". Now, our researchers are part of the R and D department, in addition to being researchers. So, instead of adding each researcher independently to the research and development group, we can add the researchers group as a member. If I type research, like this and hit "Okay", I get a list of all of the users and groups that start with research. Let's go ahead and select research and development to add the researchers group. What happened at the Windows PowerShell History? Remember, user accounts and groups are both security principles. So, we use the same PowerShell command to change group membership here like we did before. So, we've created a user and added them to some new groups. The next thing that you should know, is how to assist the people that you support with password management. We'll go over that and more in the next lesson.