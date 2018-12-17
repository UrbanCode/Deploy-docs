# Installing agents from the command line

Installing an agent from the command line involves running a batch file or shell script and specifying information about how the agent connects to the server or agent relay.

-   For production environments, create a user account that is dedicated to running the agent on the server where the agent is installed.

    **Note:** This user account must have access to all working directories that are used in the processes that this agent runs. If this user does not have access to the working directory specified in a process step, that step fails.

    If you are installing the agent on z/OS®, review [Security requirements on the IBM z/OS computers](../../com.ibm.udeploy.admin.doc/topics/security_zos.md#).

-   Make sure that your networks and firewalls allow communication on the required ports. See [Firewall and communication configuration](agent_firewalls.md).
-   Ensure that each computer where you are installing an agent has a supported version of the Java™ Runtime Environment \(JRE\) or Java developer kit. For more information, see [System Requirements for IBM UrbanCode Deploy](http://www-01.ibm.com/support/docview.wss?uid=swg27038801).

-   If the target computer has an IBM JRE or Java developer kit, update to a supported version of the IBM JRE or Java developer kit.

-   Set the JAVA\_HOME system variable to the location of the JRE or JDK that you are using.
-   Ensure that there is no limit on the maximum memory size and virtual memory size. For example, on most Linux™ systems, you can run the `ulimit -m` and `ulimit -v` commands and ensure that both return the value `unlimited`. To find out how to remove the limit on the maximum memory size and virtual memory size, see the documentation for the operating system.

Agents can also be installed directly from the HCL UrbanCode Deploy web application, see [Installing agents remotely](../../com.ibm.udeploy.doc/topics/agent_installremote.md).

For simple evaluations, the administrative user can run the agent on the computer where the server is located. Because agent workloads can be resource-intensive, for production environments, do not install agents on the computer where the HCL UrbanCode Deploy server is located. If you plan to run deployments on several target servers, install a separate agent on each one. If, for example, your testing environment consists of three servers, install an agent on each one. Follow the same procedure for each environment the application uses.

Each agent requires the appropriate rights to communicate with the HCL UrbanCode Deploy server.

At a minimum, each agent must have these permissions:

-   Open a TCP connection. A JMS agent uses a TCP connection to communicate with the server's JMS port, and a Web agent uses one for its WebSocket connection.
-   Open a HTTP\(S\) connection. The agent must be able to connect to the HCL UrbanCode Deploy user interface to download artifacts from the CodeStation repository.
-   Access the file system. Many agents need read/write permissions to items on the file system.

If the agent communicates with HCL UrbanCode Deploy by using an agent relay, you can install the agent from the command line.

1.  To install an agent from the command line:
2.   Download and extract the agent installer to the computer to install the agent on. Complete one of the following steps: 
    -   To download the installer, log in to the server and click the **Help** icon ![](../images/help_button.gif) at the upper right of any page on the server, and click **Tools**. Then, click **HCL UrbanCode Deploy Agent**, and download and extract the file.
    -   To find the installer on the server with the command line, go to the following location, and copy the file to the target computer: installation\_folder/opt/tomcat/webapps/ROOT/tools/ucd-agent.zip

        **Note:** If you are installing the agent on IBM z/OS by extracting files to the UNIX™ file system, you must convert the character encoding for several text-type files in the installation package to IBM-1047 encoding. If you are installing the agent by using SMP/E, you do not have to convert the character encoding. Move the installation files to the z/OS computer, and then extract the files. If the unzip program is not installed on the z/OS computer, use the jar command to extract the files. For instance, type the following text on the command line:

        ```
        JAVA_HOME/bin/jar xvf ucd-agent.zip
        ```

        Run the convertFilesForZos.sh script to convert the character encoding of the relevant files to IBM-1047 encoding. After you convert the files, continue with installation.

        If you used the jar command to extract files, add execute permission to convertFilesForZos.sh script first.

        **Note:** If you are installing the agent on IBM i, you must run the commands through the IBM Portable Application Solutions Environment for i \(PASE for i\) shell. Move the installation files to the i system, and then extract the files. Run the ibmi-compatability-fix.sh script to update the installer to use the PASE for i shell. After you run the script, continue with installation.

3.   After you download and expand the installation package, open the installer directory. 
4.   From this directory, run the install-agent.bat command \(Windows™\) or install-agent.sh \(UNIX, Linux, Mac OS, or IBM z/OS\). 

    **Note:** If you install the agent as a Windows service, the user account must have the following privileges:

    -   SE\_INCREASE\_QUOTA\_NAME "Adjust memory quotas for a process"
    -   SE\_ASSIGNPRIMARYTOKEN\_NAME "Replace a process level token"
    -   SE\_INTERACTIVE\_LOGON\_NAME "Logon locally"
    The HCL UrbanCode Deploy agent installer is displayed and prompts you to provide the following information. You can accept the default values \(displayed in brackets\) by pressing Enter. If two options are given, such as `Y/n`, the uppercase option is the default value. Depending on the options that you select, different prompts display.

    1.   For all agents, provide values for the following prompts: 
        -   ****Enter the directory where agent should be installed.****

            For example, enter `C:\Program Files\UCDeploy-agent` \(Windows™\) or `/opt/IBM/ucd/agent` \(UNIX™\). If the directory does not exist, enter Y to instruct the Installer to create it for you. If you enter an existing directory, the program gives you the option to upgrade the agent. For information about upgrading, see [Upgrading agents](upgradeAgents.md).

            **Note:** Do not use any shell expansions or abbreviations, such as the tilde character \(`~`\).

            The agent directory length must not exceed 38 characters on IBM® z/OS®.

        -   ****Please enter the home directory of the JRE/JDK used to run this agent.****

            If Java™ is already installed, HCL® UrbanCode™ Deploy suggests the Java™ location as the default value. To accept the default value, press Enter. Otherwise, override the default value, and enter the correct path.

        -   ****Does this agent use web or JMS communication?****

            The default value is `web`. Introduced with HCL® UrbanCode™ Deploy version 7.0.0, Web-type agents use WebSockets for communication instead of JMS technology. Web-type agents are more scalable than the older agent type, now called JMS agents. You can use both types of agents in a single installation.

        -   ****Will the agent connect to an agent relay instead of directly to the server?****

            The default value is `N`. To configure a connection to an agent relay instead of a connection to the server, specify Y. If you connect directly to a server, complete step [3.b](#server_direct). If you connect to an agent relay, complete step [3.c](#agent_relay).

    2.   If the agent connects directly to the server, provide values for the following prompts: 
        -   ** **Enter the full URI for the server this agent will connect to.****

            If you are installing a Web-type agent, specify the secure WebSocket connection URI. The format is `wss://hostname:port`. The default value is `wss://localhost:7919`.

        -   ****Enter the hostname or address of the server the agent will connect to.****

            If you are connecting the agent to a high-availability cluster of servers, specify one server in the cluster here and add the other servers as failover connections. Do not specify the host name of the load balancer. The default value is `localhost`.

        -   ****Enter the agent communication port for the server****

            If you are installing a JMS agent, this is the port the JMS agent uses to communicate with the server. The default value is `7918`.

        -   ****Do you want to configure another failover server connection?****

            The default value is `N`. If you are using a high-availability cluster of servers, specify a failover connection to each other server in the cluster.

            **Restriction:** The failover list must contain only servers or only agent relays. An agent can not have both servers and agent relays in its failover list.

            If you specify `Y`, you give information for one or more additional servers. When the agent starts, it contacts one of the specified servers at random. If that server fails, it switches to another server from the list. For more information, see [Configuring agents for failover](configure_agent_failover.md).

            To configure a failover server, type `y` and then press Enter.

            -   ****Enter the hostname or address of the server the agent will connect to.****

                The default value is `localhost`.

            -   ****Enter the agent communication port for the server.****

                The default value is `7918`.

            -   ****Do you want to configure another failover server connection?****

                The default value is `N`. To specify another failover server, press `Y`.

    3.   If the agent connects to an agent relay, provide values for the following prompts: 
        -   ****Enter the hostname or address of the agent relay the agent will connect to.****

            Enter the host name or IP address of the agent relay. Specify the value that you used when you installed the agent relay.

        -   ****Enter the agent communication port for the agent relay.****

            Enter the port that the agent uses for JMS-based communications with the agent relay. The default value is `7916`.

        -   ****Do you want to configure another failover relay connection?****

            The default value is `N`. If you specify `Y`, you give information for one or more additional relays. When the agent starts, it contacts one of the specified relays at random. If that relay fails, it switches to another relay from the list. For more information, see [Configuring agents for failover](configure_agent_failover.md).

            **Restriction:** The failover list must contain only servers or only agent relays. An agent can not have both servers and agent relays in its failover list.

            To configure a failover server, type `y` and then press Enter.

            -   ****Enter the hostname or address of the agent relay the agent will connect to.****

                You must provide the hostname or address of the agent relay.

            -   ****Enter the agent communication port for the agent relay.****

                The default value is `7916`.

            -   ****Do you want to configure another failover agent relay connection?****

                The default value is `N`. To specify another failover server, press `Y`.

        -   ****Enter the hostname or address of the HTTP proxy server for the agent relay.****

            The default value is the hostname or address of the agent relay that you provided.

        -   ****Enter the HTTP proxy port for the agent relay.****

            Enter the port that the agent uses for HTTP communications with the agent relay. The default value is `20080`.

        -   ****Do you want to disable HTTP Failover Handling?****

            The default value is `N`. You must disable HTTP failover handling if the relay is behind a firewall and accessed through a load balancer. To disable HTTP failover handling, press `Y`.

    4.   For JMS agents, provide values for the following prompts: 
        -   ****Enable mutual \(two-way\) authentication with SSL for server/agent JMS communication?****

            The default value is `N`.

            This setting must match the setting of the server. If you use mutual authentication, you must manually exchange a key between the server and each JMS agent or agent relay. For more information about this option, see [Configuring mutual authentication](ssl_mutual_auth.md).

            **Note:** Mutual authentication is not used with Web agents.

        -   ****Disable end-to-end encryption for server/agent JMS communication?****

            The default value is `N`.

            To enable end-to-end encryption, the agent installer must connect to the HCL® UrbanCode™ Deploy server via HTTPS to set up keys. For more information about this option, see [Ensuring end-to-end JMS encryption](ssl_addl_security_2.md).

        -   ****Enable the agent to verify the server HTTPS certificate?****

            The default value is `N`.

            If enabled, you must import the server certificate to the JRE keystore on the agent. For more information about this option, see [Enabling server identity verification](ssl_addl_security.md).

        -   ****Enter the full web URL for the central HCL® UrbanCode™ Deploy server.****

            Enter the URL with the protocol and port number, as shown in the following example: https://server.example.com:8443. This URL is required to enable end-to-end JMS encryption. The server must be running when you enter the URL. For information on starting the server, see [Starting and stopping the server](run_server.md).

        -   ****Enter the name for this agent.****

            Enter a unique name. The server uses this name to identify this agent. Names are limited to 256 characters and cannot be changed.

        -   ****Enter teams \(and types\) to add this agent to, separated by commas.****

            The default value is `None`.

            Agents can be added to teams the first time they connect to the server. The agent is assigned to the specific teams the first time that it connects to the server. Separate multiple teams by commas. Trailing spaces are ignored. Team names that do not exist are also ignored. To specify the agent's security type for a team, provide the team and security type in the following format: team:type.

        -   ****Do you want to install the Agent as Windows service?****

            This parameter applies only to Windows™. The default value is `N`. When installed as a service, HCL® UrbanCode™ Deploy captures only the value for the PATH variable. Values that are captured during installation are always used, even if you change them later. For recent versions of Windows™, you must run the command as Administrator.

        -   ****Enter the full web URL for the central HCL® UrbanCode™ Deploy server.****

            Enter the URL with the protocol and port number, as shown in the following example: https://server.example.com:8443. This URL is required to enable end-to-end JMS encryption. The server must be running when you enter the URL. For information on starting the server, see [Starting and stopping the server](run_server.md).

    5.   For Web and JMS agents, provide values for the following prompts: 
        -   ****Enter the name for this agent.****

            Enter a unique name. The server uses this name to identify this agent. Names are limited to 256 characters and cannot be changed.

        -   ****Enter teams \(and types\) to add this agent to, separated by commas.****

            The default value is `None`.

            Agents can be added to teams the first time they connect to the server. The agent is assigned to the specific teams the first time that it connects to the server. Separate multiple teams by commas. Trailing spaces are ignored. Team names that do not exist are also ignored. To specify the agent's security type for a team, provide the team and security type in the following format: team:type.

        -   ****Do you want to install the Agent as Windows service?****

            This parameter applies only to Windows™. The default value is `N`. When installed as a service, HCL® UrbanCode™ Deploy captures only the value for the PATH variable. Values that are captured during installation are always used, even if you change them later. For recent versions of Windows™, you must run the command as Administrator.

    6.   For IBM z/OS, provide values for the following prompts: 
        -   **Enter the high-level qualifier to install product data sets. \[Default: BUZ\]**

            Specify the high-level qualifier to install product data sets. If the agent is installed by using SMP/E, the high-level qualifier must be the same qualifier that was used in the SMP/E installation.

        -   **Enter the volume serial to install product data sets.**

            Specify the volume serial number to install product data sets. If the agent is installed by using SMP/E, the volume serial number must be the same as that was used in the SMP/E installation.

        -   **Enter the URL of the HCL® UrbanCode™ Deploy server. \[Default: https://hostname:8443/\]**

            Enter the URL with the protocol and port number. The default value is generated using the input hostname and the default port 8443.

        -   **Enter the authentication token for the UrbanCode Deploy server. You can modify the token later in installed.properties file. \[Default: empty\]**

            Specify an authentication token to be used to import z/OS® component versions. To create a token in HCL® UrbanCode™ Deploy, click **Settings** \> **Tokens** \> **Create Token**. The token is stored in the installed.properties file and can be updated when a new token must be used. The token is encrypted after the first time it is used.

        -   **Do you want to store versions in the UCD server CodeStation? If you choose No, versions will be stored in local directory. Y,n \[Default: Y\]**

            Storing versions in the local directory keeps the version artifacts in the same mainframe environment where the versions are taken from. Storing versions in CodeStation copies artifacts to the artifact repository, typically on a network storage drive or in a directory in the server installation location. For more information, see [Choosing a CodeStation and planning storage](codestation_choose_plan.md).

5.   When you install on IBM z/OS by using downloaded .zip file, submit a job to load the agent data sets. 

    Locate the job JCL at agent install dir/mvs/BUZEXPD. The JCL, except the job parameter, has already been customized based on your input. Edit and submit the job to load the agent data sets. For example, use the following command in OMVS to edit or submit the JCL:

    ```
    oedit agent install dir/mvs/BUZEXPD
    submit agent install dir/mvs/BUZEXPD
    ```


**Parent topic:** [Installing agents](../../com.ibm.udeploy.install.doc/topics/agent_install_ov.md)

