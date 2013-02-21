GDM and Enlightenment for Fedora
--------------------------------

If you want to use double layout for your keyboard on Fedora with
*GDM* and *Enlightenment* be careful because *GDM* is overwriting your
default *X* configuration. For avoiding this situation you can do the
following:

1. Create a new *xorg.conf* file. Remember that Fedora don't use a
*xorg.conf* file by default. Instead of it, Fedora create a new one on
boot time.

    `$ sudo  Xorg -configure :1`

2. Copy your new file to */etc/* directory:

    `$ sudo cp xorg.conf.new /etc/X11/xorg.conf`

3. Add the following lines to your config file:

    `Section "InputClass"`
    
          Identifier       "Generic Keyboard"
          MatchIsKeyboard  "on"
          Option           "XkbModel"    "pc105+inet"
          Option           "XkbLayout"   "us,es"
          Option           "XkbOptions"  "ctrl:nocaps,grp:ctrl_shift_toggle"
    `EndSection`
    
4. Disable *GDM*:

    `$ sudo initctl stop prefdm`

5. Launch *startx* from command line:

    `$ startx`

As you guess, we need to disable *GDM* for using *Enlightenment* with
*GDM*.

Disabling X at bootup in Fedora
-------------------------------

Open your */etc/inittab* and replace this line:

    id:5:initdefault:

For this other new line:

    id:3:initdefault: