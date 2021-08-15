The other reason we might want our own DNS servers is so we can map our internal
computers to IP addresses. That way, we can reference a computer by name,
instead of IP address. There are a few ways we can do this. One is using a local
host file which contains static IP addresses to hostname mappings. Let's take a
look at an example of this. Remember, that we learned that hosts files and
networking allows us to map IP addresses to hosts things manually. In Linux, our
host file is code etc/hosts. It has an IP address that points to 127.0.0.1 which
points to a name called localhost. This just references back to the computer.
Localhost is commonly used as a way to access a local web server. We'll talk
about web servers in an upcoming module. So for now, let's not worry too much
about localhost. Instead, if I change this IP address mapping to www.google.com,
then save and open a web browser, and type www.google.com, it won't take me
there. Let me show you that. So I'm going to go ahead and change my localhost to
www.google.com. I'm going to save this. Open my web browser to www.google.com,
and as you can see, it didn't take me anywhere. It just takes me back to my
local computer. This is because a DNS query first, checks our local host file,
then our local DNS servers. So, if there's an entry for google.com in my host
file, you go to that IP address instead. Let's say I wanted to access Natalie's
computer at 192.168.15 and her host name is catlady.examplecompany.com. I would
have to enter this in my host file for every single computer in my fleet. That's
definitely not a scalable option. So, what's our next choice? We can set up a
local DNS server that contains all the organizations computer names mapped to
their IP addresses. This is a more central storage location for this
information. Then, we change our network settings for all our computers to use
as DNS server instead of the one given to us by our ISP. Finally, let's look at
one of the last DNS option we can use for an internal network. It can be
integrated with a directory service which handles user and machine information
in its central location like, active directory and LDAP. Once we set up DNS in
our directory service, it will automatically populate with machine to IP address
mappings. So, there's no need to enter this information in manually. We'll talk
more about these directory services in the later module. And voila, that's an
overview of why you need the DNS along with your options for configuring them.
We won't dive too deeply into the technical details of setting up a DNS server,
but if you're interested in learning about which DNS software to use, there are
a few powerful options like Bind or powerDNS. I bet you can guess where you can
read more about them. In the supplemental reading. One thing about DNS, that we
haven't discussed is what to do if we use something like DHCP, which doesn't use
static IP addresses. Don't worry, we'll cover this in the next lesson.