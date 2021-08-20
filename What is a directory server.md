Have you ever looked up someone's phone number in a phone directory? Or use a
directory listing at a shopping mall to find a specific store? A directory
server essentially provides the same functionality. A directory server contains
a lookup service that provides mapping between network resources and then
network addresses. It's used to organize and look up organizational objects and
entities ranging from things like user accounts, user groups, telephone numbers,
and network shares. Instead of managing user accounts and computer information
locally on every machine, all that information can be stored on a directory
server for easy access and management. The ideal enterprise quality directory
server should support replication. This means that the store directory data can
be copied and distributed across a number of physically distributed servers but
still appear as one unified data store for querying and administering. Why is
replication important? It provides redundancy by having multiple servers
available simultaneously. So there'll be minimal disruption to the service in
the event that one of server explodes. Replication also decreases latency when
you access the directory service. By having replicas of your directory server
located in each office, you're able to answer directory service queries more
quickly. The directory service should also be flexible, allowing you to easily
create new object types as your needs change. Access to the information stored
in the directory server database should be accessible from a variety of OS types
and from the designated areas of the corporate network. Directory services are
useful for organizing data and making it searchable for an organization. This is
achieved through the use of a hierarchal model of objects and containers. The
containers are referred to as organizational units or OUs, and they can contain
objects or more organizational units. This is similar in organizational
structure to a file system. OUs are like folders which can contain individual
files or objects for a directory service. OUs can also contain additional
folders. The management benefits of this structure are pretty clear. Can you
imagine trying to keep your music library organized if there was no such thing
as subfolders? Crazy. This hierarchal structure can be used to convey additional
information about what's stored within. Take your directory structure as an
example. You may have an OU code users which contains all user accounts. Within
this OU, there could be additional OUs which represent the actual team structure
of your organization. The user's OU could contain additional OUs like sales,
engineering, marketing which include the user account objects for the
individuals that belong to these current teams. This structure can be used to
convey differences between these sub-OU sub-users. For example, we could
influence stricter password requirements for members of engineering without
affecting sales or marketing. Submembers inherit their characteristics of their
parent OU. So any changes made to the higher level user's OU would affect all
sub-OUs, including sales, marketing, and engineering. Someone with the
responsibilities of a systems administrator, whether that's a system admin or
I.T. support specialist, would be responsible for the set up, configuration, and
maintenance of the directory server. This includes the OS itself on which the
directory service would run. Standard OS management tasks are involved here,
like ensuring that updates are installed and configuring standard services.
Other responsibilities include the installation and configuration of the
directory service itself. So installing the service and configuring any related
services. If multiple servers are used in a replication setup, this needs to be
configured, too. It's very likely that the hierarchy in overall structure of the
directory itself would also be up to the sysadmin to design and implement. Well,
that covers the high level overview of what exactly a director service is. We'll
dive deep into more specific details later in this course. But for now, let's
review some of the concepts we just covered with a short quiz. Then let's meet
back at the next video where we'll do a more detailed rundown on how to
implement directory services.