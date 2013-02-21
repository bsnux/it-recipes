How to display all queries in MySQL log
----------------------------------------

1. Open and edit your *my.cnf* file. Fedora users: */etc/my.cnf*

2. Add the following entry inside the *[mysqld]* section:

	`log=/tmp/mysql.log`

3. Restart you *mysql* server. Fedora users:

	`$ sudo service mysqld restart`