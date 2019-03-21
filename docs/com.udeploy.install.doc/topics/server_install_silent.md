# Installing the server in silent mode

In silent mode, you specify the installation properties in a text file and then run the server installation without command-line prompts.

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

You specify the server installation properties in the install.properties file, which is located in the root folder of the installation files. During the installation process, the server stores these properties in the installed.properties file, which is in the conf/server folder of the server installation files. If you have an already existing installation, you can use its installed.properties file as an example of the properties.

**Note:** Some of the properties in the table below can be changed after the server has been installed and others cannot. After the server starts for the first time, the server adds other properties to the installed.properties file. Some of these additional properties can be changed and others cannot.

1.   Download and extract the installation files for HCL UrbanCode Deploy. These files are available for download from the IBM Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
2.  If you are using a database other than Apache Derby, place the JAR file for the database in the lib/ext folder of the installation files.
3.   Customize the installation by specifying the properties in the following table. If you do not specify a property, the default value is used. These properties are copied to the installed.properties file of the completed installation.

    If you specify a path in a property on a Windows system, you must escape any backslash \(\\\) characters that are in the path. For example, to set the install.server.dir property to C:\\ucd, specify install.server.dir=C\\:\\\\ucd. See [java.util Class Properties](http://docs.oracle.com/javase/6/docs/api/java/util/Properties.html#load%28java.io.Reader%29).

    **Note:** The server.initial.password needs to be specified or install will fail.

    |Property|Default value|Description|
    |--------|-------------|-----------|
    |agentcomm.keystore|     ```
../conf/server/s2s-client-identity.keystore
    ```

 |Used with Web agents. See, [Web agents](../../com.udeploy.doc/topics/web_agents.md)|
    |agentcomm.uri|     ```
wss://localhost:7919
    ```

 |WebSocket connection that is used to communicate with Web agents. The WebSocket secure URL must have the format `wss://host-or-ip:port`. Each server must have a unique URL, and every server in a HA cluster must be able to connect to this URL. Web agents use this URL to communicate with the sever.|
    |com.urbancode.ds.web.rest.integration.vsys.VsysHelper.timeout|120|The time, in seconds, that server waits while it provisions an IBM PureApplication® System environment. For complicated patterns, you might have to increase this value. Specify a value greater than the longest provision session requires. For example, if no provision is expected to take longer than 10 minutes, specify `900`, or 15 minutes.|
    |com.urbancode.ds.workflow.copyChildPropertiesToParentContext|true|Set this property to false if you are not using children process properties. This can provide a performance boost.|
    |database.databasename|None|The name of the database to use when you specify `db2zos` in the database.type property.|
    |database.derby.port|11377|The port for the Derby database. This property is used only for Derby databases.|
    |database.type|     ```
derby
    ```

 |The type of database. Valid values are `derby`, `mysql`, `oracle`, `sqlserver`, `db2`, and `db2zos`.**Warning:** Derby is for evaluation purposes only; do not use Derby for a production server. In addition, if you install the server as a node in a high-availability cluster, you cannot use Derby.

|
    |encryption.keystore|../conf/encryption.keystore|The path to the encryption keystore. This parameter is optional if you have an existing installation that you are upgrading.|
    |encryption.keystore.alias|`desedekeyuniqueID`|The encryption keystore alias. This parameter is optional if you have an existing installation that you are upgrading.|
    |hibernate.connection.driver\_class|The default value depends on the type of database|The class name of the database driver, such as `com.ibm.db2.jcc.DB2Driver` for DB2® or `org.apache.derby.jdbc.ClientDriver` for Derby.|
    |hibernate.connection.password|`password`|The password for the database connection. This password is encrypted during the installation process.|
    |hibernate.connection.url|`jdbc:derby://localhost:11377/data`|The connection URL for the database. For more information on building a database connection string, refer to documentation from your database provider.|
    |hibernate.connection.username|`ibm_ucd`|The user name for the database connection. Unless skip.db.install is set to `Y`, this user must have permission to create tables in the database.|
    |hibernate.default\_schema|None|The name of the database schema. This property is required only for Oracle databases on Windows.|
    |install.ha|`N`|Specify `Y` if the new server is part of a high-availability cluster. If you specify `Y`, Derby is not an option for the server. In this case, you must specify database information in properties such as database.type and hibernate.connection.url.|
    |install.java.home|The value of the JAVA\_HOME system variable|The location of the installation of Java to use. This value must match the value of the JAVA\_HOME system variable. It must also match the location of the JRE or JDK that you use to run the installation file.|
    |install.server.dir|    ```
/opt/ucd-7.0/server
    ```

 \(Linux\) or     ```
C:\Program Files\ucd\server
    ```

 \(Windows\)|The installation directory for the server.|
    |install.server.web.always.secure|`Y`|Specify `Y` to always use secure connections to the server. Specify `N` to allow non-secure connections.|
    |install.server.web.host|The host name of the server|If you are installing a stand-alone server, specify the host name of the computer that hosts the server. If you are installing a stand-alone server in a production environment, consider specifying a host name that is not tied to the physical computer. By specifying such a host name, you can expand the server to a high-availability system later. If you are installing a server in a high-availability cluster, specify the host name of the load balancer for the cluster.|
    |install.server.web.https.port|8443|Specify the HTTPS port for the server. The default value is `8443`. If you are installing HCL UrbanCode Deploy, UrbanCode Velocity, and IBM UrbanCode Release, be sure to use a different port for each product. If you are installing multiple instances of HCL UrbanCode Deploy on the same computer, be sure to use a different port for each instance.|
    |install.server.web.ip|0.0.0.0|The IP address that the server listens on. Specify `0.0.0.0` to listen on all addresses that are available to the system.|
    |install.server.web.port|8080|Specify the HTTP port for the server. The default value is `8080`.If you are installing HCL UrbanCode Deploy, UrbanCode Velocity, and IBM UrbanCode Release, be sure to use a different port for each product. If you are installing multiple instances of HCL UrbanCode Deploy on the same computer, be sure to use a different port for each instance.|
    |install.service|None|To install IBM UrbanCode Deploy as Windows service, enter install.service=Y.|
    |install.service.name|None|To install IBM UrbanCode Deploy as Windows service, enter install.service.name=silentUCD.|
    |install.service.login|None|To install IBM UrbanCode Deploy as Windows service, enter install.service.login=.\\\\localsystem.|
    |install.service.password|None|Enter the password for the administrative user.|
    |install.service.autostart|None|Enter install.service.autostart=N.|
    |license.server.url|None|Specify the connection information for the license server. You can specify the port and host name or IP address for the license server, such as `27000@RCLServer.example.com`. To avoid problems when a license server is not available, you can specify multiple license servers. In this case, separate each address with colons on Linux and UNIX or semicolons on Windows, as in the following example: `27000@RCLServer.example.com;27000@backupRCLServer.example.com`. For more complicated license server scenarios, see this document: [http://www-01.ibm.com/support/knowledgecenter/SSSTWP\_8.1.4/com.rational.license.doc/topics/r\_specify\_lic\_servers.html](http://www-01.ibm.com/support/knowledgecenter/SSSTWP_8.1.4/com.rational.license.doc/topics/r_specify_lic_servers.html). For more information about licensing, see [License management](../../com.udeploy.doc/topics/licenseManage.md). This parameter is optional if you have an existing installation that you are upgrading.|
    |server.activemq.queue.memory|`100 mb`|The memory limit for queues in Apache ActiveMQ. To prevent a single queue from using too much memory, this amount of memory should be less than one-fifth of the system memory limit in server.activemq.system.memory. Specify an integer value followed by `mb` for megabytes or `gb` for gigabytes.|
    |server.activemq.system.memory|`512 mb`|The total amount of memory that Apache ActiveMQ can use on the system. This amount of memory should always be much less than the maximum amount of memory that is allotted to the server. On Linux and Unix systems, the maximum server memory is set in the set\_env file, in the `JAVA_OPTS` parameter, in the `-Xmx` parameter. Specify an integer value followed by `mb` for megabytes or `gb` for gigabytes.|
    |server.activemq.topic.memory|`100 mb`|The memory limit for topics in Apache ActiveMQ. To prevent a single topic from using too much memory, this amount of memory should be less than one-fifth of the system memory limit in server.activemq.system.memory. Specify an integer value followed by `mb` for megabytes or `gb` for gigabytes.|
    |server.agentCommunicationAlwaysEncrypted|`false`|Set this property to true to accept connections only from agents that use secure connections.|
    |server.appdata.dir|The default application data folder is /opt/ibm-ucd/server/appdata on Linux and C:\\Program Files\\ibm-ucd\\server\\appdata on Windows.|The path to the application data directory. The directory must be accessible to the server, and you must have the appropriate permissions. If you are installing a node in a high-availability cluster, this directory must be on the cluster network storage.|
    |server.initial.password|None|Specify the starting password for the administrator account on the server. The administrator user name is `admin`.|
    |server.jms.mutualAuth|`false`|Specify `true` to require mutual authentication between servers and agents. See [Configuring mutual authentication](ssl_mutual_auth.md).|
    |server.jms.port|7918|Specify the port that JMS agents use to contact the server. The default value is `7918`. If you are using failover servers, you must list the JMS connection ports of those servers here, separated by commas. Each server must have a corresponding port number in this property, even if some of those servers use the same port.|
    |server.keystore|None|The path to the server keystore.|
    |server.keystore.password|`changeit`|The password for the server keystore. This password is encrypted during the installation process. Additionally, this password is initially assigned to the `encryption.keystore.password` property.|
    |skip.db.install|N|If the value is `Y` or `yes`, the installation process does not create the database schema. For example, you skip creating the schema if you have a pre-populated database, such as if you are adding a server to a cluster. In this case, you must still provide the database connection information in the other properties such as hibernate.connection.url.|
    |tomcat.key.alais|server|The keystore alias name.|

    The file looks similar to the following example:

    ```
    component.name=IBM UrbanCode Deploy
    component.directory=ucd/server
    version=6.0.0.0.123456
    nonInteractive=true
    
    install.server.dir=/opt/ucd/server
    install.java.home=/opt/IBM/ibm-java-i386-80
    install.server.web.always.secure=Y
    install.server.web.host=myserver.example.com
    install.server.web.https.port=8443
    install.server.web.ip=0.0.0.0
    install.server.web.port=8080
    database.type=derby
    hibernate.connection.username=ucd
    hibernate.connection.password=password
    hibernate.connection.url=jdbc:derby://localhost:11377/data
    database.derby.port=11377
    license.server.url=27000@RCLServer.example.com
    
    server.initial.password=admin
    ```

4.   Save the file. 
5.   Specify the `-silent` flag when running the installer. Add Run the installation file with the command `install-server.bat` on Windows or the command `./install-server.sh` on Linux. 

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

