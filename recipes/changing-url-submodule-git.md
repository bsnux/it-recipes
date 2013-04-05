How to apply changes when your git submodules URLs has been updated
===================================================================

If your *git* project is using one or more submodules and one of these changed its URLs, you'll need
to update your local copy executing the following commands:

    $ git submodule sync
    $ git submodule update
