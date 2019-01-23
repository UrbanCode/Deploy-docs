# Blueprint design server database configuration

The HCL® UrbanCode™ Deploy blueprint design server requires a database. For production installations, you can install a database, or you can reuse an engine database.

If you are installing an evaluation server, you can also allow the blueprint design server installation program to install an Apache Derby database for you. In this case, you do not need to install a database yourself. However, you cannot use Derby for production blueprint design servers. Derby is for evaluation only. To use this method, run the installation program, and when the program prompts you for the type of database, specify Derby.

-   **[Configuring a DB2 database for the HCL UrbanCode Deploy blueprint design server](../../com.ibm.edt.doc/topics/install_database_db2_bds.md)**  
To use a DB2® database with the blueprint design server, before you install the blueprint design server, install the IBM® DB2® database and provide the JDBC JAR file for the server installation process.
-   **[Configuring an Oracle database for the blueprint design server](../../com.ibm.edt.doc/topics/install_database_oracle_bds.md)**  
To use an Oracle database with the blueprint design server, before you install the blueprint design server, install the Oracle database and provide the Java™ Database Connectivity \(JDBC\) JAR file for the blueprint design server installation process.
-   **[Configuring a MySQL or MariaDB database for the HCL UrbanCode Deploy blueprint design server](../../com.ibm.edt.doc/topics/install_database_mysql_bds.md)**  
To use a MySQL or MariaDB database with the blueprint design server, before you install the blueprint design server, install the database and provide the Java™ Database Connectivity \(JDBC\) JAR file for the blueprint design server installation process.
-   **[Configuring a Microsoft SQL Server database for the blueprint design server](../../com.ibm.edt.doc/topics/install_database_sql_bds.md)**  
To use a SQL Server database with the blueprint design server, before you install the blueprint design server, install the SQL Server database and provide the Java™ Database Connectivity \(JDBC\) JAR file for the blueprint design server installation process.
-   **[Configuring a PostgreSQL database for the blueprint design server](../../com.ibm.edt.doc/topics/install_database_postgresql_bds.md)**  
To use a PostgreSQL database with the blueprint design server, before you install the blueprint design server, install the PostgreSQL database.
-   **[Adding the blueprint design server database to the engine MariaDB database](../../com.ibm.edt.doc/topics/install_database_reuse_engine.md)**  
If you have an installed Heat orchestration engine, you can reuse the engine database for the blueprint design server rather than installing a separate database.

**Parent topic:** [Installing the blueprint design server](../../com.ibm.edt.doc/topics/install_server_bds.md)

