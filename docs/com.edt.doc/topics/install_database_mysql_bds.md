# Configuring a MySQL or MariaDB database for the HCL UrbanCode Deploy blueprint design server

To use a MySQL or MariaDB database with the blueprint design server, before you install the blueprint design server, install the database and provide the Java™ Database Connectivity \(JDBC\) JAR file for the blueprint design server installation process.MySQL and MariaDB are similar databases. Which one you use depends on your operating system and version.

Before you install the blueprint design server, install the database. If you are evaluating HCL® UrbanCode™ Deploy, you can install the database on the same system as the blueprint design server.

For example, the command to install MariaDB on a system that runs Red Hat Enterprise Linux™ version 7 resembles the following example:

```
yum install -y mariadb mariadb-server
```

To set the database to run automatically and start the MariaDB database on a Linux system that uses `systemctl`, run the following command:

```
systemctl enable mariadb; systemctl start mariadb
```

**Note:** The database must be encoded in UTF-8.

Follow these steps to set the database encoding:

1.  On the system that hosts the database, open MySQL or MariaDB configuration file. The location of the file depends on the operating system. On Linux, the file is named my.cnf, and many distributions put the file in the folder /etc or /etc/mysql. On Windows, the file is named my.ini.
2.  In the `[mysqld]` section of the configuration file, add the following lines:

    ```
    character-set-server=utf8
    character-set-filesystem=utf8
    ```

3.  Restart the database. For example, to restart MariaDB on Linux, use this command:

    ```
    systemctl restart mariadb
    ```


1.   Open a command-line window and log in to the database as a user with table-creation privileges. For example, run this command from the command line:

    ```
    mysql -u root
    ```

    The command line shows a prompt that looks like this example:

    ```
    MariaDB>
    ```

2.   Create a user for the blueprint design server to use and assign the user a password, as in the following example command. This example creates a user that is named `ibm_ucdp` with the password as a `ibm_ucdp`.

    ```
    CREATE USER 'ibm_ucdp'@'localhost' IDENTIFIED BY 'password';
    ```

    Remember this user name and password because you must have them when you install the blueprint design server.

3.   Create a database for the blueprint design server, as in the following example command: 

    ```
    CREATE DATABASE ibm_ucdp;
    ```

4.   Grant permissions for the user to work with the database: 

    ```
    GRANT ALL ON ibm_ucdp.* TO 'ibm_ucdp'@'%' IDENTIFIED BY 'password' WITH GRANT OPTION;
    ```

5.   Type `quit` to exit the database command line. 
6.   Obtain the MySQL or MariaDB JDBC driver. 
7.   Either note the location of the JDBC JAR file or place the file in the installation\_directory/ibm-ucd-patterns-install/web-install/media/server/opt/tomcat/lib folder. 
8.   Begin blueprint design server installation. See [Installing the blueprint design server](install_server_bds.md#). When you are prompted for the database type, enter mysql. 
9.   Provide the JDBC driver class that the blueprint design server uses to connect to the database. The default value is `com.mysql.jdbc.Driver`.
10.  Next, provide the JDBC connection string. Typically, it is similar to the following code:

    ```
    jdbc:mysql://DB\_URL:DB\_PORT/DB\_NAME
    ```

    For example, the connection string to database that is on the same computer as the blueprint design server and that uses the default port resembles the following code:

    ```
    jdbc:mysql://localhost:3306/ibm_ucdp
    ```

11.  Finish by entering the database user name and password. 

**Parent topic:** [Blueprint design server database configuration](../../com.edt.doc/topics/install_database_bds_ov.md)

