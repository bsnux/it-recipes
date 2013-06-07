How to display differences for a file in different revisions
============================================================

If you need to display what changes between revisions in a specific file, you can
execute the following command:

    $ git diff <rev>:<filepath> <rev>:<filepath>

For example:

    $ git diff 195ca48:templates/home.html   8a08aa0:templates/home.html

