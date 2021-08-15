We discussed virtual machines
in the last course and covered how to set up a virtual
machine on a personal computer. In this lesson we're going to talk
about why virtualization can be an important part of infrastructure
services and systems administration. There are two ways you can run your
services, either on dedicated hardware or on a virtualized instance on a server. When you virtualize a server you're
putting lots of virtual instances on one server. Each instance contains a service. There are a bunch of pros and cons to running your services
on either of these platforms. Here's the rundown. Performance, a service running
on dedicated hardware will have better performance than a service
running in a virtualized environment. This is because you only have
one service using one machine as opposed to many services
using one machine. Cost, server hardware
can be pretty expensive. If you put a service on one
piece of dedicated hardware and have to do that for nine other services,
it starts to add up. One of the huge benefits to virtualizing
your service is that you can have ten services running on ten different virtual
instances, all on one physical server. Here's another way to think about this, in a typical server if you only have one
service running it's probably only taking up 10-20% of your CP utilization, the rest
of the hardware isn't being utilized. You can add plenty more services
to the physical server and still have a good threshold for
resource utilization. It's cheaper to run several services
on one machine than it is to run many services on multiple machines. Maintenance, servers require
hardware maintenance and routine operating system updates. Sometimes you need to take the servers
offline to do that maintenance. With virtualized service, you can quickly
stop your service or migrate them to another physical server, then take as
much time as you need for maintenance. Virtualized service makes server
maintenance much easier to do. Points of failure, when you put
a service on one physical machine and that machine has issues,
you're entering a world of trouble. With virtualized service, you can easily
move services off a physical machine and spin up the same service on
a different machine as a backup. You could also do this with
a physical server, but that could become costly if you
account for multiple service. Pro tip, you can prevent a single point
of failure on a physical machine if you have redundant servers set up, meaning
you have duplicate servers as a backup. You will learn about backups
in the upcoming module. As you can see there are lots of
benefits to using virtualized servers, just make sure to weigh the pros and
cons of visualising your service and using dedicated server hardware,
that way you can make the right choice for your company.