Let's start by defining what we mean by production. In an infrastructure
context, we call the parts of the infrastructure where certain services are
executed and serve to its users production. If you host a website, the service
that deliver the website content to the users are the production servers. Inside
your company, the servers that validate users' passwords are the production
authentication servers. You get the idea. So let's say, you need to make an
important change in your production infrastructure. It could be adding a new
service, changing the configuration of an existing service, updating the
operating system or maybe shutting down the service that's currently running.
How do you go about doing that? The key to safely making these changes is to
always run them through a test environment first. The test environment is
usually a virtual machine running the same configuration as a production
environment, but isn't actually serving any users of the service? This way, if
there's a problem when deploying the change, you'll be able to fix it without
the user seeing it. If you're in charge of an important service that you need to
keep running during a configuration change, we recommend that you have a
secondary or a stand-by machine. This machine will be exactly the same as a
production machine, but won't receive any traffic from actual users until you
enable it to do so. In this case, once you've tested your changes in the test
environment and are ready to deploy them to production, first, apply the changes
to the secondary machine. Once the changes have been applied, make the stand-by
machine and primary machine, and then apply the changes to the other machine.
For even bigger services, when you have lots of servers providing the service,
you may want to have canaries. Similar to the canary of coal miners carry to
detect toxic gases when entering the mines, you'll use a small group of servers
to detect any potential issues in the larger changes you want to push out in the
system. Once you verify that it works correctly on those machines, you then
deploy the change to the rest of the fleet. That way, if there's an issue with
the change, only a subset of the users get exposed to it, and you can roll it
back before it hits everyone. Now, let's say you need to make a minor change in
your production infrastructure; should you just go ahead and make the change in
production? No, you should always try it in your test infrastructure first. It
doesn't matter how minor the change may seem; there's always something that
could go wrong. Whether the infrastructure needs primary and secondary machines
or a group of canaries depends on how big the services and how important it is
that it doesn't go down. Even for the smallest services, you should never make
changes directly in production. Always use a test instance first and only deploy
the change to production after verifying that it works.