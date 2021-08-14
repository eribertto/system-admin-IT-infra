We've mentioned before that you should always test your changes before
deploying. Document what you do and have a way to revert to the previous state.
The amount of time and effort you invest in each of these steps depends on the
risk involved. You should always have a test instance for trying out changes.
But it might not be worth having a secondary server if nobody cares about
downtime. So, how do you decide how much time and effort to invest? We can
assess the risk involved by considering how important the services to the
infrastructure and how many users would be impacted if the service went down.
Certain services are mission critical. If the centralized authentication system
is down, no one will ever be able to log in. If the billing system is
unreachable, the company won't be able to receive payments. If your backups are
lost, you have no safeguards in the event of a disaster. But not all services
are mission critical. An informational website isn't as critical as an
e-commerce site. An internal ticket system isn't as critical as an external
customer support application. The infrastructure needed for a new installation
isn't as critical as the one used for logging into existing machines. In
general, the more users your service reaches, the more you'll want to ensure
that changes aren't disruptive. The more important your service is to your
company's operations, the more you'll work to keep the service up. You may have
a user agreement about the expectation of a service availability. For example,
in lots of companies, disruptive maintenance is performed on the weekend. In
these cases, it's agreed that it's fine if the main file server is down on
Saturday while you make any changes. You can also use these criteria to
establish priorities for fixing a problem. If the problem is preventing people
from doing their work, finding a solution to it should have a higher priority
than solving a minor annoyance that can be worked around.