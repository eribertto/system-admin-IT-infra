We've talked about lots of services. DNS, DHCP, NTP, and others. As an IT
support specialist, it's important to understand how the programs that provide
these services operate. So, that you can manage them and fix any problems that
pop-up. These programs run as background processes. Also known as daemons, or
just services. This means, that the program doesn't need to interact with the
user through the graphical interface or the command line interface, to provide
the necessary service. The operating system ensures that the program is running.
Each service has one or more configuration files, that you as a system
administrator will use to determine how you want the service to behave. Some
services may offer interactive interfaces, that allow a user to edit the
configuration, and to inspect the current status or the usage history. Other
services may just rely on the system infrastructure for this. Which means you
need to edit the configuration files yourself. You have to know how to start and
stop the service, and how to go through its logs to see any current or previous
activity. Services are usually configured to start when the machine boots. So
that if there is a power outage or a similar event that causes the machine to
reboot, you won't need a system administrator to manually restart the service.
If you want to decide yourself when the service starts, instead of starting upon
boot, you need to change the software configuration to make it start when you
want. Similarly, services are usually configured to restart if they crash
unexpectedly. If this is not how you want to set up, you may need to change the
system configuration than handles these properties. There are lots of services
out there, and each may require specific knowledge regarding how to configure
it, and when and how to use it. But the general concepts relate to managing and
configuring services are the same across the board. In the rest of this lesson,
we'll look at examples of how to do this on both Windows and Linux.