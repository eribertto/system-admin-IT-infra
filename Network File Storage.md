In the last course, we mentioned that very few file systems can be used across
all major operating systems. FAT32 is a popular FAT system that's compatible
with Windows, Linux, and Mac OSes. But it has severe limitations on the amount
of data you can store on a volume. What happens if you have multiple users that
want to share files between each other? Well, they need to store the files
somewhere and they need to be able to retrieve the files over a network. Network
file system, or NFS, allows us to do this. It's a protocol that enables files to
be shared over a network. The FAT system is compatible on all major operating
systems. The easiest way to setup an NFS server is by using a Linux environment.
You can install NFS server software that modify the configuration files for the
directories that you want to allow shared access to. Once you do that, the NFS
service will be running in the background of the server. On each client machine
that wants to access a server, you just mount the file system the way you would
any other file system. Except, you'd use the host name instead of a physical
disk device. From there, you can access the shared directory like you would any
other folder in a computer. Check out the next supplementary reading for some
examples of NFS server software you can configure for Linux. NFS is a good
solution to file sharing within the network, but as with anything on a network
heavy usage will slow down the file system. While NFS works with all major
operating systems there are still interoperability issues with Windows. If your
fleet consists mostly of Windows machines you might want to look at using
something like Samba. Samba services are similar to NFS since she can centrally
share and manage files services. Also, all major operating systems can use a
Samba file sharing. The only reason you might want to consider Samba over NFS,
is because it works better with Windows operating systems. It also includes
other services that can be integrated with your organization like printer
services, we'll talk about printer services in an upcoming lesson. One thing to
note is that, you may hear the term Samba or SMB. These two are differen. SMB is
a protocol that Samba implements. You can read more about SMB in the
supplemental reading. Fun fact, when you create a Windows shared folder it's
actually using the SMB protocol, Samba itself is a software service suite used
for file services which you can also read more about in the supplemental
reading. There are lots of other file storage services that you can use and you
can read more about them in, wait for it, the supplemental readings. A
relatively affordable solution for FAT storage hardware is to use a network
attached storage or NAS, pronounced NAS. Instead of setting up a dedicated
server like you would other services. NASes are computers that are optimized for
file storage. They usually come with an operating system best stripped down in
order just to serve files over a network. They also come with lots of storage
space. Whatever method you choose, central file storage and management is an
important part of I.T. infrastructure for any organization.