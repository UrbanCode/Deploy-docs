# Adding the blueprint design server database to the engine MariaDB database

If you have an installed Heat orchestration engine, you can reuse the engine database for the blueprint design server rather than installing a separate database.

Install an engine that is provided with HCL® UrbanCode™ Deploy. See [Installing an engine in interactive mode](install_engine_interactive.md#) or [Installing an engine in silent mode](install_engine_silent.md#).

1.   Log in to the MariaDB database on the computer that hosts the engine. The default user name is `root`, and the default password is `passw0rd`, as in the following example:

    ```
    mysql -u root -ppassw0rd
    ```

2.   Create a user for the blueprint design server to use: 

    ```
    CREATE USER 'ibm_ucdp'@'localhost' IDENTIFIED BY 'password';
    ```

3.  Create a database:

    ```
    CREATE DATABASE ibm_ucdp;
    ```

4.  Grant permissions for the user:

    ```
    GRANT ALL ON ibm_ucdp.* TO 'ibm_ucdp'@'%' IDENTIFIED BY 'password' WITH GRANT OPTION;
    ```

5.   Type `quit` to exit the MariaDB command-line console. 
6.   Obtain the MariaDB JDBC driver. 
7.   Either note the location of the JDBC JAR file or place the file in the installation\_directory/ibm-ucd-patterns-install/web-install/media/server/opt/tomcat/lib folder. 
8.   Begin blueprint design server installation. See [Installing the blueprint design server](install_server_bds.md#). When you are prompted for the database type, enter mariadb. 
9.   Provide the JDBC driver class that the blueprint design server uses to connect to the database. The default value is `org.mariadb.jdbc.Driver`.
10.  Next, provide the JDBC connection string. Typically, it is similar to the following code:

    ```
    jdbc:mariadb://DB\_URL:DB\_PORT/DB\_NAME
    ```

    For example, if database is on the same computer as the blueprint design server and uses the default port, the JDBC connection string resembles the following code:

    ```
    jdbc:mariadb://localhost:3306/ibm_ucdp
    ```

11.  Finish by entering the database user name and password. 

Install the blueprint design server. See [Installing the blueprint design server](install_server_bds.md#).

**Parent topic:** [Blueprint design server database configuration](../../com.edt.doc/topics/install_database_bds_ov.md)

