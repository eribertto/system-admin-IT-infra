Like Linux, Windows also allows the system administrator to manage the services
that are running on the system. For this example, let's look at the Windows
Update service. This service is in charge of detecting software updates for
either the operating system or other installed programs, downloading them and
having them ready to be applied to the system. Let's get the status of the
running service using the Get-Service command. So, I'm going to go ahead and
open PowerShell and I'm going to go ahead and type in Get-Service. I'm going to
type in the shorthand form of Windows Update service which is this. So, wuauserv
is a short name for the Windows Update service. We can see that the Windows
Update service is running and can get more information about it by running this
next command, which is going to be Get-Service wuauserv and then I'm going to
type in Format-List and asterisk. This will show us what type of service it is
and how it's configured to run. It's a good way to get additional information on
a service you're interested in. As with Linux, any user can query the status of
a service but only administrators can start or stop a service. If you try to do
the next steps with a normal user shell you won't be able to run the commands.
Now, let's try stopping the service and then checking the status. For this, I'll
open an administrator PowerShell and run the Stop-Service command. So I'm going
to go into my Start and instead of clicking on it, I'm going to right-click and
then type in run as administrator. Yes, to the security control. So, now I'm
going to go ahead and type in Stop-Service wuauserv. Next, I'm going to type in
Get-Service wuauserv. So, this service has been stopped. In order to start it
back up, we execute the Start-Service command, which I'm going to do
Start-Service wuauserv to start the service. Then I'm going to type in
Get-Service to show that the service is now running. Finally, you can list all
services that are registered in the system using the Get-Service command. We can
also perform these same actions graphically using the services management
console. So, I'm going to go ahead and click on start. This console shows us all
the services in the system. The ones that are running will say running in the
sales column, while the ones that aren't running won't say anything in the
status column. We can find the Windows Update utility at the end of the list. We
can stop it by right-clicking on it and then hitting stop and then
right-clicking again and hitting start. There you have it. That's how you get
the status Stop and Start services in Windows.