Adding syntax hightlight to gitweb
----------------------------------

We use Fedora as operating system so you'll need to execute the
following command:

    $ sudo yum install highlight
    
After executing the last command you can configure *gitweb* adding the
following line to your *gitweb.conf* file:

    $feature{'highlight'}{'default'} = [1]

Remember that version **1.7.4** for *gitweb* is required at least.