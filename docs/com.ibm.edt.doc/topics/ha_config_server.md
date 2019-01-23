# Setting up clusters of servers

To configure a cluster of servers, set up a shared database and file system for the servers to use.

-   Each server in the cluster must run the same version of HCL® UrbanCode™ Deploy.
-   Ensure that each server can connect to each other server on the network. For example, ensure that your firewall rules allow the servers to communicate over HTTPS and JMS.

To set up servers in a clustered configuration, you install servers on separate systems and connect the servers to the same database and network storage. Several log and configuration files are stored in the shared network storage, but each server also independently maintains some configuration information, such as database and JMS connection information. The database stores other configuration information and runtime data, as well as other information. Because the servers share the database, all servers run on the same interval.

Then, you configure a load balancer to distribute the traffic between the servers. Instead of accessing the servers directly, users access the load balancer URL. To the users, that URL appears to host a single instance of the server with high capacity; users are unaware of the multiple servers.

**Note:** Servers, agents, and agent relays communicate in two different ways: via HTTP/HTTPS on the default ports 8080 and 8443 and via JMS on the default ports 7918 and 7916. To set up the cluster, you must configure the load balancer to distribute the HTTP/HTTPS traffic but not the JMS traffic. In general, load balancers work well with HTTP/HTTPS traffic because this traffic is stateless and works on a request and response cycle. By contrast, JMS connections are long-lived and include a state that is not visible to the load balancer. Therefore, in general, load balancers are not effective in balancing the JMS traffic and do not increase performance with respect to this traffic.

To ensure high availability of the JMS traffic, configure agents and agent relays for failover as described in [Configuring agents for failover](../../com.ibm.udeploy.install.doc/topics/configure_agent_failover.md) and [Configuring agent relays for failover](../../com.ibm.udeploy.install.doc/topics/configure_relay_failover.md). In addition, you can also use DNS-level redirection to allow multiple servers or relays to act as a cluster for redundancy.

1.   Set up a shared database for the servers to use. See [Installing the server database](../../com.ibm.udeploy.install.doc/topics/DBinstall.md).
2.   Set up network storage for the server configuration files. Because each cluster server must access the same configuration files, each server must have access to this network storage.
3.   Configure online and offline backups for the servers. See [Backing up the server](../../com.ibm.udeploy.install.doc/topics/server_backup.md#).
4.   Install a load balancer to send requests to the servers. The load balancer must be able to forward requests to the HTTP and HTTPS ports for the servers. For more information, see the documentation for your load balancer.

    **Note:** Do not configure a load balancer to distribute requests for the agent communication JMS port. To ensure agent and agent relay availability, configure them for failover.

    **Important:** You must configure the load balancer for session persistence, also known as session affinity.

5.   If you have one or more servers already installed, populate the network storage with configuration files for the servers: 
    1.   Stop one of the existing servers. 
    2.   On the server, mount the network storage. 
    3.   From the server installation directory, move the following files and folders to the network storage and update the existing server to access those files and folders. 

        Which folders you move depends on how the files are structured on the server and which version the server is running on:

        **If the server is running on version 6.1.1.5 or later and was not migrated from a version prior to 6.1.1.5**, the server has an application data folder. The default application data folder is /opt/ibm-ucd/server/appdata on Linux™ and C:\\Program Files\\ibm-ucd\\server\\appdata on Windows™. On high-availability systems, the application data folder is always on a shared network drive that each server can access. You can also tell whether the server has an application data folder by checking to see if the server installed.properties file has a value other than two periods \(`..`\) specified as the value of the server.appdata.dir property.

        In this case, follow these steps:

        1.  Move the application data folder to the network storage.
        2.  On the server, in the installed.properties file, update the server.appdata.dir property to the new location of the application data folder.
        **If the server was upgraded from a version prior to 6.1.1.5 to version 6.1.1.5 or later**, the server does not have an application data folder. In this case, you must move the folders into an application data folder on the network storage by running these steps:

        1.  On the network storage, create a folder to be the application data folder, such as /media/share/appdata.
        2.  Copy the following folders to the application data folder:

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
            For install\_folder, use the installation directory for the server. The default server installation directory is /opt/ucd/server on Linux and C:\\Program Files\\ucd\\server on Windows.

            **Note:** For versions prior to 6.2.0.2, the notification-templates folder is in the location install\_folder/conf/server/notification-templates and not in the application data folder. In this case, if you are using notification templates, you must share this folder in addition to the application data folder.

        3.  Verify that the application data folder has the correct folder layout. For example, if you use the /media/share/appdata folder for the application data folder, make sure that you have the following folders and files:

            -   /media/share/appdata/var/plugins
            -   /media/share/appdata/var/repository
            -   /media/share/appdata/var/sa
            -   /media/share/appdata/logs
            -   /media/share/appdata/conf/server/notification-templates
            -   /media/share/appdata/conf/encryption.keystore
            -   /media/share/appdata/conf/server.keystore
            -   /media/share/appdata/conf/collectors
            -   /media/share/appdata/patches
            -   /media/share/appdata/conf/server/log4j.properties
            Some of these files and folders might not exist yet.

        4.  On the server, in the installed.properties file, set the server.appdata.dir property to the new location of the application data folder.
        **If the server is running on a version prior to version 6.1.1.5**, the server does not have an application data folder. In this case, the server is accessing individual folders; you must put each of these folders on the network storage and create links from the old folder locations to the new folder locations:

        1.  Copy the following folders to the network storage:
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
        2.  Delete the old folders.
        3.  Create links from the old folder locations to the new folder locations.
    4.   Delete the original copies of the files and folders that you moved to network storage. \(In other words, delete the files on the local server and keep the files on the network storage.\) 
6.   If you terminate SSL at the server level, set the servers to use the same security certificate. For example, you can copy the certificate in the /opt/tomcat/conf/tomcat.keystore file to the other servers. When you import the certificate into other servers, in the server.xml file, set the keyAlias property to point to the imported certificate.
7.   Configure the license server for high availability. For information, see the Rational® Common Licensing documentation: [http://www-01.ibm.com/support/knowledgecenter/SSSTWP](http://www-01.ibm.com/support/knowledgecenter/SSSTWP). For high availability options for the license server, see [http://www-01.ibm.com/support/docview.wss?uid=swg27036356&aid=1](http://www-01.ibm.com/support/docview.wss?uid=swg27036356&aid=1).

After you configure the load balancer to distribute connections to the systems, users can connect to a single URL and use the entire cluster. The servers also ensure that the correct number of licenses are used, even if a user accesses multiple servers.

Several server processes behave differently than with individual servers. See [High-availability server processes](../../com.ibm.udeploy.admin.doc/topics/ha_servers.md#).

-   Add servers to the cluster. See [Adding servers to clusters](ha_add_server.md).
-   Set up cold standby servers to use for disaster recovery. See [Adding cold standby servers](../../com.ibm.udeploy.install.doc/topics/server_install_cold.md#).
-   Configure agents and agent relays for failover. See [Configuring agents for failover](../../com.ibm.udeploy.install.doc/topics/configure_agent_failover.md) and [Configuring agent relays for failover](../../com.ibm.udeploy.install.doc/topics/configure_relay_failover.md).

