Platform services provide a platform for developers to completely build and
deploy software applications, without having to deal with OS maintenance, server
hardware, networking or other services that are needed to use the platform
tools. A web server that we deploy our web applications to, or the development
software that we use to code our applications are both examples of platform
services. In this day and age. Most businesses have a digital presence. Whether
that's a Web site that promotes their business, or even a website that is their
business. Businesses that run web services keep their services stored on a web
server. A web server stores and serves content to clients through the Internet.
You can access web service using a domain name like Google dot com. A web server
itself stores web files and runs an HTTP service or HTTP server, that processes
HTTP requests. Remember that HTTP is how the Web formats and transfer's web
pages. You can think of the web server as the physical server that stores with
files and the HTTP server software. When your web browser makes a request to
fetch a web page from a URL, it sends an HTTP request that gets processed by the
HTTP server. Then the HTTP server sends out and HTTP response with the content
that you requested. There are a lot of popular HTTP server software out there.
But the most widely used is the Apache HTTP server, most commonly referred to as
Apache. Apache is a free and open source. It helps serve a large percentage of
web pages on the Internet. Let's actually see how a web server serves content to
the Web. I'm going to install the Apache Web server software or my Linux
computer here. You don't have to understand the specifics of the setup. I just
want you to see how easy it is to run a web service. So, let me go ahead and
install Apache. So, I'm going to go ahead and do "sudo apt-get install apache2"
and then hit the flag. Yes to accept. All my packages. Perfect. Now I will web
server services running on our machine. We're actually able to start hosting web
content. The machine that we're hosting our content on is well, this machine
right here. Remember that our computer has an IP address that's associated with
itself 1 2 7 0 0 dot 1 or a hostname of localhost. Localhost itself is reserved
for this purpose. So, it's not possible to get the domain name localhost. So,
now that we know our machines location, lets enter it to the web browser. And
here it is, our local web server content running on our machine. The files we
see here, come with the default Apache installation. But if we want to upload
our own web content, you can just navigate to the directory where this is
stored, and replace it with our web content. Remember, that since this contemn
is hosted on our local machine. We will need to use DNS to let the world know
that our web server exists. If you need a refresher on this, feel free to go
back to the lesson on DNS services. That's a quick rundown of how web servers
work. You can read more about Apache and other HTTP servers in the next
supplemental reading. System administrators aren't responsible for creating the
content that gets served. But they might be responsible for making sure that
content is available. If you're an IT support specialist with a web service that
needs to be manage, you should have a pretty good understanding of how it works.