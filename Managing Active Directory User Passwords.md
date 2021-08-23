One of the key advantages of central authentication is that it simplifies the
management of passwords. Did you know that up to 25 percent of people forget
their password at least once a day? Helping users with password issues is a
common task for an I.T support specialist. Once a user changes their password in
active directory, that change is effective on every machine that they're
permitted to log onto. With certain exceptions, AD doesn't store the user's
password. Instead, it stores a one-way cryptographic hash of the password.
You'll learn more about hashing in the I.T security course. In the meantime, the
basic idea is that passwords can be easily turned into a hash, but hashes can't
be easily turned back into passwords. You can't look up a user's password even
if you wanted to. That's actually a really good thing. As a general rule, you
should avoid ever knowing the password of another person's account. If there's
more than one person who can authenticate using the same user name and password,
then auditing becomes difficult or even impossible. To audit your infrastructure
in this sense means to analyze who perform specific actions in your I.T
infrastructure. In a security audit or troubleshooting scenario, it's important
that only one person can authenticate with their account. So, keeping that in
mind, how can you assist with the account passwords? The most common issue is
that a person forgets the password. When this happens, if you have SysAdmin
responsibilities, you may be authorized to reset their password for them. This
should only be done when you're absolutely sure that the person requesting the
password reset is allowed to do so. Many organizations will have policies and
procedures that require the request to be made in person, or that the person
otherwise prove that they are who they say they are. Once you know that the
password reset is authorized, you've done the hard part. The rest is simple. So,
let's imagine that Mateo reports that he can't sign into his account because he
forgot his password. In the Active Directory administration center which I'll
show you right here, we're going to right click on his user account. Lets find
his user account first. And then right-click his account, and click reset
password. The password that we enter here will be temporary because we we're
going to make sure that user must change password at next log in is checked. So
I'm going to go ahead and create a temporary password. And I want to make sure
that the user must change the password at next log on option is checked, and
then hit okay. Again, we don't want to know the user's password. So, I'm not
going to ask Mateo for a temporary password. He might just tell me a variation
of his usual password, and I don't want that. Some orgs will have policies about
how to generate and distribute temporary passwords. You want to make sure you
know if those exist. We'll go over the details of strong passwords and having
policies to enforce them in the upcoming I.T security course. In this example,
I'm just going to generate a random password and enter it here. Oh, what's this?
User accounts can be locked by active directory if someone enters a wrong
password for that account too many times. It seems that this is what's happened
to Mateo. Once an account is locked, nobody can authenticate with the account
until the account is unlocked by an administrator. Active directory password
policies control how many attempts are allowed before an account is locked out.
We'll take a look at password policies here in a bit when we go over group
policy objects or GPOs. Back to the problem at hand. I want Mateo to be able to
log in and change his password. So I'll make sure the option, unlock account is
checked, and click okay. If you look at what is happening in PowerShell, you'll
see some familiar commands along with a new one for unlocking Mateo's account.
When you change your password, you have to provide the current password as well
as the new one. This is the sort of thing that happens when a user changes their
own password. When you reset a password as an administrator, you only provide
the new password and your administrative authorization overrides the existing
password. If this person has used the NTFS encrypting file system or EFS feature
to encrypt files, they can lose access to those files if their password is
reset. To learn more about this and how to prevent data loss, check out the next
supplemental reading.