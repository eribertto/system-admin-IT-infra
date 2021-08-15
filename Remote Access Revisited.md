Another important part of physical infrastructure services is the ability to
connect to your infrastructure from anywhere in the world. We talked about
remote access in an earlier course, and we've been using it all throughout this
program to connect to our lab machines. In this lesson, we're going to discuss
what's needed to set up for remote access for a small organization. As a systems
administrator, or as anyone in IT support, you'll want to be able to remotely
access another server or user's machine so that you can troubleshoot an issue.
Or do maintenance from wherever you may be. In Linux, the most popular remote
access tool is OpenSSH. We've already learned how to SSH into a remote computer
in the last course, and we talked a bit about what's needed to set up SSH. But
we'll quickly show you how to do this. To SSH into another machine, you need to
install an SSH client on the machine you're connecting from. Then install an SSH
server on the machine you're connecting to. To learn more about open SSH, you
can check out the next supplementary reading. But let's keep rocking and rolling
with how to install the open SSH client on a machine. It's super easy. What
you're going to do is always, go to my client machine, and simply run this
command, sudo apt-get install openssh-client. And going, downloading package,
perfect. So, it looks like my client has been installed. Next, you need to
install the open SSH server on the machine you want to access. Remember, the SSH
server is just a process that listens for incoming SSH connections. So, let's go
to the server and install the open SSH server. So I'm going to do sudo apt=get
install openssh-server. Perfect, so it looks like my server's up and running. So
let's go back to the client and do a test. I do ssh, and to my server IP address
with my username. It asks for my password which is a good thing. Perfect, so as
you can see, I'm connected to my server. And one true way to test this if I go
into my desktop of my server, and let me create a folder. Now if I go back to my
server, which is on this window, and I list the files, you can see the folder
test, and that's it. Now you're able to SSH into a machine from another machine.
Not too complicated, right? Windows has similar tools that you can use. A
popular tool to access the CLI remotely is WinRM or Putty. RDP is also popular
if you want to access the GUI remotely. We've already discussed how to connect
to a machine using Putty in the last course. Just remember to install an SSH
server on the machine you want to connect to. We also already discussed how to
set up RDP in the last course. Feel free to read those lessons as a refresher.
You can read more about the Windows Remote Access tools in the next reading. The
takeaway here is that when you manage IT infrastructure, you can utilize tools
like Remote Access to work on your physical infrastructure. You'll need to do a
little bit of setup beforehand, like installing a SSH client, SSH servers, and
allowing remote desktop connections, etc. But it will be worth it in the long
run. Next up, we'll tackle network service. See you there.