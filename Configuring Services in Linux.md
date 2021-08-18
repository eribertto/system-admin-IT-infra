On top of knowing how to query the status, stop, and start services as a system
administrator, you have to know how to configure services to meet the needs of
your organization. For example, if you're running a DNS server, you'll need to
configure the DNS zones that you want to serve. If you're running a Web server,
you'll need to configure the different sites and Web applications that you'd
like to have enabled. And in general, you'll want to apply any specific security
and backup policies to all your services. The details will depend a lot on the
operating system and the service, but let's talk about the basics that you'll
need to know for all services. Most services are enabled as soon as you install
them. These are programs that are shipped with the defaults that are good enough
to safely start serving right away, but not all services can provide default
values that are suitable for everyone. In some cases, you will need to edit the
configuration files before the service can go live. On Windows, most of the
configuration is stored in the registry. This can be modified using graphical
wizards or using the set service command. On Linux, the configuration files for
the installed services are located in the /etc directory. And while some
software may ship graphical configuration editors, you typically have to edit
the configuration files with a text editor. Let's experiment with a simple ftp
server called vsftpd, a service that gets enabled by default when installed. So
I'm going to go ahead and type in sudo apt install vsftpd to install the
service. Once it's done installing, the service is already running. We can query
the status of the service by running service vsftpd status, and see that it's
running. This tells us that the service is already running. We can also verify
that it's running by connecting to the ftp server with an ftp client. To do
this, I'm going to go ahead and type in lftp localhost. Lftp is an ftp client
program that allows us to connect to an ftp server. When we tell it to connect
to local host, it'll try to connect to the ftp server running on local host.
Now, let's try to run the ls command to list the contents of the current
directory. So I'm going to type in, ls. And then type in exit. This is failing
because it's requiring a username and password, and we aren't providing them. It
makes sense that the default behavior of the ftp server is to be locked down. If
we really want to enable anonymous connections, we'll have to do that
explicitly. Let's modify the configuration file to allow anonymous connections.
To do that, I'll edit the configuration file for this service that's located in
the /etc/vsftpd.conf to change the anonymous enable setting from no to yes. So
I've got sudo vim /etc/vsftpd.conf, this will open up my config file. And then I
want to go ahead and change the anonymous_enable from no to yes, save my
configuration file. By changing the value of the anonymous_enable setting from
no to yes, we're telling the ftp server program that we won't allow anonymous
connections. We've made the change but we aren't done yet. If we try to connect
again, ls will still fail. Ls. It failed, and then we hit exit. This will also
happen with other services because most services read their configuration when
they start, and then keep it in memory while they're running. In order for our
service to re-read the configuration, we need to tell it to reload. Reloading
means that the service re-reads the configuration file without having to stop
and start. That way, ongoing connections aren't interrupted, but new connections
will use a new configuration. Let's do this for our ftp service, so I type in
sudo service vsftpd reload. Once we've done this we can try to connect again,
and this time executing at last will succeed. Let's see, it worked.