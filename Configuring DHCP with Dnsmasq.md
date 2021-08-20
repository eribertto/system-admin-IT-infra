We've seen how to use dnsmasq to serve DNS queries, but as we mentioned before,
dnsmasq can also be used for other networking services. Let's look at how it can
be used as a DHCP server. A DHCP server is usually set up on a machine or a
device that has a static IP address configured to the network interface which is
being used to serve the DHCP queries. That interface is then connected to the
physical network that you want to configure through DHCP, which can have any
number of machines on it. In real life, the DHCP server and the DHCP client
usually run on two separate machines, but for this example, we'll be doing a
simulation on one machine so that you can experiment with a similar set-up in
the upcoming quick lab exercises. In this machine, we have an interface called
eth_srv, that's configured to be the DHCP server's interface. So, now I'm going
to type in ip address show eth_srv. This command shows us that this interface
has the 192.168.1.1 IP address. The slash 24 part indicates that this IP is in a
network that goes from 192.168.1.0 to 192.168.1.255. If this isn't clear, you
may want to review the lessons on IP addressing in the networking course. The
interface also has an IPV6 address configured, but we won't go into IPV6 for
this example. We also have an interface called eth_cli, which is the interface
that we'll use to simulate a client requesting an address using DHCP. This
interface doesn't have an IP configured yet. So, I'm going to type in ip address
show eth_cli. We can see that this interface doesn't have an IPV4 address
configured. We will change this by using our DHCP server. To do this, we need to
provide additional configuration to dnsmasq. There are lots of things we can
configure. We're going to use a very basic set of options. Let's look at the
configuration file. So, I'm going type in cat DHCP config. The interface option
tells dnsmasq that it should listen for DHCP queries on the eth_srv interface.
The bind interfaces option tells it not to listen on any other interfaces for
any kind of queries. This allows us to have more than one dnsmasq server running
at the same time each on its own interface. The domain option tells the clients,
the networks domain name and will be used for querying host names. Then, we have
two different DHCP options, which are additional information that will be
transmitted to DHCP clients when the IP is assigned. In this case, we're telling
clients what to configure as a default gateway and which DNS servers should be
used. There are a lot more options that we can set, but these two are the most
common ones. Finally, we configure the DHCP range. This is the range of IP
addresses that the DHCP server can hand out. Depending on your specific setup,
you may want to reserve some of the addresses in your network for machines that
need to have a static address. If you don't plan to do that, you can make the
range larger, but make sure you don't include the address of the DHCP server
itself. The last value in the DHCP range Line is the length of the lease time
for the IP address. In this case, it's 12 hours, which means that once an
address is assigned to a machine, it will be reserved for that machine for those
12 hours. If the lease expires without the client renewing it, the address can
be assigned to a different machine. All right, we've gone through the
configuration file. Let's tell dnsmasq to start listening for queries using this
config. So, now I'm going to type in sudo dnsmasq -d -q -c DHCP config and then
hit Enter. We can see in the output that dnsmasq is listening for DHCP queries
on the eth_srv interface with the options that we set in our configuration file.
Now, let's run a DHCP client on a second terminal. So, I'm going open up the
second terminal. Now, my second terminal, I'm going type in sudo dhclient -i
eth_cli and then -v for verbose. We're using dhclient which is very common DHCP
client on Linux. We're telling it to run on the eth_cli interface and we're
using the -v flag to see the full output of what's happening. Back in the
networking course, we explained the whole process of DHCP client getting a DHCP
lease and here, we see the packet's being exchanged and how our client got the
IP address 192.168.1.80. We also see that the DHCP client expects to renew the
address before it expires. Let's see how our interface looks now. So, now, I'm
going to type in an ip address show eth_cli. Our eth_cli interface has
successfully acquired an IP address. Now, let's look at what dnsmasq printed
when the request was made. We see the same packet exchange that we saw from the
client, but dnsmasq also shows that it now knows the host name of the machine
with the address 192.168.1.80 because dnsmasq also has DNS capabilities. This
means it will also provide this as an authoritative answer for local queries.
So, now I am going to type in dig @localhost instance-1. With that, we've seen
how dnsmasq can act not only as DNS server, but also as a DHCP server. This
setup was a simulation to show you what you can do with dnsmasq. As mentioned
earlier, in real life you would have this on separate machines physical or
virtual. If you want to test a set-up like this, you'd normally do that on a
separate network from the production network. Remember, never test in
production. We caught a lot of information in this module. You've learned about
the overall services needed an IT infrastructure. On top of that, you learned
about the physical infrastructure services like remote access and virtualization
that help your organization run more efficiently. You even learn about essential
network services like DNS and DHCP along with the overall picture of what's
needed to set up DNS for normalization, and why you'd want to do that. We've
seen most of the services in action. Now, we're going to let you practice with
some quick lab exercises and test you on what you've learned. Don't forget you
can always go back and review the material again if you want before you take the
quiz. In the next module, we're going to cover two of the other IT
infrastructure services; software and platform services. I'll see you there.