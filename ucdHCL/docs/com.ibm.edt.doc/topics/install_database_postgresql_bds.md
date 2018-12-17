# Configuring a PostgreSQL database for the blueprint design server

To use a PostgreSQL database with the blueprint design server, before you install the blueprint design server, install the PostgreSQL database.

Before you install the blueprint design server, install PostgreSQL. If you are evaluating HCL® UrbanCode™ Deploy, you can install the database on the same system as the blueprint design server.

For example, the command to install PostgreSQL on a Red Had Enterprise Linux™ \(RHEL\) 7 system might look like the following example:

```
yum -y install postgresql-server
```

The command to initialize and start the PostgreSQL database on a RHEL 7 system might look like the following example:

```
postgresql-setup initdb ; systemctl start postgresql
```

**Note:** The blueprint design server requires data from the database to be encoded in UTF-8.

The installation files for the blueprint designer contain the JDBC file that is required for the blueprint design server to communicate with the PostgreSQL database.

1.   Open a command-line window and log in to the database as a user with table-creation privileges. The default PostgreSQL user is `postgres`.

    **Restriction:** If you install PostgreSQL on RHEL, you cannot access the database with the root user account. If you are logged in to RHEL 7 as the root user, you can access the `postgres` account by running the following command:

    ```
    su - postgres
    ```

    The command to log in to the database server might look like this example:

    ```
    psql
    ```

2.   Create a database. The following commands are an example of how you might create this database:

    ```
    CREATE DATABASE ibm_ucdp;
    ```

    ```
    CREATE USER ibm_ucdp WITH PASSWORD 'password';
    ```

    ```
    GRANT ALL PRIVILEGES ON DATABASE ibm_ucdp TO ibm_ucdp;
    ```

3.   To exit the PostgreSQL command line, type `\q`. 
4.   Configure the PostgreSQL database to communicate with the blueprint design server. 
    1.   Open the configuration file for host-based authentication. You specify the location of this file at server start. By default, the file is named pg\_hba.conf. By default, on RHEL 7 , the file is at /var/lib/pgsql/data/, and on Windows™, the file is at C:\\Program Files\\PostgreSQL\\version\_number\\data\\.
    2.   In the configuration file for host-based authentication, configure password-based authentication for the connection to your blueprint design server. For example, to specify hashed passwords for either an IPv4 or an IPv6 connection, set the METHOD parameter to md5. The settings resemble the following code:

        ```
        
        # TYPE  DATABASE    USER        CIDR-ADDRESS          METHOD
        # "local" is for Unix domain socket connections only
        local   all         all                               ident
        # IPv4 connections:
        host    all         all         192.168.2.0/24        **md5**
        # IPv6 connections:
        host    all         all         ::/0                  **md5**
        ```

        **Note:** You must not change your local authentication method.

    3.   In the configuration file for host-based authentication, specify the CIDR address for your blueprint design server. The CIDR address contains both the IP address of the connection and its routing prefix. See [http://www.postgresql.org/docs/9.3/static/auth-pg-hba-conf.html](http://www.postgresql.org/docs/9.3/static/auth-pg-hba-conf.html). For example, if you use an IPv4 connection, set the CIDR-ADDRESS to `ip\_address/routing\_prefix`. In the following code, the IPv4 CIDR-ADDRESS is set to 192.168.2.0/24:

        ```
        
        # TYPE  DATABASE    USER        CIDR-ADDRESS          METHOD
        # "local" is for Unix domain socket connections only
        local   all         all                               ident
        # IPv4 connections:
        host    all         all         **192.168.2.0/24**        md5
        
        ```

    4.   Open the PostgreSQL configuration file. The file is named postgresql.conf. By default, on RHEL 7, the file is at /var/lib/pgsql/data/, and on Windows, the file is at C:\\Program Files\\PostgreSQL\\version\_number\\data\\.
    5.   In the PostgreSQL configuration file, open the database communication port. Uncomment the line that contains the port parameter and provide the appropriate value. For example, to specify the default communication port for the JDBC connection, set the port to 5432. The line resembles the following code:

        ```
        port = 5432
        ```

    6.   In the PostgreSQL configuration file, provide the IP addresses to listen on. Uncomment the line that contains the listen\_addresses parameter and provide the appropriate value. For example, to listen on all addresses, set the listen\_addresses to '\*'. The line resembles the following code:

        ```
        listen_addresses = '*'
        ```

5.   Restart the database. For example, to restart in RHEL 7, run the following command:

    ```
    systemctl restart postgresql
    ```

6.   Begin server installation. See [Installing the blueprint design server](install_server_bds.md#) . When you are prompted for the database type, enter postgres. 
7.   Provide the JDBC driver class that the blueprint design server uses to connect to the database. The default value is `org.postgresql.Driver`.
8.   Next, provide the JDBC connection string. Typically, it uses this format:

    ```
    jdbc:postgresql://DB\_URL:DB\_PORT/DB\_NAME
    ```

    This example shows a JDBC connection string:

    ```
    jdbc:postgresql://localhost:5432/ibm_ucdp
    ```

9.   Enter the database user name and password that you created. 

**Parent topic:** [Blueprint design server database configuration](../../com.ibm.edt.doc/topics/install_database_bds_ov.md)

