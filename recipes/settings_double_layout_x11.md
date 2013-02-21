Setting double layout for X11
-----------------------------

Edit your *xorg.conf* file and add the following lines:

     Section "InputClass"
	     Identifier	        "Generic Keyboard"
	     MatchIsKeyboard	"on"
	     Option		        "XkbModel"	"pc105+inet"
	     Option		        "XkbLayout"	"us,es"
         Option             "XkbOptions"    "ctrl:nocaps,grp:ctrl_shift_toggle" 
     EndSection

We set two different layout for our keyboard (USA and Spain) and we
can change among them using *Ctrl+Shift*. In addition to this
configuration, we remmaped *Caps Lock* as an additional *Ctrl* (very
useful for *Emacs*). If you need more information
about available shortcuts take a look at
*/usr/share/X11/xkb/rules/base.lst* file.