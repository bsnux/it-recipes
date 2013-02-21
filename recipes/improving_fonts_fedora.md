Improving fonts in Fedora
-------------------------

It's easy to improve our fonts in Fedora:

    $ sudo yum update
    $ sudo ln -s /etc/fonts/conf.avail/10-autohint.conf /etc/fonts/conf.d/
    $ sudo ln -s /etc/fonts/conf.avail/10-sub-pixel-rgb.conf /etc/fonts/conf.d/
    
Before continouing, reboot your machine. After taken this action,
install this additional package:

    $ sudo yum install freetype-freeworld"

Right now, you can reboot again or just execute the following command:

    $ sudo fc-cache
    
For more information related to improving fonts, please read this [page](http://fedoraunity.org/Members/khaytsus/improve-fonts)