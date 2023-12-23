# Can I run Lute on a private web server?

Lute can be run anywhere that has the necessary requirements (Python, etc).  For a server installation, Docker would probably be the easiest.

It's outside of the scope of this manual to show how to set up your server in AWS, Digital Ocean, or wherever, but it's totally possible.

The biggest thing you probably have to worry about is your backup and disaster recovery plan.  Lute writes disk for the database and images, so make sure you're backing up and exporting to some secure, reliable location.