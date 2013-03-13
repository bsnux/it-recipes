Configuring a graphic tool for git
==================================

If you need to use a graphic tool with *git* for displaying differences between
files and/or revisions, you can configure it. One of the most popular of this
kind of graphic tools is [Meld](http://meldmerge.org/).

First step will be to install *Meld* in your machine. If you are using *Ubuntu*
or similar Linux *distro*, you only need to execute the following command:

	$ sudo apt-get install meld

Then you need to configure you *git* so you should launch the next commmand:

	$ git config --global diff.tool meld

Now your tools are configured and you can use them directly to display differences
between files and/or revisions:

	$ git difftool master..mybranch

If you take a look at your *~/.gitconfig* file, you can display a new section that
has been created:

	[diff]
	    tool = meld

Also, you can use *Meld* as graphic tools for working with merging operations.