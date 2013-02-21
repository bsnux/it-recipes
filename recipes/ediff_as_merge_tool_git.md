Using *ediff* (emacs) as merging tool for *git*
-----------------------------------------------

Edit your *.gitconfig* file and add the following lines:

    [mergetool "ediff"]
    cmd = xemacs -eval \"(ediff-merge-files-with-ancestor \\\"$PWD/$LOCAL\\\" \\\"$PWD/$REMOTE\\\" \\\"$PWD/$BASE\\\" nil \\\"$PWD/$MERGED\\\")\"
    [merge]
    tool = ediff