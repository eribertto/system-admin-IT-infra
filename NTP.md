One of the oldest Internet protocols in use today is the network time protocol
or NTP. It's used to keep the clock synchronized on machines connected to a
network. You've probably seen NTP implemented in your personal life if you've
ever been in an airport. Airports utilize synchronized clocks systems, and many
of their systems use NTP. This is because the information that you see on your
departure and arrival screen has to match the time that the air traffic control
team sees for their airplanes. If only NTP could solve for airport delays.
Anyway, in the IT world, machines need to have accurate time across a network
for a lot of reasons. There are some security services like Kerberos and network
authentication protocol that depend on the time being consistent across the
network to work. You'll learn more about that in the IT security course coming
up. It is important to keep the time consistent and accurate across your
company's fleet. You can't depend on the hardware itself to keep consistent
time, so you might want to set up an NTP server. There are different ways that
an IT support specialist or sysadmin can do this for an organization. You can
use a local NTP server or a public NTP server. To set up a local NTP server, you
can install NTP server software on your management server. Then, you install NTP
clients on your machines and tell those computers which NTP service to sync
their time to. This is a great option because you can then manage the entire
process from end to end. The other way to set up NTP is to use a public NTP
server. Public NTP servers are managed by other organizations that your client
machines connect to in order to get synchronized time. This is an awesome way to
utilize NTP without having to run a dedicated NTP server. But if you have a
large fleet of thousands of machines, it's better etiquette to be running your
own NTP servers. Another good practice is to run your own NTP server. Then, have
that point to a public NTP server. This makes it so that you don't connect all
your clients to a public NTP server, and you don't have to measure time
synchronization. Whether you run your own NTP server, or you use a public one,
NTP is an important network service that you should definitely integrate into
your own fleet.