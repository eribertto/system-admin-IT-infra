So we've talked about how important backups are, and why you should be backing
up any important data. And some tools that can be used to help you back up data.
But how exactly do you decide when, and how to back up data? Well let's explore
those options. There's a couple of ways to perform regular backups on data
that's constantly changing. You can do a full backup on a regular basis, which
involves making a copy of the data to be fully backed up. The full unmodified
contents of all files to be backed up is included in this backup mechanism
whether the data was modified or not. In the case of data that doesn't change
very often, like operating system configuration files, this approach can be
inefficient. You're backing up multiple copies of data that isn't changing,
which waste space and uses bandwidth unnecessarily. That doesn't seem like the
best idea does it? A more efficient approach is to only backup files that are
changed, or been created since the last full backup, this is called a
differential backup. The advantage is that you aren't storing backups of
duplicated, unchanging data, only the files that changed are backed up. Saving
us some storage space and time to form the backup. But you wouldn't want to
completely stop taking full backups. Over time you wind up tracking and storing
lots of copies of files that change a lot, which will also take up more and more
disk space over time. To avoid this it's a good practice to perform infrequent
full backups, while also doing more frequent differential backups. How often you
perform a full backup will depend on how far back you want changes to be
tracked. Let's say we perform full backups once every week, and differential
backups daily. In the worst case scenario we'll lose close to 24 hours of data
changes, that's not bad. Another efficient way to backup changing data is to
perform regular incremental backups. While a differential backup backs files
that have been changed or created, and incremental backup is when only the data
that's changed in files is backed up. This is even more efficient in terms of
both disk space, and time required compared to differential backups. Again
you'll want to use frequent incremental backups along with less frequent full
backups. But because this approach only sorts differences in the files that have
changed since the last incremental backup, it's possible that all incremental
backups are needed to fully reconstruct the files. If one of these incremental
backups is missing or corrupt it might not be possible to recover data any more
recently than the last full back up. Another drawback is that recovery might be
more time consuming. This is because the most recent version of backed up data
has to be recreated by integrating the last full backup with each incremental
backup that follows. For super large files that are changing frequently this
could require a lot of time to process. One more thing backup systems can do to
help save space is bar compression. When creating a backup all the files and
folder structures will be copied and put into an archive. Archives are useful
for keeping files organized and preserving full structure. Besides archiving the
files, backups can also be compressed, this is a mechanism of storing the same
data while requiring less disk space by using complex algorithms. Those are way
to complicated to go into detail here, but it's important to call out that not
all data types lend themselves to being compressed. This means that space
savings from compression will depend on what you're backing up. Another thing
you should know about compressing backups is the expense of restoration. To
recover data from a backup it needs to be decompressed first. Depending on the
size of your backups this could take a lot of time, and disk space to expand. We
touched on backup storage location a bit in the last lesson, but let's dive into
a little more detail. Good news, there's a pretty cheap and easy to maintain
option out there for storing backup data on site. You can use a commercial NAS
device, or configure a filer server with a large amount of disk space. Wherever
you chose to store your backup data you'll need a lot of space. You could go out
and buy a giant 10 terabyte hard disk, which could work for a little while. But
what do you do once your back up data grows to fill that one disk? Are they even
making disks larger than 10 terabytes yet? Another thing to worry about is what
do you do if that one disk holding all your backed up data fails. Yikes, that
wouldn't be good. These are issues a RAID array can address. RAID stands for
Redundant Array of Independent Disks, it's a method of taking multiple physical
disks and combining them into one large virtual disk. There are lots of types of
RAID configuration called levels. Depending on the characteristics desired from
the RAID, various RAID levels prioritize features like performance, capacity, or
reliability. RAID arrays are a great, inexpensive way of creating a lot of data
capacity, while minimizing risk of data loss in the event of disk failure. They
can even be flexible enough to allow future growth in disk capacity. We won't go
into the nitty gritty details of the different RAID levels available, but if you
want to learn more check out the supplemental readings at the end of this
lesson. I want to stress the fact that RAID isn't a back up solution, it's a
data storage solution that has some hardware failure redundancy available in
some of the RAID levels. But storing data on a RAID array doesn't protect
against accidentally deleting files, or malware corrupting your data. This is so
important that I'm going to say it one more time. RAID is not a replacement for
backups.