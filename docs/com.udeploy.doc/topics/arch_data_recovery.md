# Restoring a backup

To restore a backup of the server, stop the server and replace the existing files and databases with the backup files and databases.

You can restore the server, the blueprint design server, and the engine all at once, or you can restore only individual systems.

**Note:** These instructions are for an engine that you installed through HCL® UrbanCode™ Deploy. If you extended a different Heat engine, follow the backup and restore instructions from the engine vendor.

**Parent topic:** [Backing up and recovering](../../com.edt.doc/topics/backup_recover.md)

## Restore a backup of the server

1.  To restore the server from a backup, follow these steps:
2.   Stop the server. 
3.   Copy the server files from the backup to the application data directory, overwriting the current files. You must restore the backup files to the same location as the existing files because configuration files include system paths.
4.   Restore the database from the backup. 

    **Important:** You must restore the database from a backup that was taken at the same time as the backup of the application data directory.

5.   Restart the server. 

## Restore a backup of the blueprint design server

1.  To restore the blueprint design server from a backup, follow these steps:
2.   Stop the blueprint design server and cloud discovery service. 
3.   Restore the repository and workspace folders from the backup. By default, these folders are in the following locations:
    -   /opt/ibm-ucd-patterns/repositories
    -   /opt/ibm-ucd-patterns/workspace
4.   Restore the other folders that you backed up by using the instructions in [Backing up the blueprint design server](../../com.udeploy.install.doc/topics/backup_bds.md). You backed up the following folder locations by default:
    -   /opt/ibm-ucd-patterns/conf
    -   /opt/ibm-ucd-patterns/java/jre/lib/security/cacerts
    -   /opt/ibm-ucd-patterns/patches
5.   Restore the database from the backup. 
6.   If you backed up the cloud discovery service configuration file, restore that file and set the CLOUDDISCOVERYSERVICE\_SETTINGS\_FILE system variable to the location of the file. 
7.   Restart the blueprint design server and cloud discovery service. 

## Restore a backup of the engine

1.  To restore the engine from a backup, follow these steps:
2.   Stop the engine Heat services. See [Stopping the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/stop_patterns.md).
3.   Restore the database from the backup. The engine MySQL database is installed automatically on the same system as the engine, except in the case of a high-availability installation. In high-availability installations, the engine uses an external MySQL database. For example, if you used the mysqldump command to create a backup file that is named engineDBBackup.sql, you can restore the backup by running the following command:

    ```
    mysql -u root -ppassw0rd < engineDBBackup.sql
    ```

    **Attention:** This command overwrites existing information in the database with the contents of the backup.

4.   If you backed up the engine configuration files, restore them to the /etc/heat folder. 
5.   Start the engine Heat services. See [Starting the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/start_patterns.md). The RabbitMQ system that the engine uses is not persistent and therefore does not have any data to restore.

## Restore a backup of the engine by using a script

1.  To restore the engine from a backup that you created from the back up script, follow these steps:
2.   Extract the backup package that you created by running the backup script. The backup package is named backup.package.number.tar.gz, where number represents the time of package creation and contains both the contents of your engine and configuration files and the script to restore them. See [Backing up engines](../../com.udeploy.install.doc/topics/backup_engine.md#).
3.   To restore the engine, run the following command: 

    ```
    ./extracted\_location/backup.package.number/restoreengine\_versionEngine.sh
    ```

    In this command, extracted\_location is the folder where you extracted the compressed backup package and engine\_version represents the level of the Heat engine that you restore.


