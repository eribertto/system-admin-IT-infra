Let's say you have a web server providing a website to clients. In a typical
setup for this kind of service running in a cloud, a number of virtual machines
will be serving this same website. A load balancer ensures that each VM receives
a balanced number of queries. Whenever there's a request for your website, a
different VM will be picked to serve the response. These types of services are
usually configured to spin out more virtual machines when there are lot of
queries. And to shut down some of the VMs when the number of queries goes down.
This capability is called autoscaling. It allows the service to increase or
reduce capacity as needed, while the service owner only pays for the cost of the
machines that are in use at any given time. Since some machines will shut down
when the demand is lower, then local disks will also disappear and should be
considered ephemeral or short-lived. If you need data persistence, you have to
create separate storage resources to hold that data and connect that storage to
the VMs. Usually, VMs operating websites or web services are connected to a
database, also running in the cloud. This database is also served by multiple
machines behind a load balancer. But this is managed by the cloud provider, and
doesn't concern the cloud user. To make sure the service is running smoothly,
you can set up monitoring and alerting. When you do this, you can detect and
correct any problems with your service before your users even notice. Most cloud
providers include monitoring and alerting solutions as part of their services.
You can configure when and how you want to be alerted if the monitoring
infrastructure detects performance issues. It may seem tricky to set up cloud
resources, but most providers make them easy to configure. We've also included
some additional information in the supplemental reading to help you along.