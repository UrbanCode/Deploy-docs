# Installing agent relays in silent mode

In silent mode, you specify the installation properties in a text file and then run the agent relay installation without command-line prompts.

-   Ensure that the computer on which you are installing the agent relay has a supported version of the Java™ Runtime Environment \(JRE\) or Java Development Kit \(JDK\). For more information, see [System Requirements for IBM® UrbanCode™ Deploy](http://www-01.ibm.com/support/docview.wss?uid=swg27038801).

    **Important:** Beginning in version 6.2.2, the HCL® UrbanCode Deploy server and agent relays require a Java Runtime Environment \(JRE\) or Java Development Kit \(JDK\) version 8.

-   If the target computer has an IBM JRE or Java developer kit, update to a supported version of the IBM JRE or Java developer kit.

-   Set the JAVA\_HOME system variable to the location of the JRE or JDK that you are using.
-   Set the PATH variable to contain the location of the JRE or JDK that you are using.
-   Ensure that the firewall on the computer allows connection to the HCL UrbanCode Deploy server through HTTP/HTTPS and through JMS.
-   Install the HCL UrbanCode Deploy server.
-   Ensure that you have an authentication token for the relay. If you intend to use the component version replication option, the token must be assigned to a user with the server configuration permission `Read Artifact Set List`. For information about tokens, see [Setting server configuration security](../../com.udeploy.admin.doc/topics/security_system.md).
-   Set up an account on the computer for the agent relay to use.
-   Make sure that your networks and firewalls allow communication on the required ports. See [Firewall and communication configuration](agent_firewalls.md).
-   Ensure that there is no limit on the maximum memory size and virtual memory size. For example, on most Linux™ systems, you can run the `ulimit -m` and `ulimit -v` commands and ensure that both return the value `unlimited`. To find out how to remove the limit on the maximum memory size and virtual memory size, see the documentation for the operating system.

To install the agent relay in silent mode, you specify the installation properties in a properties file. The example.agentrelay.install.properties file is provided as an example of a properties file. The example.agentrelay.install.properties file is in the agent relay installation file.

1.   Download and extract the agent relay installer to the computer on which you want to install the agent relay: 
    -   To download the installer from the server, click **Help** ![](../images/help_button.gif), located in the upper-right corner of the page, and then click **Tools**. Then, click **HCL UrbanCode Deploy Agent Relay** and download and extract the file.
    -   To find the installer on the server with the command line, go to the following location and copy the file to the target system: installation\_folder/opt/tomcat/webapps/ROOT/tools/agent-relay.zip
2.   Expand the compressed installation file. 
3.   Open the example.agentrelay.install.properties file for editing, or copy the example.agentrelay.install.properties file to a new properties file. 
4.   Customize the installation by specifying the properties in the following table. If you do not specify a property, the default value is used. These properties are copied to the agentrelay.properties file of the completed installation.

    |Property|Default value|Description|
    |--------|-------------|-----------|
    |agentrelay.activemq.queue.memory|64mb|The memory limit for queues in Apache ActiveMQ. To prevent a single queue from using too much memory, this amount of memory should be less than one-fifth of the system memory limit in server.activemq.system.memory. Specify an integer value followed by `mb` for megabytes or `gb` for gigabytes.|
    |agentrelay.activemq.system.memory|512mb|The total amount of memory that Apache ActiveMQ can use on the system. This amount of memory should always be much less than the maximum amount of memory that is allotted to the server. On Linux and Unix systems, the maximum server memory is set in the set\_env file, in the `JAVA_OPTS` parameter, in the `-Xmx` parameter. Specify an integer value followed by `mb` for megabytes or `gb` for gigabytes.|
    |agentrelay.activemq.topic.memory|64mb|The memory limit for topics in Apache ActiveMQ. To prevent a single topic from using too much memory, this amount of memory should be less than one-fifth of the system memory limit in server.activemq.system.memory. Specify an integer value followed by `mb` for megabytes or `gb` for gigabytes.|
    |agentrelay.home|`/opt/ibm/agentrelay` on Linux or `C:\\Program Files\\IBM\\agentrelay` on Windows™|The installation folder for the relay. On Windows, escape each backslash with an additional backslash, as in the following example:    ```
agentrelay.home=C:\\Program Files\\IBM\\agentrelay
    ```

|
    |agentrelay.jms\_proxy.name|`ibm-ucd-relay`|The name of the relay. Each relay must have a unique name.|
    |agentrelay.http\_proxy.host|`0.0.0.0`|The IP address or host name on which the relay listens for HTTP requests from agents. In most cases, the agent relay listens on all IP addresses that are available to the computer; in this case, specify `0.0.0.0`.|
    |agentrelay.http\_proxy.port|`20080`|The port on which the agent relay listens for HTTP requests coming from agents. **Note:** In addition, the relay automatically listens for CodeStation requests on port `HTTP_proxy + 1` on the system where the agent relay is located. If you use the default port for HTTP requests, the relay uses 20081 for CodeStation requests and artifact transfers. If the CodeStation request port is blocked, agents cannot download artifacts.

|
    |agentrelay.jms\_proxy.relay\_host|`0.0.0.0`|The IP address or host name on which the relay listens for HTTP requests from servers. In most cases, the agent relay listens on all IP addresses that are available to the computer; in this case, specify `0.0.0.0`.|
    |agentrelay.jms\_proxy.relay\_port|`7916`|The port that the agent relay uses for JMS-based communications with remote agents.|
    |agentrelay.jms\_proxy.servers|None.|The host name or IP address and JMS port of the server that the relay connects to, as in the following example: `myserver.example.com:7918`

To connect to multiple servers for failover, separate addresses with commas, as in the following example: `newyork-server.example.com:7918, losangeles-server.example.com:7918`

For more information, see [Configuring agent relays for failover](configure_relay_failover.md).|
    |agentrelay.user|`agentrelay`|The user with which to run the agent relay. This property is not used on Windows systems.|
    |agentrelay.group|`agentrelay`|The group with which to run the agent relay. This property is not used on Windows systems.|
    |agentrelay.jms\_proxy.mutualAuth|`false`|Whether to use mutual authentication.|
    |verify.server.identity|`false`|Whether the agent relay attempts to verify the server certificate. If set to `true`, you must import the server certificate to the JRE keystore on the agent relay.|
    |agentrelay.codestation.server\_url|None.|The full URL of the central server to connect to, such as ``https://myserver.example.com:8443`.`|
    |agentrelay.codestation.server\_password|None.|An authentication token from the server.|
    |agentrelay.codestation.enable\_replication|`false`|Specify `true` to enable artifact caching on the relay.|
    |agentrelay.codestation.max\_cache\_size|None.|The size to which to limit the artifact cache, such as `500M` for 500 MB or `5G` for 5 GB. To not put a limit on the cache, specify `none`.**Note:** By default, each hour, the agent relay checks the size of the artifact cache. If the cache is over the limit, the agent relay removes files based on which files have not been used in the longest time. Therefore, the total disk space used by the cache can exceed the cache limit. You must ensure that the agent relay has enough space to store all of the cached artifacts.

|
    |agentrelay.codestation.geotags|None.|If you choose to cache files on the relay, you can specify one or more component version statuses here, separated by semicolons. The agent relay automatically caches component versions with any of these statuses so that those versions are ready when they are needed for a deployment. A status can contain a space except in the first or last position. A status can contain commas. The special `*` status replicates all artifacts, but use this status with caution, because it can make the agent relay store a large amount of data. If no value is specified, no component versions are cached automatically.**Note:** If you cache files on the relay, do not put the CodeStation cache on an NFS file system.

|
    |agentrelay.install.service|`false`|Specify `true` to install as a Windows service.This property is used only on Windows.|
    |agentrelay.install.service.name|`agentrelay`|The name of the service. This property is used only on Windows.|
    |agentrelay.install.service.login|`.\\localsystem`|The user to run the service. This property is used only on Windows.|
    |agentrelay.install.service.password|`nopass`|The password for the user that runs the service. This property is used only on Windows.|
    |agentrelay.install.service.autostart|`false`|Specify `true` to start the service automatically. This property is used only on Windows.|
    |java.home|None.|To use a JRE other than the JRE in the JAVA\_HOME environment variable, specify the location of that JRE here.|
    |agentrelay.keystore|`conf/jms-relay/agentrelay.keystore`|The location of the keystore for JMS communication.|
    |agentrelay.keystore.password|`changeit`|The keystore password for the agentrelay.keystore file.|
    |agentrelay.cert.alias|`agentrelay`|The certificate alias for the agentrelay.keystore file.|
    |agentrelay.cert.password|`changeit`|The password for the agentrelay.keystore certificate.|
    |codestation.keystore|`conf/codestation.keystore`|The location of the keystore for HTTPS communication.|
    |codestation.keystore.password|`changeit`|The keystore password for the codestation.keystore file.|
    |codestation.cert.alias|`agentrelay`|The certificate alias for the codestation.keystore file.|
    |codestation.cert.password|`changeit`|The password for the codestation.keystore certificate.|

5.   Save the file. 
6.   Run the installation file with the install-silent.cmd command on Windows or the ./install-silent.sh command on Linux. Provide the properties file as a command-line argument. For example, on Windows, if the properties file is named installrelay.properties, type the following command:

    ```
    install-silent.cmd installrelay.properties
    ```

    On Linux, if the properties file is named installrelay.properties, type the following command:

    ```
    ./install-silent.sh installrelay.properties
    ```

    To install a FIPS-compliant agent relay, add the `-fips` parameter, as in the following example:

    ```
    ./install-silent.sh installrelay.properties -fips
    ```

7.   If the relay is on Linux or UNIX and will connect to 400 or more agents, increase the process and file limit for the server: 
    1.   Add the following lines to the file that sets process and file limits. For example, for Red Hat Enterprise Linux, version 7, use the /etc/security/limits.conf file. For AIX, use the /etc/security/limits.d/90-nproc.conf file. 

        ```
        relayUser             soft    nofile          60000
        relayUser             hard    nofile          60000
        relayUser             soft    nproc           65535
        relayUser             hard    nproc           65535
        ```

        Use the name of the operating system user that is running the agent relay for `relayUser`. By default, the agent relay installation program creates a user that is named `agentrelay`.

    2.   Restart the computer that hosts the agent relay. 
8.   To start the agent relay, go to the installation folder for the relay and run the following command: 

    ```
    bin/agentrelay start
    ```


Any messages that are created during the installation are stored in the file agentrelay-install.log.

If you must modify the relay, you can edit these properties in the `agentrelay.properties` file in the relay\_installation\\conf directory.

Now you can install agents and connect them to the relay. See [Installing agents](agent_install_ov.md).

To monitor the status of the relay and the agents that are connected to it, click **Resources** \> **Agent Relays**. This tab shows the number of active and offline agents that are connected to each relay, as shown in the following figure:

![Information about agent relays, including the number and state of connected agents](../images/agentRelayInstall_a.gif)

For more information about an agent relay, in the **Name** column, click the relay.

**Parent topic:** [Installing agent relays](../../com.udeploy.install.doc/topics/agentRelayInstall.md)

