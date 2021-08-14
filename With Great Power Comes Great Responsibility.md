When you have administrative rights for something, whether it's one machine, a
fleet of 100 machines, or a cloud service with thousands of users, you need to
be careful that you use these rights responsibility. The most important thing is
to avoid using administrator rights for tasks that don't require them. For
example, you shouldn't browse the web as an administrator user. Try to minimize
the time spent in an administrative session. Do whatever you need to do, and
once you're done close the session. In Linux systems, we usually use the pseudo
command to execute commands as an administrator. When you execute pseudo for the
first time in a machine, you get a message like this. These principles apply to
any administrator rights regardless of the operating system or service you're in
charge of. Let's take a deeper dive into what this all means. Respect the
privacy of others. Don't use your administrator rights to access private
information that you have no business accessing. Having file system access to
the information stored in a user's home directory doesn't mean you should be
looking at their personal files. Being an administrator of an email server
doesn't mean you should read someone else's email. Just because you can doesn't
mean you should. Even if you have a business reason to access a certain piece of
information, make sure you follow the appropriate process or policies to access
it. You shouldn't use your administrator rights to bypass any rules. Think
before you type. When you use your administrator rights, your actions can have
much greater consequences than you when you're acting as a normal user. Think
through what you're doing and don't rush. Mistakes like deleting the wrong set
of files, rebooting the wrong machine, or breaking the connection that you're
using to manage a remote machine can all happen if you're not careful. You can
train yourself to do this by writing out the steps you plan to take before doing
them. This helps in two ways. It allows you to plan ahead and serves as
documentation of what you did. Documenting what you did is crucial when using
administrator rights. Listing the commands you executed let's you repeat the
same exact process in the future and fix any problems that may come up later. In
Linux, there's a command called script. We can use it to record a group of
commands as they're being issued along their output. In Windows Power-Shell,
there's an equivalent command called Start-Transcript. The output of these tools
is useful for automating procedures. Similarly, we can use the recordMyDesktop
tool to record the interaction with the graphical application. We put
information about these tools in the next supplemental reading. The last of the
pseudo-command principle is, with great power comes great responsibility. It's a
little cheeky but the point is serious. The more you can do with your
administrator rights, the more you can mess up. You can minimize the impact of
any mistake, and some mistakes are inevitable, by making sure you can quickly
revert your changes if something goes wrong. You can do this by making a copy of
the state before changing it. By keeping your configuration in a version control
system or by documenting what steps you needed to take in order to go back to
the previous state. Reverting to the previous state is called a rollback. Some
commands are easy to roll back than others. For example, if you change a
configuration setting from true to false, the rollback is to set it back to
true. But if you're deleting a file in a way that it doesn't keep a backup copy,
the rollback could be tough or even impossible. So, before you make a change,
take a moment to think about what all that would look like and make sure you
have copies of any information that could be lost.