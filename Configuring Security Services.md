The last software services that
we'll discuss are security services. Security is super important
to all organizations. It's integrated into pretty much all
aspects of an IT infrastructure service. We'll dive deeper into this in
the last course on IT security. For now, remember that there are lots of
different security protocols that are put in place for all sorts of things, keeping
data encrypted, authentication, etc. If you ever manage a web server
that serves content to other users, you want to let them know that
when they access your website, you're keeping their interaction
with you as secure as possible. Let's say that you have an online bank
account that you're logging into. The URL will most likely
begin with an HTTPS. Remember that HTTP stands for
HyperText Transfer Protocol, which is used to format and
transfer web content around the Internet. When you enter in a URL, you notice
that HTTP comes before everything else. HTTPS, or Hypertext Transfer Protocol
Secure is a secure version of HTTP. It makes sure the communication your web
browser has with the website is secured through encryption. HTTPS is also referred to as HTTP over TLS or HTTP over SSL. This is because there are two protocols
that enables us to make our web servers secure. The first is Transport Layer Security
protocol, or TLS, which is the most popular way to keep
communications secure over a network. TLS is widely used to keep
web browsing secure, but it can be used in a lot of
other applications, too. We'll do a deep dive into the technical
details of TLS in a later course. The second protocol is
Secure Socket Layer protocol, or SSL. It's a way of securing communication
between a web server and client. But it's pretty old and insecure, so
it's been deprecated in favor of TLS. You may still see it today being used
over the TLS protocol like SSL/TLS. The two protocols are often
used interchangeably. In fact, SSL version 3.0,
was essentially TLS version 1.0. But TLS's new features and
updates have made it more secure than SSL. So if you're managing
an organization's website on a server, how do you enable TLS on the server so
that the site can be using HTTPS? Well, you need to get a digital
certificate of trust from an entity called a certificate authority. The certificate authority grants a
certificate to your website saying that it trusts that you control the web server. And verifies that you
are who you say you are. Once it does that, you can install
the certificate on your web server. That way, when users visit your site, they'll see the HTTPS in
the URL instead of just HTTP. You'll learn more about certificates and certificate authorities
in an upcoming course. For now, think of certificates as a way
to verify that something is trustworthy. Security is an integral part of IT, and it's not just the responsibility
of security engineers. Everyone should be
thinking about security. And all layers of your
infrastructure should have a layer of security built upon them. There are lots of other security
software that you can add to your IT infrastructure,
which we'll dive into in the last course. For now, it's a good idea to know the basics of
keeping a web server secure with HTTPS.