Gitweb and remote repositories
------------------------------

Let's suppose our remote repositories are in
*/home/git/repositories*. We're going to use *Apache* for serving our
files through *gitweb*. After installing *gitweb*, you'll need to
configure your */etc/httpd/conf.d/git.conf* file adding the following
lines:

    <Directory /var/www/git>
      Options +ExecCGI
      AddHandler cgi-script .cgi
      DirectoryIndex gitweb.cgi
    </Directory>

Set your *$projectroot* variable in your */etc/gitweb.conf* adding the following line:

    our $projectroot = "/home/git/repositories/";

Remeber that *git:git* are set for */home/git* and the *apache* user
is running our *Apache* server, then we need to give read permissions
to our repositories. Let's do that:

   1. `# chmod 2775 -R /home/git/`
   2. Add the following line to your *.gitolite.rc* file:
      `$REPO_UMASK = 0027;`

After doing the last change (2) all new created files will have the
group *git* as owner. Remeber that `chmod 2755` is setting the group
guid for the directory.