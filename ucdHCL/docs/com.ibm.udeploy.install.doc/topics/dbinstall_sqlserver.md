# Configuring a Microsoft SQL Server database for the HCL UrbanCode Deploy server

To use an SQL Server database with the server, before you install the server, install the SQL Server database and provide the driver file for the server installation process.

Before you install the HCL® UrbanCode™ Deploy server, install an SQL Server database. Specify case-sensitive collation for the database. If you are evaluating HCL UrbanCode Deploy, you can install the database on the same system as the HCL UrbanCode Deploy server.

When you install HCL UrbanCode Deploy, you need the SQL Server connection information, and a user account with table-creation privileges.

**Note:** The user account cannot have the sysadmin role.

For example, the commands to create a database, create an SQL server user, and configure the database, might look like the following example:

```
CREATE DATABASE ibm_ucd;

USE ibm_ucd;

CREATE LOGIN ibm_ucd WITH PASSWORD = 'password';

CREATE USER ibm_ucd FOR LOGIN ibm_ucd WITH DEFAULT_SCHEMA = ibm_ucd;

CREATE SCHEMA ibm_ucd AUTHORIZATION ibm_ucd;

GRANT ALL TO ibm_ucd;
```

**Note:** It is recommended that the database be encoded in UTF-8. Changing the database to a case-sensitive collation is also recommended.

1.   Obtain the SQL Server JDBC driver files from the Microsoft™ site. 

    When multiple drivers are available, you might need to consult with the database provider to determine which driver to use. The JDBC driver version that you must use might depend on the version of the database and the version of Java™ used by the HCL UrbanCode Deploy server.

2.   Put the JDBC JAR file to installer\_directory\\lib\\ext. 
3.   Begin server installation. See [Installing the server](serverInstall.md). When you are prompted for the database type, enter sqlserver. 
4.  Provide the JDBC driver class HCL UrbanCode Deploy uses to connect to the database.The default value is `com.microsoft.sqlserver.jdbc.SQLServerDriver`.
5.  Next, provide the JDBC connection string.The format depends on the JDBC driver. Typically, it is similar to the following code:

    ```
    jdbc:sqlserver://DB\_URL:DB\_PORT;databaseName=DB\_NAME
    ```

     For example, the connection string to database that is on the same computer as the HCL UrbanCode Deploy server and that uses the default port resembles the following code:

    ```
    jdbc:sqlserver://localhost:1433;databaseName=ibm_ucd
    ```

    If your database server uses integrated security, include the integratedSecurity parameter, as in the following example:

    ```
    jdbc:sqlserver://database\_server:1433;databaseName=ibm_ucd;integratedSecurity=true;
    ```

    **Note:** Before using the `integratedSecurity=true` option, place the `sqljdbc_auth.dll` file in the `\bin` directory of your JRE. The file can be found in the `\auth\x86` or `\auth\x64` directory of the SQL Server installation files.

6.  Finish by entering the database user name and password. 
7.   Before you start the server, log into the database and run the following command: 

    ```
    ALTER DATABASE database\_name SET READ_COMMITTED_SNAPSHOT ON
    ```

    Use the name of the database for `database\_name`.

8.   Start the server. 

**Parent topic:** [Installing the server database](../../com.ibm.udeploy.install.doc/topics/DBinstall.md)

