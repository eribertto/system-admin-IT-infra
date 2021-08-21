Directory services became an open network standard for interoperability among
different software vendors. In 1988, the X.500 directory standard was approved
and included protocols like Directory Access Protocol or DAP, Directory System
Protocol or DSP, Directory Information Shadowing Protocol or DISP, and Directory
Operational Bindings Management Protocol or DOP. Alternatives to DAP were
designed to allow clients to access the X.500 directory. The most popular of
these alternatives was lightweight directory access protocol or LDAP. Since
these are open standards for communication and access for directory services, a
bunch of different implementations of these services cropped up. There are
offerings from Apache, Oracle, IBM, and Red Hat, but we'll cover two in more
detail later in this module. The first is Microsoft's implementation, which is
referred to as Active Directory or AD. It has some customization and added
features for the Windows platform. There are also open source implementations of
directory services using LDAP. A popular example of this is OpenLDAP, which
we'll also cover in greater detail. OpenLDAP supports a wide range of platforms
like Windows, Unix, Linux and various Unix derivatives. In addition to the
server software, there are also client tools used for accessing and
administering a directory server, Microsoft Office Active Directory Users and
Computers or ADUC, which works well with Microsoft Active Directory Server.
There are also other more open tools that can be used to interface with a lot of
other directory server implementations. Along with clients for administering and
managing a directory server, there are also client applications that can
interface with and query a directory server. All major OS platforms support
integrating into a directory server for log in and authentication purposes. The
advantage here is that this allows for centralized management of user accounts.
We'll cover the details of centralized management in the next lesson, so don't
worry too much about that right now. When looking at specific implementations
for your directory server, you'll want to consider OS support, not just the
server they'll be running the directory service itself, but also what OS is your
client fleet runs and the compatibility or support for you directory services.
You can read more about why this is important in the next reading.