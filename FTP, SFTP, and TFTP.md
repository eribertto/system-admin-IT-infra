Now that we're a little more familiar with some of the common aspects of
physical infrastructure, let's move onto network services. A network service
that's commonly used in organization is a file transfer service. So why would
you want to have a service dedicated to file transfer? Well, sure, you could
probably carry around a flash drive and copy files to each machine you work on
or even use a remote copy tools we learned in the last course, or you could
essentially store huge files and transfer files from one computer to another
using the Internet. There are a few different file transfer protocol services
that are used today. Let's take a quick rundown of what's out there and what
they do. FTP, in the second course of this program the, bits and bytes of
computer networking, we mentioned FTP a.k.a the file transfer protocol. It's a
legacy way to transfer files from one computer to another over the Internet, and
it's still in use today. It's not a super secure way to transfer data because it
doesn't handle data encryption. The FTP service works much like RSH service.
Clients that want to access an FTP server have to install an FTP client. On the
FTP server, we install the software that allows us to share information located
in the directory on that server. FTP is primarily used today to share web
content. If you use a website host provider, you might see that they have an FTP
connection already available for use so they can easily copy files to and from
your web site. SFTP, it's a secure version of FTP, so it makes sense to choose
this option over FTP. During this SFTP process, data is sent through SSH and is
encrypted. TFTP stands for trivial FTP. It's a simpler way to transfer files
than using FTP. TFTP doesn't require user authentication like FTP, so any files
that you store here should be generic and not need to be secure. A popular use
of TFTP is to host installation files. One method of booting a computer that we
haven't discussed yet is PXE or PXE boot, which stands for preboot execution.
This allows you to boot into a software that's available over the network. A
common use case for organization that want to install software over a network is
to keep operating system installation files in a TFTP server. That way, when you
perform a network boot, you can be automatically launched into the installer.
This is a lot more efficient than having to carry around a USB with an operating
system image. You can learn more about PXE boot in the next reading. Depending
on your usage of file transferring services, you might want to weigh the option
we mentioned. We encourage you to read about popular FTP clients using the
supplemental reading. If you just want to share files between your computers in
a secure way and have a nice directory where you can access all the shared files
instead of transferring them to your machine, you'll want to look at network
file storage services instead. We'll discuss those in the upcoming module.