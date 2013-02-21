Exporting a repo from Mercurial to Git
--------------------------------------

1. Install *fast-export* tool:

          $ git clone git://repo.or.cz/fast-export.git

2. Install *pygments* Python's library:

          $ sudo pip-python install pygments

3. Creates a new empty *git* repo:
       
         $ mkdir git-repo
         $ cd git-repo
         $ git init

3. Export your *hg* repo:

         $ ./fast-export/hg-fast-export.sh -r ~/pathto/hg_repo --force

4. Change to your working branch
        
         $ git checkout branch_name