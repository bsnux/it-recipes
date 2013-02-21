Installing gitweb in Fedora
---------------------------

Just execute the followig command:

    $ sudo yum install gitweb

The binary package will create two different configuration files:

   1. */etc/gitweb.conf*: Configuration file for *gitweb*
   2. */etc/httpd/conf.d/git.conf*: Configuration file for *Apache*.

Keep in mind that the *gitweb* binary package will need *Apache* for
running.

Don't forget to set the variable for your root git repositories, for
example edit your */etc/gitweb.conf* and add the following line:

    our $projectroot = "/home/arturo/Documents/dev/";