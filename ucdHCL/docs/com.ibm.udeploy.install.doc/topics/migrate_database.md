# Migrating the server database

The server installation files include a script that migrates the server database from Derby to another database system. You can not migrate from any database other than Derby.

Install the database that you want to migrate to and create an account for the server to use.

1.   Download and extract the installation files for HCL® UrbanCode™ Deploy. These files are available for download from the IBM® Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
2.   Place the JAR file for the new database in the lib/ext folder of the installation files. 
3.  Stop the server.
4.  Back up the current database.
5.  From the command line, run the database migration script. 

    -   On Windows™, run the migrate-database.bat file.
    -   On Linux™, run the migrate-database.sh file.
    Depending on your system settings, you might need to run this file as an administrator.

6.  Follow the instructions in the migration script, specifying the current location of the server and the connection information for the new database.
7.  When the migration script is finished, restart the server and verify that the data has been migrated.

    If the migration fails due to memory issues, increase the memory that is available to the script. To increase the memory, open the migration script and find the line of code that says `'ANT_OPTS="-Xmx1024m"`. The `1024m` in this code represents 1024 megabytes of memory. Increase this number and run the migration script again.


**Parent topic:** [Upgrading and migrating](../../com.ibm.udeploy.doc/topics/c_node_upgrading.md)

