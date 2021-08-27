So, what exactly goes into an effective disaster recovery plan? Well, it
depends. Keep in mind, there's no one-size-fits-all for disaster recovery plans.
The mechanisms chosen and procedures put in place will depend a lot on the
specifics of your organization and environment. But we can't start by covering
the three types of measures in more detail. We'll also go over some examples to
help give you an idea of what to think about. A good way to understand what to
plan for is to perform a risk assessment. This involves taking a long hard look
at the operations and characteristics of your teams. A risk assessment allows
you to prioritize certain aspects of the organizations that are more at risk if
there's an unforeseen event. Risk assessment can involve brainstorming
hypothetical scenarios and analyzing these events to understand how they'd
impact your organization and operations. When you look into preventive measures,
pay attention to systems that lack redundancy. If it's something critical to
permit operations, they should probably have a redundant spare, just in case.
Make sure you have a sound backup and a recovery system, along with a good
strategy in place. Ideally, you should have regular but automated backups to
backup systems located both on site and off site. It's also critical that you
have data recovery procedures clearly documented and kept up-to-date. Data
recovery following a disaster is hopefully something you will rarely do. It's
important to make sure that these procedures are updated since systems change
and evolve throughout their lifetime. Redundancies shouldn't be limited only to
systems. Anything critical to operations should be made redundant whenever
possible. This includes power delivery or supply, communications systems, data
links, and hardware. Think through the impacts that a disaster affecting each of
these aspects would have on your day-to-day operations. What would happen to
your network if the building lost power? Can you use continue to work at the
fiber-optic data line if the building gets damaged by a nearby construction
work? You call router for the office just burst into flames. Okay. The last one
is a little far-fetched, but I think you get where I'm going. Another super
important preventive measure that should be evaluated and verified is
operational documentation. Make sure that every important operational procedure
is documented and accessible. This includes things like setting up and
configuring critical systems and infrastructure. Any steps or specific
configuration details that are needed to restore 100 percent functionality to
core systems and services should be documented in detail. It's also important
that this documentation is kept up-to-date. An effective way to do this is
periodically verify that the steps documented actually work. You don't want to
find yourself in a situation where you need to reconfigure assistant following
incident, only to discover that the documentation is wrong. When looking at
detection measures, you'll want to make sure you have a comprehensive system in
place that can quickly detect and alert you to service outages or abnormal
environmental conditions. If up-time and availability is important for your
organization, you'll likely have two internet connections; a primary and a
secondary. You want to monitor the connection status of both of these links.
Ideally, they should be configured to automatically fail over if one goes down.
But you'll still want to be alerted when this happens, so you can investigate
why the link went down and work on getting it back as soon as possible. The way
to think about designing detection measures is to evaluate what's most critical
to the day-to-day functioning of the organization. What infrastructure services
and access are absolutely vital? Those are the ones you should be closely
monitoring. And it's not just outages or complete failures you should be
watching for. Of course, you want to monitor for those, but you also want to
monitor for conditions that indicate that a problem is likely to occur. If we
can avoid a catastrophic failure by being alerted to an overheating server
before it fails, that would be much better, wouldn't it? So, you want to monitor
conditions of service and infrastructure equipment. Things like temperatures,
CPU load and network load for a service monitoring for error rates and requests
per second will give you insight into the performance of the system. You should
investigate any unusual spikes or unexpected increases. These early warning
systems allow you to head off disaster before it brings operations to a halt.
And of course, you absolutely must test these systems. Simulate the conditions
your monitoring systems are designed to catch. Make sure the detection
thresholds actually fire the alerts like they're supposed to. This testing goes
beyond just the monitoring systems too. You'll also want to test your reactions
and responses to these alerts. If you're monitoring systems reliably trigger
alerts but everyone just ignores them, they aren't super useful, are they? You
want to conduct regular disaster test to make sure systems are functioning and
that your procedures to handle them are also up to the task. Corrective or
recovery measures include actions that are taken to restore normal operations
and to recover from an incident or outage. This includes taps like restoring a
corrupted database from a backup or rebuilding and re-configuring a server. Your
disaster plan should include reference or links to documentation for these types
of tasks. Anything and everything that would be required to restore normal
operations following some disaster. This is where the steps for restoring
various systems and data from backups should be. The disaster recovery doc
doesn't need to contain the details of the operations. Links and references are
sufficient. But it's important to be prepared for a situation where typical
documentation acts methods are unavailable. Let's imagine you keep all your
operational documentation in a wiki on a dedicated server. What happens when
that server suffers an outage? It's important that critical documentation is
accessible if an emergency scenario or disaster strikes. In the next lesson,
we'll cover what to do after a failure. See you there.