Creating a new git repository using gitolite
--------------------------------------------

When *gitolite* is configured for controlling the access to our *git*
repositories we can create a new one repository using the following
steps:

* Clone the *gitolite-admin* repository
* Modify the *conf/gitolite.conf* adding a few lines for the new
  repository:
  
         repo     new repo
                RW+    =    user1
                Rw+    =    user2