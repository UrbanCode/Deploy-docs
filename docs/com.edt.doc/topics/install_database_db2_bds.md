# Configuring a DB2 database for the HCL UrbanCode Deploy blueprint design server

To use a DB2® database with the blueprint design server, before you install the blueprint design server, install the IBM® DB2 database and provide the JDBC JAR file for the server installation process.

DB2 is bundled with HCL® UrbanCode™ Deploy.

Before you install the blueprint design server, install and start a DB2 version 9.7 or later server on a Windows™ or Linux™ system. You must also create a DB2 user with table-creation privileges. See [IBM DB2 10.5 for Linux, Unix and Windows documentation](http://www.ibm.com/support/knowledgecenter/SSEPGG_10.5.0/com.ibm.db2.luw.kc.doc/welcome.html).

When you install the HCL UrbanCode Deploy blueprint design server, you need the DB2 connection information and a user account with table-creation privileges. If you are evaluating the blueprint designer, you can install the database on the same host as the blueprint design server.

**Note:** The database must be encoded in UTF-8.

1.   Open a command-line window and log in to the database as a user with table-creation privileges. The command to log in to the database server and start DB2 input interactive mode resembles this example:

    ```
    db2
    ```

    The command line shows a prompt that looks like this example:

    ```
    db2 =>
    ```

2.   From the DB2 input interactive mode, create a database with a default page size of 32 K. Type the following text on the command line to create a database that is named ibm\_ucdp:

    ```
    create database ibm_ucdp pagesize 32 K
    ```

3.   Type `quit` to exit the DB2 command line. 
4.   Obtain the DB2 JDBC driver. The JDBC JAR file is included among the installation files for the database. The driver is unique to the edition you are using.

    When multiple drivers are available, you might need to consult with the database provider to determine which driver to use. The JDBC driver version that you must use might depend on the version of the database and the version of Java™ used by the HCL UrbanCode Deploy server.

5.   Either note the location of the JDBC JAR file or place the file in the installation\_directory/ibm-ucd-patterns-install/web-install/media/server/opt/tomcat/lib folder. 
6.   Begin blueprint design server installation. See [Installing the blueprint design server](install_server_bds.md#). When you are prompted for the database type, enter db2. 
7.   Provide the JDBC driver class that the blueprint design server uses to connect to the database. The default value is `com.ibm.db2.jcc.DB2Driver`.
8.   Next, provide the JDBC connection string. Typically, it is similar to the following code:

    ```
    jdbc:db2://DB\_URL:DB\_PORT/DB\_NAME
    ```

    In the following example, the value for DB\_URL is `localhost`, the value for DB\_PORT is `50000`, and the value for DB\_NAME is `ibm_ucdp`:

    ```
    jdbc:db2://localhost:50000/ibm_ucdp
    ```

9.   Finish by entering the database user name and password. 

**Parent topic:** [Blueprint design server database configuration](../../com.edt.doc/topics/install_database_bds_ov.md)

