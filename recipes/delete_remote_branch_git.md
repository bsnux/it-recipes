Deleting a remote branch in git
===============================

You only need to execute the following command:

	$ git push origin :<remote_branch_name>

If our remote branch is called *feature-25*, we'll execute next command:

	$ git push origin :feature-25

Also, you should delete your local branch using the following command:

	$ git branch -d feature-25