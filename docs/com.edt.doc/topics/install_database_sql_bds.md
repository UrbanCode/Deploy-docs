# Configuring a Microsoft SQL Server database for the blueprint design server

To use a SQL Server database with the blueprint design server, before you install the blueprint design server, install the SQL Server database and provide the Java™ Database Connectivity \(JDBC\) JAR file for the blueprint design server installation process.

Before you install the blueprint design server, install a SQL Server database. If you are evaluating the blueprint designer, you can install the database on the same system as the blueprint design server.

When you install the blueprint design server, you need the SQL Server connection information, and a user account with table-creation privileges.

**Note:** The user account cannot have the sysadmin role.

**Note:** The database must be encoded in UTF-8.

To create the SQL Server database and user account, run the following commands:

```
CREATE DATABASE ibm_ucdp;

USE ibm_ucdp;

CREATE LOGIN ibm_ucdp WITH PASSWORD = 'password';

CREATE USER ibm_ucdp FOR LOGIN ibm_ucdp WITH DEFAULT_SCHEMA = ibm_ucdp;

CREATE SCHEMA ibm_ucdp AUTHORIZATION ibm_ucdp;

GRANT ALL TO ibm_ucdp;
```

1.   Obtain the SQL Server JDBC driver from the Microsoft™ site. The JDBC JAR file is not included among the installation files. Use the sqljdbc4.jar driver file, not the sqljdbc.jar file.

    When multiple drivers are available, you might need to consult with the database provider to determine which driver to use. The JDBC driver version to use might depend on the version of the database and the version of Java used by the blueprint design server.

2.   Either note the location of the JDBC JAR file or place the file in the installation\_directory/ibm-ucd-patterns-install/web-install/media/server/opt/tomcat/lib folder. 
3.   Begin the blueprint design server installation. See [Installing the blueprint design server in interactive mode](install_server_interactive_bds.md). When you are prompted for the database type, enter sqlserver. 
4.   Provide the JDBC driver class HCL® UrbanCode™ Deploy uses to connect to the database. The default value is `com.microsoft.sqlserver.jdbc.SQLServerDriver`.
5.   Next, provide the JDBC database connection string. The format depends on the JDBC driver. Typically, it is similar to the following code:

    ```
    jdbc:sqlserver://DB\_URL:DB\_PORT;DatabaseName=DB\_NAME
    ```

    For example:

    ```
    jdbc:sqlserver://localhost:1433;DatabaseName=ibm_ucdp
    ```

    If your database server uses integrated security, include the integratedSecurity parameter, as in the following example:

    ```
    jdbc:sqlserver://database\_server:1433;databaseName=ibm_ucdp;integratedSecurity=true;
    ```

6.   Finish by entering the database user name and password. 

**Parent topic:** [Blueprint design server database configuration](../../com.edt.doc/topics/install_database_bds_ov.md)

