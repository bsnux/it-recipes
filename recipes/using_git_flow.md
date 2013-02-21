Using git-flow
--------------

You can use *git-flow* for a new one repository or for an existing
one.

Commands for working with *git-flow*:

   * Starting: `$ git-flow init`
   
   * Creating a new *feature* branch: `$ git-flow feature start <name>`
   * Finishing your *feature* branch (ready for merging): `$ git-flowfeature finish <name>`
     
     * It will merge *feature/<name>* into *develop* deleting the *feature* branch
       
   * Start a *release* branch: `$ git-flow release start <version_name>`
   * Finishing a *release* branch `$ git-flow release finish <version_name>`
     
     * It will merge your changes to *master* and back to *develop*