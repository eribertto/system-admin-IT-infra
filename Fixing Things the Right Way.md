As an IT support specialist, you will
often be in charge of fixing problems. The problem could be in a user's computer,
a server in your own infrastructure, a piece of code running in the cloud or
somewhere in between. So how do you go about fixing it? Let's say you're dealing with a problem,
either because you found it or someone reported it to you. Before you start fixing it, make sure you
can recreate the error as you'll want to test your solution to make sure the
problem is gone after you apply the fix. This is called a Reproduction case. And means you're creating a roadmap to
retrace the steps that led the user to an unexpected outcome. Like reaching an error page. When looking for a reproduction case, there are three questions
you'll need to answer. What steps did you take
to get to this point? What's the unexpected or bad result? And what's the expected result? Let's say that you're trying to fix
a problem where a user can't access a website page. Their reproduction case would be
navigating to the failing site with a web browser. The bad result is an error page, where
the expected result is a visible website. Once you have the steps you need to
recreate the unexpected result, and you know what the right result should be,
you can try to fix the underlying issue. Remember, always do this in your
test instance, never in production. Make sure you document all your steps and
any findings. Having this documentation may prove
invaluable if you ever have to deal with similar issues again. Your future self will thank you. After applying your fix, retrace the same
steps that took you to the bad experience. If your fix worked, the expected
experience should now take place. For our page example, you can verify
your solution by visiting the site. Once you've applied the necessary fix,
you should see the website content, instead of the error page. Wow, we've come a long way and covered lots of different aspects of
the responsibilities of a sysadmin, including how to apply changes safely
with the right amount of effort. Next, you will practice these
concepts using Qwiklabs. Then in the next module, we'll talk about the technical details of
the infrastructure services used in IT. See you there.