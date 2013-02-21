Creating one MySQL database with one user
-----------------------------------------

    CREATE DATABASE mydb DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
    GRANT ALL PRIVILEGES ON mydb.* TO 'mydb'@'localhost' IDENTIFIED BY 'mydb';
    FLUSH PRIVILEGES;
    exit;