So you're looking to bring a backup solution into your organization. But how do
you chose between a DIY backup system or one of the many cloud providers? Well
let's start by looking at the tradeoffs between the two. On site, or self
managed backups, could be as simple as buying a commercial NAS device, loading
it with a bunch of hard drives, and sending data to it over the network. This
would definitely work, but it might not be the best long term solution. How do
you grow the disk capacity when you need more storage space? How do you handle
the failed hard disk? Because hard disks will fail eventually, by the way, it's
important to call out these options aren't mutually exclusive. There's nothing
stopping you from implementing both on site and offsite backups. Actually, it's
often recommended to have both if it's within your organization's budget. One
thing that you should consider when evaluating the backup strategy for an
organization is, backup time period. How long do you need to hang on to backups
for? This answer will impact your long term storage needs and overall costs to
maintain a backup system. One approach, which balances cost with convenience, is
to archive older data using a slower but cheaper storage mechanism. The standard
medium for archival backup data storage is data tapes. These are a lot like
audio cassette tapes since they use spools of magnetic tape run through machines
that allow data to be written to and read back from the tape. Tape storage is
pretty cheap, but isn't as easy or quick to access as data stored on hard drives
or solid state drives. This storage system is usually used for long term
archival purposes, where data isn't likely to be needed. If it is needed some
delay in getting the data isn't a concern. There are dozens and dozens of backup
solutions available, we won't cover specific ones since there are way to many.
But we'll cover some common tools and give you some examples of backup solutions
available. One is the command line utility rsync. Rsync isn't explicitly a
backup tool, but it's very commonly used as one. It's a file transfer utility
that's designed to efficiently transfer and synchronize files between locations
or computers. Rsync supports compression and you can use SSH to securely
transfer data over a network. Using SSH, it can also synchronize files between
remote machines making it super useful for simple automated backups. Apple has a
first party backup solution available for their, Mac operating systems called it
Time Machine. It operates the using an incremental backup model. Time Machine
supports restoring an entire system from backup or individual files. It even
allows restoring older versions of backup files. Microsoft also offers and first
party solution called Backup and Restore. This has two modes of operation, as a
file based version where files are backed up to a zip archive. Or there's the
system image where the entire disk saved block by block to a file. File based
backup support, either complete backups or incremental ones. System image
backups support differential mode, only backing up blocks on the disk that have
changed since the last backup. If you want to learn more about these tools,
follow the links and supplemental readings after this lesson.