Git: How-to undo a merge action
================================

If you use *pull* action using parameters such as *origin* and branch name, for
sure you sometimes make a non-desire action like the following one:

    (master) $ git pull origin another-branch

Well, no problem. You can undo last one action execting the next command:

    (master) $ git reset --merge ORIG_HEAD

