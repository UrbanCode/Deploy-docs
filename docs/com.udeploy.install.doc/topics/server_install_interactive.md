# Installing the server in interactive mode

In interactive mode, you install the server by typing configuration information on the command line.

-   Make sure that you have a license server with available licenses. See [License management](../../com.udeploy.doc/topics/licenseManage.md).
-   Ensure that the system that you are installing the server on meets the system requirements. See [System requirements and performance considerations](sysRequire.md).
-   Ensure that a supported version of a Java™ Runtime Environment \(JRE\) or Java Development Kit \(JDK\) is installed on the computer on which you are installing HCL UrbanCode Deploy. For more information, see [System Requirements for IBM® UrbanCode Deploy](http://www-01.ibm.com/support/docview.wss?uid=swg27038801). Supported JREs are included with the installation files.

    **Important:** Beginning in version 6.2.2, the HCL UrbanCode Deploy server and agent relays require a Java Runtime Environment \(JRE\) or Java Development Kit \(JDK\) version 8.

    **Important:** 

    For best results, download and use the latest available version of the IBM Java Runtime Environment \(JRE\) for the HCL UrbanCode Deploy server and agent relays. An IBM JRE is available as a separate download. See the [IBM developer kits](https://www.ibm.com/developerworks/java/jdk/) page to get the latest version. Install the IBM JRE according to the documentation on the page. Be sure to set the JAVA\_HOME system variable to the location of the IBM JRE. If you are updating or changing the JRE to the latest version, see [Changing or updating the JRE of servers](../../com.udeploy.doc/topics/jre_change.md#) and [Updating the JRE location for agent relays](../../com.udeploy.doc/topics/update_JRE_agent_relays.md#) for instructions. For documentation on the IBM JRE, see [IBM SDK, Java Technology Edition](https://www.ibm.com/support/knowledgecenter/SSYKE2/welcome_javasdk_family.html).

    Using JREs or Java development kits other than those provided by IBM might cause unexpected results.

-   Set the JAVA\_HOME system variable to the location of the JRE or JDK that you are using.
-   If you are installing the server to be compliant with Federal Information Processing Standards \(FIPS\), the computer must use a supported version of an IBM JRE or JDK.
-   If you are installing the server in a production environment, install and configure the server database before you install the server. See [Installing the server database](DBinstall.md). If you are not installing in a production environment, you can install an instance of Apache Derby during the installation steps. You can migrate the database to a different database system later, as described in [Migrating the server database](migrate_database.md).
-   If you are using a database other than Apache Derby for the server, place the JAR file for the database driver in the lib/ext folder of the installation program.
-   If you are installing on AIX®, the unzip program is required.
-   Make sure that your networks and firewalls allow communication on the required ports. See [Firewall and communication configuration](agent_firewalls.md).
-   To install and run the server on Linux™ as a non-root user, create a user to use when you install and run the server. Also, ensure that the user has read and write permission to the folder to which you are installing the server.
-   Ensure that there is no limit on the maximum memory size and virtual memory size. For example, on most Linux systems, you can run the `ulimit -m` and `ulimit -v` commands and ensure that both return the value `unlimited`. To find out how to remove the limit on the maximum memory size and virtual memory size, see the documentation for the operating system.

If you are adding the server to a high-availability cluster, including as a cold standby server:

-   Configure the high-availability cluster; see [Setting up high-availability clusters](../../com.udeploy.doc/topics/server_install_clustered.md).
-   Ensure that the system on which you are installing the new server has a connection to the cluster network storage and that the system can connect to the database that the cluster is using.
-   Each server in the cluster must run the same version of HCL UrbanCode Deploy.

For information about high-availability clusters, see [High availability and failover](../../com.udeploy.doc/topics/ha_config_ov.md). For information about cold standby, see [Adding cold standby servers](server_install_cold.md#).

**Note:** HCL UrbanCode Deploy is also available as a hosted service. In this case, IBM hosts the server for you. For more information, see the [IBM Marketplace](https://www.ibm.com/us-en/marketplace/application-release-automation).

The properties that are set during installation are recorded in the file server\_install/conf/server/installed.properties on the server.

1.   Download and extract the installation files for HCL UrbanCode Deploy. These files are available for download from the IBM Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
2.  If you are using a database other than Apache Derby, place the JAR file for the database in the lib/ext folder of the installation files.
3.  From the command line, run the server installer program. 

    -   On Windows, run the install-server.bat file.
    -   On Linux, run ./install-server.sh.
    -   To install a FIPS-compliant server, add the switch `-fips` to the command, such as `install-server.sh -fips`.

        **Note:** If you install a FIPS-compliant server, cloud provisioning is not available. Your JVM connects to only FIPS 140-2 certified IBM providers.

    Depending on your system settings, you might need to run this file as an administrator.

4.   Specify the configuration information as the installation program prompts you. 
    -   ****Enter the directory of the server to upgrade\(leave blank for installing to a clean directory\).****

        To install HCL® UrbanCode™ Deploy, press Enter.

    -   ****Enter the home directory for the JRE/JDK that the new server or already installed server uses.****

        Specify the location of the JRE or JDK for the server. The default value is the value of the JAVA\_HOME system variable.

5.  Read the license agreements for the software package. Press Enter to show one page at a time, or press F and then press Enter to show the entire license at once.
6.  If you agree to the terms of all of the license agreements, press Y and then press Enter.
7.  Specify the following information as the installation program prompts you.Accept the default values \(displayed within brackets\) by pressing Enter. If two options are given, such as `[Y/n]`, the capitalized option is the default value.
    -   ****Enter the directory where the HCL® UrbanCode™ Deploy server should be installed.****

        Specify the installation directory for the server. The default server installation directory is /opt/ucd/server on Linux™ and C:\\Program Files\\ucd\\server on Windows™.

        **Note:** Do not use any shell expansions or abbreviations, such as the tilde character \(`~`\).

    -   ****The specified directory does not exist. Do you want to create it?****

        Press Y to create the installation directory.

    -   ****Will this server be used as a node in a high availability cluster?****

        Press Y to add the server to a high-availability \(HA\) cluster, including cold standby clusters. Selecting this option sets the property com.urbancode.ds.UDeployServer.multiserver to true on the new server, which indicates that it is part of a high-availability installation.

    -   ****Where should the server store application data such as logs, plugins, and keystores?****

        Type the name of the application data directory. The directory must be accessible to the server, and you must have the appropriate permissions. If you are installing a node in a high-availability cluster, this directory must be on the cluster network storage. The default application data folder is /opt/ibm-ucd/server/appdata on Linux™ and C:\\Program Files\\ibm-ucd\\server\\appdata on Windows™.

        Depending on whether the shared folder exists or is empty, you are prompted with one of the following options:

        -   If the folder does not exist, you are prompted with the following option: **The specified directory for application data doesn't exist. Do you want to create it?**. Press Y to create the application data directory. If you select `N`, the installation process ends.
        -   If the shared folder exists and is not empty, you are prompted with the following option: **The specified directory for shared resources already exists and is non-empty. Do you want to use the existing data?**. Press Y to use the data. If you select `N`, the installation process ends; in this case, you must manually clear the application data folder to use it.
        -   If the shared folder exists but is empty, the folder is used and you are not prompted to use the existing data.
        **Note:** Do not use any shell expansions or abbreviations, such as the tilde character \(`~`\).

    -   ****What host name will users access the web UI at?****

        If you are installing a stand-alone server, specify the host name of the computer that hosts the server. If you are installing a stand-alone server in a production environment, consider specifying a host name that is not tied to the physical computer. By specifying such a host name, you can expand the server to a high-availability system later. If you are installing a server in a high-availability cluster, specify the host name of the load balancer for the cluster.

        The server listens on all IP addresses that are available to it, not just this host name or IP address.

    -   ****Do you want the Web UI to always use secure connections using SSL?****

        Press Y to use secure connections to the server. If you select this option, you must configure a certificate for the server; see [Configuring SSL on Apache Tomcat and LDAP servers](../../com.udeploy.doc/topics/ssl_config.md).

    -   ****Enter the port on which the Web UI should listen for secure HTTPS requests.****

        Specify the HTTPS port for the server. The default value is `8443`. If you are installing HCL® UrbanCode™ Deploy, UrbanCode Velocity, and IBM® UrbanCode™ Release, be sure to use a different port for each product. If you are installing multiple instances of HCL® UrbanCode™ Deploy on the same computer, be sure to use a different port for each instance.

    -   ****Enter the port on which the Web UI should redirect unsecured HTTP requests.****

        Specify the HTTP port for the server. The default value is `8080`.If you are installing HCL® UrbanCode™ Deploy, UrbanCode Velocity, and IBM® UrbanCode™ Release, be sure to use a different port for each product. If you are installing multiple instances of HCL® UrbanCode™ Deploy on the same computer, be sure to use a different port for each instance.

    -   ****Enter the initial password for the admin user.****

        Specify the starting password for the administrator account on the server. The administrator user name is `admin`. Then, type the password again to verify it.

    -   ****Enter the port to use for JMS agent communication.****

        Specify the port that JMS agents use to contact the server. The default value is `7918`.

    -   ****Do you want the Server and Agent communication to require mutual authentication? This requires a manual key exchange between the server and each agent. See the documentation for more details.****

        If you use mutual authentication, you must manually exchange a key between the server and each agent. For more information about this option, see [Configuring mutual authentication](ssl_mutual_auth.md).

    -   ****Enter the web agent communication URL for this server.****

        The WebSocket secure URL must have the format `wss://host-or-ip:port`. For example, `wss://myUCD:7919`. The default WebSocket port is `7919`. Each server must have a unique URL, and every server in a HA cluster must be able to connect to this URL. Web agents use this URL to communicate with the sever. When you install an agent, you determine its type, either **WEB** or **JMS**.

    -   ****Enter the RCL server path\(s\).****

        Specify the connection information for the license server. You can specify the port and host name or IP address for the license server, such as `27000@RCLServer.example.com`. To avoid problems when a license server is not available, you can specify multiple license servers. In this case, separate each address with colons on Linux™ and UNIX™ or semicolons on Windows™, as in the following example: `27000@RCLServer.example.com;27000@backupRCLServer.example.com`. For more complicated license server scenarios, see this document: [http://www-01.ibm.com/support/knowledgecenter/SSSTWP\_8.1.4/com.ibm.rational.license.doc/topics/r\_specify\_lic\_servers.html](http://www-01.ibm.com/support/knowledgecenter/SSSTWP_8.1.4/com.ibm.rational.license.doc/topics/r_specify_lic_servers.html). For more information about licensing, see [License management](../../com.udeploy.doc/topics/licenseManage.md). 

        **Note:** If you add the server to an existing high-availability cluster, you are not prompted to provide information about a license server.

    -   ****Create database schema?****

        In most cases, press Y to create new schema definitions in the database. However, if you have a pre-populated database, such as if you are adding a server to a cluster, press N. If you are adding the server to a high-availability cluster, press N unless the server is the first node in the cluster.

    -   ****Enter the database type to use.****

        Specify the type of database. If you select `derby`, the installation program installs a new instance of Apache Derby for the server to use. Depending on the type of database that you select, new fields appear for information about the database. Valid values are `derby`, `mysql`, `oracle`, `sqlserver`, `db2`, and `db2zos`.

        **Warning:** Derby is for evaluation purposes only; do not use Derby for a production server. In addition, if you install the server as a node in a high-availability cluster, you cannot use Derby.

        If you specify `db2zos`, you are prompted to enter the database name, which is not necessarily the database location.

        If you specify a type other than `derby`, specify the following database-related parameters:

        -   ****Enter the database driver.****

            Specify the class name of the database driver.

        -   ****Please place the jar file containing the driver for your database inside the lib/ext directory in the IBM UrbanCode Deploy installer.****

            Verify that you placed the JAR file for the database driver in the lib/ext folder of the installation program and then press Enter.

        -   ****Enter the database connection string.****

            Specify the complete connection string for the database, such as the following string:

            ```
            jdbc:db2://localhost:50000/ibm_ucd
            ```

        -   ****Enter the database schema name.****

            Specify the name of the database schema to create or use. This field is required on Windows™ if the user has the database administrator role. This field applies only to Oracle databases.

    -   ****Enter the database username.****

        Specify the user name for the database. If you are creating the database schema, this user must have permission to create tables in the database.

    -   ****Enter the database password.****

        Specify the password for the database.

8.  If you are installing on Windows, the installation program prompts you with the following questions after a pause:
    -   ****Do you want to install the Server as Windows service?****

        Press Y to install the server as a Windows™ service.

    -   ****Enter a unique service name. No spaces allowed.****

        Specify a name for the Windows™ service. The name must be unique on the system and must not contain spaces.

    -   ****Enter the user account name including domain path to run the service****

        Specify the user account with which to run the service, including the domain path. Prefix local accounts with a period, such as .\\localsystem.

    -   ****Do you want to start the service automatically?****

        Press Y to start the server automatically. Otherwise, you can start and stop the server manually. See [Starting and stopping the server](run_server.md).

    -   ****User account password****

        Specify the password for the user account.


The installation program installs the server. If you install the server as a node in high-availability cluster, the installer loads the existing encryption keystore that is in the shared storage folder by using the default settings. If the default password is incorrect, you are prompted for the password. If after three attempts you do not enter the correct password, the installation process stops. If the keystore has more than one alias, you are prompted to specify an alias.

To start the server, see [Starting and stopping the server](run_server.md).

If you selected mutual authentication, set up the authentication. See [Configuring mutual authentication](ssl_mutual_auth.md).

When you run the server for the first time, you might see an error message that says that no agent or tag is configured to import new component versions. To import component versions, including built artifacts, you must use an agent, and the server requires that you specify a default agent for this purpose. You can override this default setting when you create a component. Follow these steps to specify a default agent or agent tag:

-   To specify a default agent, click **System** \> **System Settings** and under **General Settings**, clear the **Use Agent Tag For Integration** check box. Then, select an agent in the **Agent for Version Imports** list. Then, at the bottom of the page, click **Save**.
-   To specify a default agent tag, click **Settings** \> **System Settings** and under **General Settings**, clear the **Use Agent Tag For Integration** check box. Then, select an agent tag in the **Agent Tag for version imports** list. Then, at the bottom of the page, click **Save**. If no tags are listed, add a tag to one or more agents on the server.

If you see "Out of memory" errors, increase the amount of memory that is available to the HCL UrbanCode Deploy service. See [Increasing the amount of memory that is available to the server](../../com.udeploy.doc/topics/server_memory.md).

If you are using Derby, you might see the following error in the results of the installation program:

```
[echo]     waiting for db to start - 6 seconds remaining
[echo]     waiting for db to start - 3 seconds remaining
[echo] Could not start database
[echo] Stopping embedded database ...
[java] Tue Feb 04 09:11:25 EST 2014 : Could not connect 
  to Derby Network Server on host localhost, port 11377: 
  Connection refused
```

If you see this error, you must change the default security settings for the Java installation on the server:

1.  Open the Java security policy file in a text editor. If you are using a Java Runtime Environment \(JRE\), this file is at the location JAVA\_HOME/lib/security/java.policy, where JAVA\_HOME is the base folder of the Java installation. If you are using a Java Development Kit \(JDK\), the file is at the location JAVA\_HOME/jre/lib/security/java.policy.
2.  In the java.policy file, in the section that is labeled `// default permissions granted to all domains`, within the `grant{}` block, add the following code:

    ```
    permission java.net.SocketPermission "localhost:11377", "listen";
    ```

3.  Run the installation program again.

**Parent topic:** [Installing the server](../../com.udeploy.install.doc/topics/serverInstall.md)

