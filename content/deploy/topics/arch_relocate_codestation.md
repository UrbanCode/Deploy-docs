# Relocating CodeStation {#arch_relocate_codestation .task}

You can move the CodeStation artifacts to a different location on the server.

By default, the server's log files and CodeStation artifacts are stored in the application data directory. You specified this directory when you installed the server. In the case of high-availability clusters, this directory is in a shared location where each server in the cluster can access it.

Ideally, this data is stored on robust network storage that is regularly synchronized with an off-site disaster recovery facility. In addition, the IBM® UrbanCode® Deploy server requires a fast network connection to this storage.

**Tip:** The following formula shows a good rule-of-thumb for determining CodeStation storage requirements: `average artifact size * number of versions that are imported per day * average number of days before cleanup`

1.  Follow these steps to move the location of the CodeStation artifacts:
2.   Stop the server. See [Starting and stopping the server](../../com.ibm.udeploy.install.doc/topics/run_server.md#).
3.   Move the CodeStation data to a new location. Which folders you move depend on whether the server uses an application data folder or not:

    -   If the server is running a version prior to version 6.1.1.5, the server does not use an application data folder.
    -   If the server is running version 6.1.1.5 or later, check the installed.properties file on the server. If the server.appdata.dir property in this file has a value of two periods, \(`..`\) the server does not use an application data folder. If the property has a value other than two periods, the server uses an application data folder.
    When you know whether the server has an application data folder or not, you can move the correct files to a new location.

    -   If the server uses an application data folder, complete these steps:

        1.  Move the application data folder to a new location. The default application data folder is /opt/ibm-ucd/server/appdata on Linux™ and C:\\Program Files\\ibm-ucd\\server\\appdata on Windows™.
        2.  On the server, in the installed.properties file, update the server.appdata.dir property to the new location of the application data folder.
        If the new application data folder is on a remote system, you might have to set the server.appdata.dir property to a remotely mounted folder or other network storage.

    -   If the server does not use an application data folder, complete these steps:
        1.  Move the following individual folders to new locations:
            -   install\_folder/var/plugins
            -   install\_folder/var/repository
            -   install\_folder/var/sa
            -   install\_folder/logs
            -   install\_folder/conf/server/notification-templates
            -   install\_folder/conf/encryption.keystore
            -   install\_folder/conf/server.keystore
            -   install\_folder/conf/collectors
            -   install\_folder/patches
            -   install\_folder/conf/server/log4j.properties
        2.  Create links from the previous folder locations to the new folder locations so that the server can continue to access the folders. For example, on Linux systems, you can use symbolic links, also known as symlinks.
4.   Start the server. 

**Parent topic:** [Server settings and configuration](../topics/settings_ch.md)

