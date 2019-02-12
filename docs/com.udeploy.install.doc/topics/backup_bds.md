# Backing up the blueprint design server

To back up the blueprint design server, back up its database and the folders in which it stores blueprints and configuration files.

**Note:** Always back up the database and folders at the same time. Using a backup of the database and folders from different times can cause problems when you restore the backup.

1.   Stop the blueprint design server and the cloud discovery service. See [Stopping the blueprint designer, cloud discovery service, and engine](stop_patterns.md).
2.   Create a full backup of the database. For instructions on backing up the database, see the documentation for your database.
3.   Copy the repository and workspace folders to a secure backup location. By default, these folders are in the following locations:
    -   /opt/ibm-ucd-patterns/repositories
    -   /opt/ibm-ucd-patterns/workspace
4.   Copy the server configuration files to a secure backup location. The default location of these files is /opt/ibm-ucd-patterns/conf.
5.   If you imported certificates, back them up. By default, certificates are stored in the /opt/ibm-ucd-patterns/java/jre/lib/security/cacerts file.
6.   If you installed patches, back them up. The default location of these patches is /opt/ibm-ucd-patterns/patches.
7.   If you customized the cloud discovery service configuration file, back that file up. The location of the cloud discovery service configuration file is in the system variable CLOUDDISCOVERYSERVICE\_SETTINGS\_FILE. If this system variable is not set, the cloud discovery service is using a default configuration file and there is no need to back up the service.
8.   Start the blueprint design server and cloud discovery service. See [Starting the blueprint designer, cloud discovery service, and engine](start_patterns.md) 

To restore HCL® UrbanCode™ Deploy from a backup, see [Restoring a backup](../../com.udeploy.doc/topics/arch_data_recovery.md).

