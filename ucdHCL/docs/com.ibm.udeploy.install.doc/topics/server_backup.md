# Backing up the server

To back up the server, make a backup copy of the database and application data directory. Both frequent online backups and occasional offline backups are required.

**Parent topic:** [Backing up and recovering](../../com.ibm.udeploy.install.doc/topics/backup_recover.md)

## Online backups

Online backups happen frequently, and without stopping the server. For online backups, you need to back up only the database.

Because the database data is more important for deployments to run than the file system data, online backups typically include only the database and not the server file system and application data directory. Use the backup options for your database system.

**Note:** To make the online backups easier to restore, configure your database to create full regular restore points and to enable transaction logging. For example, the database might make full backups once a month and log transactions all the time. That way, you can restore the database at any time.

## Offline backups

Offline backups happen when the server is stopped, for example during a monthly maintenance window when you install operating system updates and other updates on the server and agent systems.

Offline backups must include both the database and the server file system, including the application data directory.

**Note:** Always back up the server directory and the database at the same time. Using a backup of the server directory and the database taken from different times can cause problems when you restore the backups.

Follow these steps to take an offline backup of the server:

1.   Stop the server. See [Starting and stopping the server](run_server.md).
2.   Create a full backup of the database. For instructions on backing up the database, see the documentation for your database.
3.   Back up the application data folder to a secure backup location. The default application data folder is /opt/ibm-ucd/server/appdata on Linux™ and C:\\Program Files\\ibm-ucd\\server\\appdata on Windows™. On high-availability systems, the application data folder is always on a shared network drive that each server can access. 
4.   Back up the conf folder. The default location of this folder is /opt/ibm-ucd/server/conf on Linux and C:\\Program Files\\ibm-ucd\\server\\conf on Windows. On high-availability systems, back up this folder for each server.
5.   Start the server. 

To restore HCL® UrbanCode™ Deploy from a backup, see [Restoring a backup](../../com.ibm.udeploy.doc/topics/arch_data_recovery.md).

