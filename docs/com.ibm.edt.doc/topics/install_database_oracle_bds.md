# Configuring an Oracle database for the blueprint design server

To use an Oracle database with the blueprint design server, before you install the blueprint design server, install the Oracle database and provide the Java™ Database Connectivity \(JDBC\) JAR file for the blueprint design server installation process.

For evaluation purposes, the blueprint design server installer can install an Apache Derby database, but for a production system, you can use an Oracle database.

Before you install the blueprint design server, install an Oracle database. If you are evaluating the blueprint designer, you can install the database on the same system as the blueprint design server.

When you install the blueprint design server, you need the Oracle connection information and a user account with table-creation privileges.

The blueprint design server supports the following editions.

-   Oracle Database Enterprise
-   Oracle Database Standard
-   Oracle Database Standard One
-   Oracle Database Express

For most production systems, use an architecture that is based on Oracle Real Application Clusters \(RAC\).

No specific parameterization, optimization setting, or histogram generation is required. The blueprint design server does not require `n*` types, such as `nchar`, `nvarchar2`, and `nclob`. The blueprint design server does not support multiple databases.

**Note:** If you upgrade your database to version 12c, you must edit the installed.properties file on the server and add the following line of code:

```
hibernate.dialect=org.hibernate.dialect.Oracle10gDialect
```

**Note:** The database must be encoded in UTF-8.

1.   Obtain the Oracle JDBC driver. The JDBC JAR file is included among the Oracle installation files. The driver is unique to the edition you are using.

    When multiple drivers are available, you might need to consult with the database provider to determine which driver to use. The JDBC driver version to use might depend on the version of the database.

2.   Either note the location of the JDBC JAR file or place the file in the installation\_directory/ibm-ucd-patterns-install/web-install/media/server/opt/tomcat/lib folder. 
3.   Begin the blueprint design server installation. See [Installing the blueprint design server in interactive mode](install_server_interactive_bds.md). 
4.   When you are prompted for the database type, enter oracle. 
5.   Provide the JDBC driver class that the blueprint design server uses to connect to the database. The default value is `oracle.jdbc.driver.OracleDriver`.
6.   Provide the JDBC connection string. The format depends on the JDBC driver. Typically, it is similar to the following code:

    ```
    jdbc:oracle:thin:@DB\_URL:DB\_PORT:SID
    ```

    For example:

    ```
    jdbc:oracle:thin:@localhost:1521:ORCL
    ```

    In the case of Oracle RAC, you might need to specify properties in the connection string in the format of the following example:

    ```
    jdbc:oracle:thin:@(DESCRIPTION=(LOAD_BALANCE=on)(ADDRESS=(PROTOCOL=TCP)
      (HOST=host)(PORT=port))(CONNECT_DATA=(SERVICE_NAME=port)))
    ```

7.   Finish by entering the database user name and password. 

    **Note:** The schema name must be the same as the user name.


**Parent topic:** [Blueprint design server database configuration](../../com.ibm.edt.doc/topics/install_database_bds_ov.md)

