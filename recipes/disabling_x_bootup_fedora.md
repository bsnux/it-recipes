Disabling X at bootup in Fedora
-------------------------------

Open your */etc/inittab* and replace this line:

    id:5:initdefault:

For this other new line:

    id:3:initdefault: