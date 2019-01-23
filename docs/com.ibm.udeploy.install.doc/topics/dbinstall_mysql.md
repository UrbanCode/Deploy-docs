# Configuring a MySQL or MariaDB database for the HCL UrbanCode Deploy server

To use a MySQL or MariaDB database with the server, before you install the server, install the database, and provide the JDBC JAR file for the server installation process.MySQL and MariaDB are similar databases. Which one you use depends on your operating system and version.

Before you install the HCL® UrbanCode™ Deploy server, install MySQL or MariaDB, depending on your operating system and version. If you are evaluating HCL UrbanCode Deploy, you can install the database on the same system as the HCL UrbanCode Deploy server.

For example, the command to install MariaDB on a system that runs Red Hat Enterprise Linux™ version 7 resembles the following example:

```
yum install -y mariadb mariadb-server
```

To set the database to run automatically and start the MariaDB database on a Linux system that uses `systemctl`, run the following command:

```
systemctl enable mariadb; systemctl start mariadb
```

When you install HCL UrbanCode Deploy, you need the database connection information, and a user account with table-creation privileges.

**Note:** It is recommended that the database be encoded in UTF-8. Changing the database to a case-sensitive collation is also recommended.

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


1.   Open a command-line window and log in to the database. The command might look like the following example:

    ```
    mysql -u username -ppassword
    ```

    For `username`, specify the user name for the database. The default user name is `root`. For `password`, specify the password for that user name. The default account has no password; in this case, omit the `-p` flag and the password.

    **Note:** Do not insert a space between the `-p` flag and the password.

2.   Create a database. Specify case-sensitive collation. The following commands are an example of how you might create this database:

    ```
    CREATE USER 'ibm_ucd'@'localhost' IDENTIFIED BY 'password';
    ```

    ```
    CREATE DATABASE ibm_ucd character set utf8 collate utf8_bin;
    ```

    ```
    GRANT ALL ON ibm_ucd.* TO 'ibm_ucd'@'%' IDENTIFIED BY 'password' WITH GRANT OPTION;
    ```

3.   Log out of the database command line. 
4.   Obtain the database JDBC driver. The JDBC JAR file is included among the database installation files. The driver is unique to the database edition you are using.

    When multiple drivers are available, you might need to consult with the database provider to determine which driver to use. The JDBC driver version that you must use might depend on the version of the database and the version of Java™ used by the HCL UrbanCode Deploy server.

5.  Copy the JDBC JAR file to installer\_directory\\lib\\ext. 
6.   Begin server installation. See [Installing the server](serverInstall.md). When you are prompted for the database type, enter mysql. 
7.   Provide the JDBC driver class HCL UrbanCode Deploy uses to connect to the database. The default value is `com.mysql.jdbc.Driver`.
8.  Next, provide the JDBC connection string.Typically, it is similar to the following code:

    ```
    jdbc:mysql://DB\_URL:DB\_PORT/DB\_NAME
    ```

    For example, the connection string to database that is on the same computer as the HCL UrbanCode Deploy server and that uses the default port resembles the following code:

    ```
    jdbc:mysql://localhost:3306/ibm_ucd
    ```

9.  Finish by entering the database user name and password. 

**Parent topic:** [Installing the server database](../../com.ibm.udeploy.install.doc/topics/DBinstall.md)

