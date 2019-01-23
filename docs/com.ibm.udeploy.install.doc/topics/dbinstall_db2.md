# Configuring a DB2 database for the HCL UrbanCode Deploy server

To use a DB2® database with the server, before you install the server, install the IBM® DB2 database and provide the JDBC JAR file for the server installation process.

DB2 is bundled with HCL® UrbanCode™ Deploy. Before you install the HCL UrbanCode Deploy server, install DB2 version 9.7 or later. If you are evaluating HCL UrbanCode Deploy, you can install the database on the same computer as the HCL UrbanCode Deploy server.

When you install HCL UrbanCode Deploy, you need the DB2 connection information and a user account with table-creation privileges.

**Note:** It is recommended that the database be encoded in UTF-8. Changing the database to a case-sensitive collation is also recommended.

1.  Create a database with a default page size of 32 K.Type the following text on the DB2 command line to create a database that is named ucd:

    ```
    create database ucd pagesize 32 k
    ```

2.   Increase the transaction log size of the database. Type the following text on the DB2 command line to increase the transaction log size of a database that is named ucd to 30720 blocks:

    ```
    update db cfg for ucd using logfilsiz 30720 immediate
    ```

    **Note:** If you plan to use the WebSphere® Application Server - Configure plug-in with this installation of HCL UrbanCode Deploy, use the following command:

    ```
    update db cfg for ucd using logfilsiz 30720 logprimary 100 immediate
    ```

    For more information, see the Troubleshooting page in the [plug-in documentation](https://developer.ibm.com/urbancode/plugindoc/ibmucd/ibm-configure/1-2/troubleshooting/).

3.  Obtain the DB2 JDBC driver.The JDBC JAR file is included among the installation files for the database. The driver is unique to the edition you are using.

    When multiple drivers are available, you might need to consult with the database provider to determine which driver to use. The JDBC driver version that you must use might depend on the version of the database and the version of Java™ used by the HCL UrbanCode Deploy server.

4.  Copy the JDBC JAR file to installer\_directory\\lib\\ext. 
5.  If you are installing on IBM z/OS®, edit the file ibm-ucd-install/database/deploy/ud-foreign-keys.ddl to add the following line of code:

    ```
    SET CURRENT RULES = 'STD';
    ```

6.   Begin server installation. See [Installing the server](serverInstall.md). When you are prompted for the database type, enter db2. 
7.   Provide the JDBC driver class HCL UrbanCode Deploy uses to connect to the database. The default value is `com.ibm.db2.jcc.DB2Driver`.
8.  Next, provide the JDBC connection string.Typically, it is similar to the following code:

    ```
    jdbc:db2://DB\_URL:DB\_PORT/DB\_NAME
    ```

    For example:

    ```
    jdbc:db2://localhost:50000/ibm_ucd
    ```

9.  Finish by entering the database user name and password. 

**Parent topic:** [Installing the server database](../../com.ibm.udeploy.install.doc/topics/DBinstall.md)

