# Configuring an Oracle server database for the HCL UrbanCode Deploy server

To use an Oracle database with the server, before you install the server, install the Oracle database and provide the JDBC JAR file for the server installation process.

Before you install the HCL® UrbanCode™ Deploy server, install an Oracle database. If you are evaluating HCL UrbanCode Deploy, you can install the database on the same system as the HCL UrbanCode Deploy server.

When you install HCL UrbanCode Deploy, you need the Oracle connection information and a user account with resource, connect, create session, and create table privileges.

HCL UrbanCode Deploy supports the following editions.

-   Oracle Database Enterprise
-   Oracle Database Standard
-   Oracle Database Standard One
-   Oracle Database Express®

For most production systems, use an architecture that is based on Oracle Real Application Clusters \(RAC\).

No specific parameterization, optimization setting, or histogram generation is required. The server does not require `n*` types, such as `nchar`, `nvarchar2`, and `nclob`. The server does not support multiple databases.

**Note:** If you upgrade your database to version 12c, you must edit the installed.properties file on the server and add the following line of code:

```
hibernate.dialect=org.hibernate.dialect.Oracle10gDialect
```

**Note:** It is recommended that the database be encoded in UTF-8. Changing the database to a case-sensitive collation is also recommended.

1.  Obtain the Oracle JDBC driver.The JDBC JAR file is included among the Oracle installation files. The driver is unique to the edition you are using.

    When multiple drivers are available, you might need to consult with the database provider to determine which driver to use. The JDBC driver version that you must use might depend on the version of the database and the version of Java™ used by the HCL UrbanCode Deploy server.

2.  Copy the JDBC JAR file to installer\_directory\\lib\\ext. 
3.   Begin server installation. See [Installing the server](serverInstall.md). When you are prompted for the database type, enter oracle.
4.  Provide the JDBC driver class HCL UrbanCode Deploy uses to connect to the database.The default value is `oracle.jdbc.driver.OracleDriver`.
5.  Provide the JDBC connection string. The format depends on the JDBC driver.Typically, it is similar to the following code:

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

    If you have more than one server, specify the host name and port of each server, as in the following example:

    ```
    jdbc:oracle:thin:@(DESCRIPTION=(LOAD_BALANCE=on)
      (ADDRESS=(PROTOCOL=TCP)(HOST=server1)(PORT=port1))
      (ADDRESS=(PROTOCOL=TCP)(HOST=server2)(PORT=port2))
      (CONNECT_DATA=(SERVICE_NAME=service)))
    ```

6.  Finish by entering the database user name and password. 

    **Note:** The schema name must be the same as the user name.


**Parent topic:** [Installing the server database](../../com.udeploy.install.doc/topics/DBinstall.md)

