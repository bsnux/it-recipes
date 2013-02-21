Exporting/Importing a private GPG key
-------------------------------------

For exporting:

    $ gpg --export-secret-key -a > /tmp/secret.key
    
For importing

    gpg --import /tmp/secret.key