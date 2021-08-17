Web servers, and servers in general,
are prone to breakage, just like any other machine. Troubleshooting a web server can
involve lots of different variables. We won't discuss a specific
troubleshooting scenario in this lesson, but we'll talk about some easy
trouble shooting tools you can use to diagnose a faulty web server or
browser called HTTP status codes. When we want to go to Google.com our
browser is sending an HTTP request to the HTTP server on the web server. In turn we get an HTTP response. Sometimes this response returns
the content that we want. Almost all the time it'll return
a status message of the response. HTTP status codes are codes or numbers
that indicate some sort of error or info messages that occurred when
trying to access a web resource. Knowing common HTTP status
code comes in handy when you're troubleshooting website error. They usually tell you useful information
that can help you isolate the root cause. Here's a common HTTP status
code you might recognized. The dreaded 404 Not Found A 404 error indicates that the URL you entered
doesn't point to anything. Let's see what happens if I type in
google.com/asdf, let's type that in. I get this error message. The requested URL /asdf was
not found on this server. That is exactly what I expected to happen. I typed in an address, I knew didn't exist
and the website confirmed it for me. But, how do we know it
is a 404 error code? Depending on the website HTTP error
messages could be displayed right on the page when you try to access it. However, to be absolutely sure you can
just view the HTTP response itself. To do that we'll have to do a bit of work. Browsers today have built in tools that
help people diagnose issues with the web browser or website itself. Since I'm using Chrome, I'm going to use a Chrome Developer Tools,
let me go ahead and do that. So, I want to click on this,
I get into tools. And then click on Developer Tools. This will open up the Developer Tools
side by side to my web browser. Developer Tools is a great resource for
testing and debugging issues with the website or
browser. We won't go through this tool, though. If you want to learn more, you can
check out the supplemental reading. For now, we just want to
see the HTTP response code. To get to that, I'm going to go to
the network type here and refresh my page. If I'm trying to go to google.com/asdf, I'll see the request I made
in the left hand side here. If I clicked that, I'll see
the status codes says 404 not found, pretty neat, right? HTTP status codes that start with 4xx
indicate an issue on the client-side. The client try to do something that
it couldn't, like enter a bad URL. Access something it was
not authorized to do, etc. The other common HTTP status codes
that you might see start with 5xx. These errors indicate
an issue on the server-side. The web server that hosts this web
content is experiencing issues and hopefully their server
administrators are looking into it. HTTP status codes tell us
more than just errors. They can also tell us when
our request is successful, which is denoted by the codes
that begin with 2xx. HTTP status codes can tell us a lot
about an issue with a website. If you encounter one you aren't
familiar with, just look it up. They will probably tell you
exactly what the issue is. For a list of HTTP status code,
take a look at the supplemental reading.