You might remember that we can use a web server to store and serve content
declines that request our services. We'll probably want to store website content
on our web server. If clients want to reach our website, we need to set up DNS
so that they can just type a URL to find us. So, let's talk about how DNS gets
set up for a website. First, we need a domain name. We can buy a domain name
like SettingUpDNSIsFun.example.com. We can purchase domain names like this from
companies called domain registrars, like GoDaddy.com, or BluHost.com. Once we
have our domain name, we want to point our website files to this domain name.
Our website files can be stored on a cloud hosting provider, or we can decide to
control this ourselves and store it on our own servers. Typically, domain
registrars also provide cloud hosting services but they can charge you a monthly
fee to host your web files for you. Protip, if you don't want to utilize cloud
hosting services, you can just run your own web server. Don't forget, there are
always pros and cons to hosting a service yourself or offshoring it somewhere
else. If you're the sole IT support specialist for an organization, make sure to
weigh all your options before committing to an infrastructure service. Let's
assume that we do want to host our website files ourselves. From here, we still
need to point our new domain name to where web content is located. We can do
this in two ways. Most domain registrars can provide you with DNS settings and
you can give the IP address of where your content is stored. If you decide not
to use your domain registrar to host DNS for you, then you have to set up an
authoritative DNS server for your website. Remember from our discussion in
course 2 that authority DNS servers are the DNS servers that know exactly what
the IP address is for the domain name. Since we own the domain name and host our
web content ourselves, it makes sense for us to have the DNS servers that know
that information.