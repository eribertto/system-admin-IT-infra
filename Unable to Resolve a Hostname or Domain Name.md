There will be times when you're working in an IT support role and you won't be
able to resolve or get the IP address of a website name. This particular problem
could be tricky to identify when you see it. You might just think that your
network connection isn't working. Let's go ahead and try to navigate Google.com
from our web browser. So let me get to my webrowser and navigate to Google.com.
It doesn't look we get to Google.com. Let's go over some of the tools that we
learned in our networking class that can help. First off, if you're unable to
resolve a domain name, check that your network connection is actually working.
You can do a quick check and ping a website that you know is available. An oldie
but goodie is to ping www.google.com. It's pretty rare that Google would be
down, although it can happen. So let me go into my terminal and type in ping
www.google.com. Looks like we're getting responses. Let's move on to isolating
another problem, DNS. To verify that your DNS server is giving you a correct
address for google.com, you can use nslookup. Remember that nslookup gives us
the name server of a host or domain name, so let me go ahead and do that on my
terminal. From here, we can rule out if DNS isn't issued by verifying that the
host name points to a name server. If we copy the IP address of the result and
paste it into the web browser, it should resolve the website name if DNS is
working. Let's go ahead and do that. So I'm going to go ahead and copy the
non-authoritative IP address. Open my web browser So I see that's working.
What's going on? It looks like my DNS settings aren't working correctly. Let's
look at my ping results again. So I'm going to go ahead to my terminal and ping
www.google.com. I see that it checks an IP address different from what I have
here. If I go to this IP address, it doesn't take me anywhere. So I'm going to
take this IP address, copy this. Remember that when a DNS query is performed,
your computer first checks host file. Now if I access my host file here, I can
see that I have an entry for www.google.com. And it points to a fake IP address.
If I remove this line right here where it says 127.1.1.3 And save that
configuration file, And then restart my browser, If I type in www.google.com,
there we go, we're there. And the correct DNS setting should be applied to
www.google.com. There are some situations where DNS can be tricky to navigate,
since there can be many contributing factors. But as with any troubleshooting
scenario, remember to keep isolating the problem down until you can get to a
root cause. With time and experience, you'll learn a lot more about DNS and how
to troubleshoot it in the real world.