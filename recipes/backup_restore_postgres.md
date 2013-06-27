Backup and restore a PostgreSQL database
=========================================

*pg_dump* and *pg_restore* are commands for creating and restoring backups of *PostgreSQL* databases.

The following command creates a simple *SQL* file with all data and tables of your DB:

    $ pg_dump <db> -U <user> > /tmp/db_backup.sql

Don't forget to replace **<db>** for your database name and **<user>** for username with privileges to connect to database.

Before restoring yor backup, you'll need to drop your database and create a new one, then you can execute the following command:

    $ pgsql <db> -U <user> < /tmp/db_backup.sql

However, sometimes it's more convenient to use *pg_restore* tool instead of *pgsql* for restoring your backup. In that
case, you'll need to create your backup usinga different format instead of plain SQL file. The following command will
create a backup using a appropiate format:

    $ pg_dump <db> -U <user> -F c > /tmp/db_backup.data 

Then you can restore your backup executing the next command:

    $ pg_restore <db> -U <user> -c /tmp/db_backup.data

The **-c** option tell to *pg_restore* that database objects will be dropped before recreating them.
