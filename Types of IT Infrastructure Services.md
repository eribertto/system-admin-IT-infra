There are lots of types of IT infrastructure services out there. We'll start by
giving you a high level overview of them in this lesson, then we'll dive into
the nitty gritty details on how you configure and maintain these services and
later lessons. Sounds good? Let's get started. We talked about physical
infrastructure components of an IT environment in an earlier lesson. Remember
that you can set up different servers to run your services on, like a server to
run your file storage service. You can buy or rent hardware for these servers
and set up and store them either on-site, or at another location. Essentially,
you manage these servers end-to-end. There's another option. If you don't want
to be responsible for managing the hardware tasks and updating your server
operating systems security patches and updates, you can use the Cloud
alternative to maintain your own infrastructure, which is called Infrastructure
as a Service, or IaaS. IaaS providers give you pre-configured virtual machines
that you can use just as if you had a physical server. Some popular IaaS
providers are, Amazon Web Services and their Elastic Compute Cloud or EC2
instances, Linode, which runs out virtual servers, Windows Azure, and Google
Compute Engine, which you've been using throughout this course. You can read
more about the different IaaS providers in the supplemental reading right after
this video. Your company's internal network, isn't going to be like your network
at home. You're going to have multiple computers that need to be on a certain
subnet. You have to assign them IP addresses statically or using DHCP. The
networking hardware has to be set up, wireless internet will probably need to be
available, DNS needs to be working et cetera. If your company is large,
networking is usually taken care of by a dedicated team. But in smaller
companies, you'll probably be responsible for setting up the network. Network
can be integrated in an IaaS provider, but in recent years, it's also been
branched off into its own Cloud service, Networking as a Service or NaaS. NaaS
allows companies to offshore their networking services so that they don't have
to deal with the expensive networking hardware. Companies also won't have to set
up their own network security, manage their own routing, set up a WAN and
private internets, and so on. For more about NaaS providers, check out the
supplemental reading. Let's talk about the software that your company might want
to use. Do you need to type out word documents, use an email client, communicate
with other people, use operating systems, process spreadsheets or have any of
other software needed to run a business? I bet yes. The right software has to be
available to your company's users. We've already discussed how to install and
maintain software in machines. You have to deal with things like licences,
security, updates, and maintenance for each machine. The Cloud alternative to
maintaining your own software is known as Software as a Service, or SaaS.
Instead of installing a word processor on every machine, you can use Microsoft
Office 365 or Google G suite. These are both services that you can purchase that
allow you to edit word documents, process spreadsheets, make presentations and
more, all from a web browser. You can check out the next supplemental reading
for more about SaaS providers. Some companies have a product built around a
software application. In this case, there is some things that software
developers need to be able to code, build and shape their software. First,
specific applications have to be installed for their programming development
environment. Then, depending on the product, they might need a database to store
information. Finally, if they're serving web content like a website, they'll
need to publish their product on the internet. If you're building this entire
pipeline yourself, you may need to set up a database and a web server. The
programming development environment will also have to be installed on every
machine that needs it. If you want an all-in-one solution to building and
deploying a web application, you can use something called Platform as a Service,
or PaaS. This includes an entire platform that allows you to build code, store
information in a database, and serve your application from a single platform.
Popular options for PaaS are, Heroku, Windows Azure, and Google App Engine. As
you might have guessed, you can read more about PaaS providers in the
supplemental reading. The last IT infrastructure service we'll discuss is the
management of users, access and authorization. A directory service, centralizes
your organizations users and computers in one location so that you can add,
update, and remove users and computers. Some popular directory services that you
can set up are Windows Active Directory, OpenLDAP, and we'll dive a little
deeper into both of these later on in this course. Directory services can also
be deployed in the Cloud using Directory as a Service, or DaaS providers. Guess
we can read more about DaaS providers. That's right, in the supplemental
reading. There you have it. This is a general overview of the most common IT
infrastructure services you'll encounter when handling system administration
tasks. While Cloud Services are a great option, it's super important that you
understand how a service works and how to maintain before you employ the help of
a Cloud Service. Even though Cloud Service are widely used in the industry, and
have a lot of pros, there are also some cons. These include recurring cost, and
the need to depend on the providers service. We're going to teach you about the
technical details and the implementation of these common IT infrastructure
services. We'll cover everything from setting up your own server, and figuring
out which applications you need to be productive, to how to set up multiple
users and get your network services in order. By the end of this course, you'll
have the foundational knowledge required to set up the IT infrastructure, for a
small organization.