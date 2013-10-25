screen Quickstart
==================

When you need to run a command or program even if you terminal is close, you can use *screen*. Also,
*screen* allows you to start a command or program from command-line session on a computer and then go to other
computer and resume that session.

## Simple flow

* Lauching *screen*: **$ screen**
* Deattaching a session: **C-a d**
* Connecting to dettached session: **$ screen -x**
* Creating a new session: **screen -S staging**
* Reattaching to existing session: **screen -r staging**
* Creating a new window: **C-a c**
* Go to window 3: **C-a 3**
* Kill current window: **C-a k**
* Create a running log history: **C-a h**
* Rename current window: **C-a A**
* Listing all attached sessions: **$ screen -ls**
* Split screen: **C-a S**
* Move to next window in split screen: **C-a TAB**
* Come back to normal view: **C-a Q**

## Basic .screenrc file

	bind c screen 1
	bind ^c screen 1
	bind 0 select 10
	screen 1

	vbell off
	autodetach on
	startup_message off

	hardstatus alwayslastline
	hardstatus string '%{= kG}[ %{G}%H %{g}][%= %{= kw}%?%-Lw%?%{r}(%{W}%n*%f%t%?(%u)%?%{r})%{w}%?%+Lw%?%?%= %{g}][%{B} %m-%d %{W} %c %{g}]'
