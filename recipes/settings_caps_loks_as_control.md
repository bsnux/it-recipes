Setting Caps Lock key as Control
--------------------------------

Usually *Emacs* users want to change the default behaviour for the
*Caps Lock* key and using it as an additional *Control* key. We can
change it using *Xmodmap*:

1. Edit your `/etc/X11/Xmodmap` adding the following lines:
    
    `clear lock`
    
    `add control = Caps_Lock`

2. Execute the `Xmodmap` command:

    `$ xmodmap /etc/X11/Xmodmap`