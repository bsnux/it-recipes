Git: Tracking branches for pulling/pushing
===========================================

If you use *git* daily, for sure you found this message after executing **git pull**:

	You asked me to pull without telling me which branch you
	want to merge with, and 'branch.mybranch.merge' in
	your configuration file does not tell me, either. Please
	specify which branch you want to use on the command line and
	try again (e.g. 'git pull <repository> <refspec>').
	See git-pull(1) for details.

	If you often merge with the same branch, you may want to
	use something like the following in your configuration file:
	    [branch "mybranch"]
	    remote = <nickname>
	    merge = <remote-ref>

	    [remote "<nickname>"]
	    url = <url>
	    fetch = <refspec>

	[branch "mybranch"]
		remote = origin
		merge = refs/heads/mybranch


What happened? Basically, previous message inform you about some local branches
are not tracked from your *origin*. You can fix this quickly, executing following command:

	git branch --set-upstream <branch_name> origin/<branch_name>

Keep in mind that **<branch_name>** is the name of the branch you want to track. You should
repeat that command for tracking each branch. Alternatively, you can change your **.git/config** file
directly:

	[branch "mybranch"]
	remote = origin
	merge = refs/heads/mybranch

