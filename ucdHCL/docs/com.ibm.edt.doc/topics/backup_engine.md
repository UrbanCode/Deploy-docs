# Backing up engines

To back up a the Heat engine that is required for the HCL® UrbanCode™ Deploy blueprint designer, back up its database.

**Note:** These instructions are for an engine that you installed through HCL UrbanCode Deploy. If you extended a different Heat engine, follow the backup and restore instructions from the engine vendor.

1.   To back up the engine manually, use the following steps: 
    1.   Stop the engine. See [Stopping the blueprint designer, cloud discovery service, and engine](stop_patterns.md).
    2.   Back up the engine database. By default, the engine uses a MariaDB or MySQL database on the same system as the engine. However, if the engine is part of a high-availability cluster, the database might be on a different system. You must back up the database that is named `heat`. Also, if you installed a Keystone service with the engine, you must also back up the database that is named `keystone`. You can use the mysqldump command to create an SQL file backup of these databases, as in the following example:

        ```
        mysqldump --databases heat keystone -u root -ppassw0rd > engineDBBackup.sql
        ```

    3.   If you changed the engine configuration files in the /etc/heat/ folder, copy this folder to a secure backup location. 
    4.   Start the engine. See [Starting the blueprint designer, cloud discovery service, and engine](start_patterns.md).
2.   To back up the engine by using a script, use the following steps: 

    **Note:** The script that backs up the engine is available in only versions 6.2.1.1 and later. You should use the default Keystone service that you installed with the Heat engine.

    1.   Stop the engine. See [Stopping the blueprint designer, cloud discovery service, and engine](stop_patterns.md).
    2.   Run the engine backup script. The script is supplied with the engine installation media and is in the /extracted\_location/ibm-ucd-patterns-install/engine\_install/resources/tools/ folder, where extracted\_location is where you extracted the engine installation media. The script performs the following actions:

        -   Creates a backup of the Heat engine database.
        -   Creates a backup of the Keystone service database.
        -   Creates copies of necessary configuration files.
        -   Packages all created files into a compressed file.
        -   Creates a restoreengine\_versionEngine.sh file to run when you restore the engine. The value for the engine\_version variable is Juno if you run a Juno level engine or Kilo if you run a Kilo level engine.
        -   Restarts the Heat engine and Keystone services.
        Run the following command:

        ```
        /extracted\_location/ibm-ucd-patterns-install/engine-install/resources/tools/create-engine-backup.sh
        ```

        The compressed file is at ./backup.package.number.tar.gz, where number represents the time of package creation.


To restore HCL UrbanCode Deploy from a backup, see [Restoring a backup](../../com.ibm.udeploy.doc/topics/arch_data_recovery.md).

**Parent topic:** [Backing up and recovering](../../com.ibm.edt.doc/topics/backup_recover.md)

