Fixing problem with *git pull*
-----------------------------

You can use *git pull* which by default will execute *git pull origin
master*. But sometimes, after using *git fetch* the *git pull* command
doesn't work in the same way. If you execute *git pull* you can find
this message:

    You asked me to pull without telling me which branch you
    want to merge with, and 'branch.master.merge' in
    your configuration file does not tell me, either. Please
    specify which branch you want to use on the command line and
    try again (e.g. 'git pull <repository> <refspec>').
    See git-pull(1) for details.

    If you often merge with the same branch, you may want to
    use something like the following in your configuration file:

    [branch "master"]
    remote = <nickname>
    merge = <remote-ref>

    [remote "<nickname>"]
    url = <url>
    fetch = <refspec>

For avoiding this message just execute the next command:

    $ git pull origin master
    
If you want to continue using *git pull*, you can execute this
command:

    $ git config branch.master.remote origin && git config branch.master.merge refs/heads/master
    
After executing this operation, you can use `git pull` without any problems.