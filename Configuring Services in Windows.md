We've now seen how to start, stop, restart, modify configuration and reload this
configuration for Linux services. Let's look at how you can do something similar
using Windows. For this example, we'll be using Internet Information Services,
the feature offered by Windows to serve web pages. First, we'll need to enable
this feature. We'll use the "Turn features on and off" option in the Windows
Control Panel. So, I'm going to go ahead and click "Start", "Control Panel",
click on the "Turn Windows features on and off." This opens the Server Manager
which we can now use to enable Internet information services. So, I'm going to
go ahead and click on "Next", "Next" again, "Next" again, so a total of three
times. I'm going to go ahead and scroll down and look for Web Server, IIS. I'll
click on that. I'm going to click "Add features". Click "Next", click "Next"
again, "Next" again, "Next" again, and then hit "Install". I've selected the web
server option to have this service enabled on this Windows Instance. It's now
installing all the necessary pieces to enable a web server on this machine. It's
now done installing. When we close this window, we notice that there is a new
option on the service manager called IIS. We see here that we have an IIS
service running on this server. We can configure this service by right-clicking
on the entry and then selecting "Internet information services manager". Then,
I'm going to expand on our server and then click on "Sites". These are the
websites that are handled by the service. Currently, there's only one called
default website. Let's see what this website looks like by navigating to
localhost. So I'm going to go ahead and click on "Internet Explorer" and type in
"localhost". Great! Our server is serving the default website. Now, let's add a
different website to it. We go back to our Windows Information Services. I've
created an example site and stored it in "My documents" folder. Now, I'll copy
this example site into the inetpub directory, which is the directory normally
used to serve websites when using IIS. So I hit copy. Then, I'm going to go into
the Inet directory C:/inetpub. Now, I paste that example folder for my documents
to the Inetpub directory and then hit "Continue" in the Security Control. All
right, I've copied my website, now let's enable it in the IIS Manager console.
So, let's go back to the console. I can add a new website by right-clicking on
the list of websites and selecting the "Add website" option. I'm now presented
with a bunch of options that I need to fill in. Let's select example as the name
of my website. Let's select the folder that I just copied as the physical path
for the website. Finally, let's select 8080 as the port. This last one is so
that the default website can run in the default port, port 80, while our example
website can run in a separate port. All right, I set up the new website. IIS
tells me that the website is already up and running. Let's see if that's
correct. I'm going to go ahead and click on "Internet Explorer", type up
"localhost" and type in colon port 8080, and hit enter. Success. We've added a
second website to our webserver. We've now seen how to install, manage and
configure Linux and Windows services. In the next quick lab exercises, you'll be
able to try these actions yourself. Have fun.