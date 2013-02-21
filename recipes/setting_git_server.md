Setting up a git server
-----------------------

[Gitolite](https://github.com/sitaramc/gitolite) is a great tool for handling permissions for multiple
users and repositories on a *git* server. One of its best features is
to use only one system users for handling the access to multiple git's users.

Our goal is to get working a *git* server which allows us to work with
multiple users and repositories with different permissions. But we
only want to use **one** system user.

These are the steps to set up a *git* server:

1. Choose a machine for your *git* server.

2. Install *Gitolite*:
    * Option 1: Using the binary package for your distro. For example, Fedora users can execute:
     
           * $ sudo yum install gitolite
       
    * Option 2: Downloading the code from *github*:
   
           * `$ git clone git://github.com/sitaramc/gitolite gitolite`
           * `$ cd gitolite`
           * `$ sudo mkdir -p /usr/local/share/gitolite/conf /usr/local/share/gitolite/hooks`
           * `$ sudo src/gl-system-install /usr/local/bin /usr/local/share/gitolite/conf /usr/local/share/gitolite/hooks`
       
           You're ready for executing binary files included in
           *Gitolite* as *gl-setup*

3. Create a system user called *git* or whatever on your *git* server
machine and login on the system:

     * `$ su - git`

4. Each new *git* user should send to you (the *admin*) a *SSH
key*. For example: A user called *lucas* generated a public key and
send to you a file called *lucas.pub*. 

5. At this point we need to add an *admin* user. Of course, we need
his/her *SSH public key* as we explained in the previous step. We'll
add this key using the following command:

    * `$ gl-setup /tmp/admin.pub`
    
6. After executing the command in the previous step we have a new
*git* repository called **gitolite-admin**. This repository will be
cloned for change all things related to *admin* issues. Don't forget
that *Gitolite* requires that every change must do locally, never on
the server. After each local change we need to execute *pull** for
updating our **gitolite-admin** repository. Also, a new repository
called **testing** is created by default.

7. We're going to clone our new **gitolite-admin** repository:

    * `$ git clone ssh://git@myrepo-server/gitolite-admin`

8. The **gitolite-admin** repo. have 2 specific directories:

    1. **conf** where the main **gitolite.conf** file is stored.
    2. **keydir** where *SSH public keys** for users are stored.
    
9. Adding repos. and users. For example, let's add one new
repo. called **myrepo** with *read/write* permissions for the
*grijander* user.

    * Edit your *conf/gitolite.conf* and add the following lines:
        
        * `repo myrepo`
               `RW+ grijander`
    
    * Copy the *SSH public key* for the user *grijander* to the
      **keydir** directory:
      
        * `$ cp /tmp/grijander.pub keydir/`

10. We're ready to *push* our changes to the server:

    * `$ cd gitolite-admin`
    * `$ git add .`
    * `$ git commit -a -m "Creating a new repo. with RW to the
      grijander user"`
    * `$ git push origin master`
    
11. Done!!

Right now **grijander** can clone the new **myrepo** repository on
his/her machine:

    $ git clone ssh://git@myrepo-server/myrepo

If we have an existing repository, we need to export it to our *git*
server. For example, if the user *grijander* has an existing
repo. called **myrepo** (already was created through *Gitolite*), he
can export it executing the following commands:

    $ git remote add origin ssh://git@myrepo-server/myrepo
    $ git push origin master

The documentation for *Gitolite* can be found
[here](http://sitaramc.github.com/gitolite/doc/).