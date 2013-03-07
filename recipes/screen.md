screen Quickstart
==================

When you need to run a command or program even if you terminal is close, you can use *screen*. Also,
*screen* allows you to start a command or program from command-line session on a computer and then go to other
computer and resume that session.

## Simple flow

* Creating a new session: **screen -S staging**

* Deattaching a session: **C-a d**

* Reattaching to existing session: **screen -r staging**

* Creating a new window: **C-a c**

* Go to window 3: **C-a 3**

* Listing all attached sessions: **screen -ls**

## Basic .screenrc file

	bind c screen 1
	bind ^c screen 1
	bind 0 select 10
	screen 1

	vbell off
	autodetach on

	hardstatus alwayslastline
	hardstatus string '%{= kG}[ %{G}%H %{g}][%= %{= kw}%?%-Lw%?%{r}(%{W}%n*%f%t%?(%u)%?%{r})%{w}%?%+Lw%?%?%= %{g}][%{B} %m-%d %{W} %c %{g}]'