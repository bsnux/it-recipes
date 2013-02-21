Installing MS TrueType fonts in Fedora
--------------------------------------

It's convenient to activate the *RPMFusion* repositories using the
instructions in [this web site](http://rpmfusion.org/Configuration/),
then you can execute the following commands:

    $ cd /tmp/
    $ wget http://corefonts.sourceforge.net/msttcorefonts-2.0-1.spec
    $ yum install rpm-build cabextract ttmkfdir
    $ rpmbuild -ba msttcorefonts-2.0-1.spec
    $ cp ~/rpmbuild/BUILD/msttcorefonts/fonts/* ~/.fonts/
    $ sudo fc-cache -fv