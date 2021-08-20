In large enterprise deployments, you probably have different programs serving
each of the networking services that we covered in this module. In smaller
set-ups you may be better off having a centralized solution that handles all
services. Let's look at dnsmasq; a program that provides DNS, DHCP, TFTP and PXE
services in a simple package. This will let us do some hands on configuration of
these services even if it's not as complex as other networking solutions. Let's
start by installing dnsmasq in this machine. So, I'm going to type in sudo apt
get install dnsmasq. Once we've installed dnsmasq it's immediately enabled with
the most basic functionality. It provides a cache for DNS queries. This means
that you can make DNS requests to it, and you'll remember the answer so your
machine doesn't need to ask an external DNS survey each time you make the query.
In order to check this functionality, we'll use the dig command, which lets us
query DNS servers and see their answers. So, let's ask our DNS server running in
local host for the address of www.example.com. We do this by running dig
www.example.com @localhost. The part after the at sign indicates which DNS
server we want to use. Here, we have the reply from our query. Our DNS server is
telling us the IP address for the domain example.com. How do we know that this
query was actually answered by the service the machine is running? We can run
the service in debug mode so we get more information about what's going on
behind the scenes. This isn't how you would normally run the service, but it's
useful for understanding what's happening. So, let's stop the dnsmasq service
that's running, and then start it in debug mode. So now, I'm going to type in
sudo service dnsmasq stop, then type in sudo dnsmasq the -d and then pass the
-q. By passing d and q, we're telling dnsmasq that we want to run it in debug
mode and that we wanted to log the queries that we execute. When it starts, it
prints in the compilation options that are enabled and the configuration files
that are used. Now, we can query again with our friendly dig command. If we run
the command again, we will get the same answer and we'll see the debug output in
the dnsmasq console. So, in my second console now, I'm going to go ahead and
type in dig www.example.com @localhost. This is showing us that our dnsmasq
service received the query, forward it to the configure DNS server and then
reply to the original machine. If we query for the same host name again, we'll
see that instead of asking the other DNS server, dnsmasq replies with the cached
query. So now my second console. I'm going to type in, again, dig
www.example.com @localhost. So, if I hit enter, for now a dnsmasq is operating
as a simple caching DNS server. But we can make it do more than that. For
example, we can give it a list of host names and IPs and had this service give
authoritative answers for them. You might remember that when trying to resolve a
host name to an IP, they can be servers that store the information about the
mappings, which can then provide the authoritative answers while other servers
will only be able to forward and delegate the queries to the server that had the
information. These files have the same format as the exe host file. I created
this file that lists the internal host that I want to be able to resolve. So,
I'm going to type in cat myhosts. As you see, it's a very simple format. You
just had to list which IP is associated with each host. We use the h parameter
to tell us dnsmasq that we want to include this list in the information being
served. So, I'm going to cancel this, clear and I'm going to type in sudo
dnsmasq -d -q -H myhosts. Now that we have our list of host loaded, let's query
with dig. So now, my second console. I'm going to type in dig oxygen.local
@localhost. As dnsmasq is authoritative about this host, there's nobody to
forward the question to. It also lists which file is using to get the
information need. Finally let's see what the output looks like when we ask for
information that it doesn't have. So I'm going to type in dig hydrogen.local
@localhost. We see that it replied that the authoritative service are the root
servers but that I couldn't find any results. What did the running dnsmasq say?
Since the requested name isn't in the list of hosts known to our DNS server, it
forwarded the query to the configure DNS server. The reply for that was NXDOMAIN
which means none existent domain.While dnsmasq is as simple as it gets, you've
now seen what a DNS server looks like in action. Cool, right?