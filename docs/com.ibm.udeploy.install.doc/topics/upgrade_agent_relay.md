# Upgrading agent relays

When you upgrade the server, be sure to always upgrade agents and agent relays.

Upgrade the server.

The CodeStation request port is configured automatically on the system where the agent relay is located. The CodeStation port number is one greater than the number assigned for HTTP communication. By default, the HTTP port is 20080. If you use the default value for the HTTP port, the CodeStation request port would be numbered 20081.

If the CodeStation request port is blocked, agents cannot download artifacts. If you upgrade from versions before 6.1, ensure that the port is not blocked by the firewall or other processes on the agent relay system.

**Important:** Beginning in version 6.2.2, the HCL® UrbanCode™ Deploy server and agent relays require a Java™ Runtime Environment \(JRE\) or Java Development Kit \(JDK\) version 8.

**Important:** After you upgrade to IBM UrbanCode Deploy version 6.2.2 or later, note these changes to agent relays:

-   Users might notice that some agent relays are no longer listed in the user interface even though they were able to view relays before the upgrade. The new version includes updated security controls. The agent relays are still available to the users. However, System Team administrators can assign agent relays to teams and set the **View Agent Relays** permission for roles so that appropriate users can see the agent relays in the user interface.
-   Users can install and use agent relays. However, the relays are not listed in the user interface for the user until a System Team administrator assigns the agent relay to teams and sets the **View Agent Relays** permission.

1.   Download and extract the agent relay installer to the computer on which you want to install the agent relay: 
    -   To download the installer from the server, click **Help** ![](../images/help_button.gif), located in the upper-right corner of the page, and then click **Tools**. Then, click **HCL UrbanCode Deploy Agent Relay** and download and extract the file.
    -   To find the installer on the server with the command line, go to the following location and copy the file to the target system: installation\_folder/opt/tomcat/webapps/ROOT/tools/agent-relay.zip
2.   Stop the agent relay. 
3.   If the system that hosts the agent relay is using a version of Java prior to version 8, upgrade to a JRE of version 8 or later. See [Updating the JRE location for agent relays](../../com.ibm.udeploy.doc/topics/update_JRE_agent_relays.md).
4.   From the agent relay installer folder, run install.sh \(Linux\) or install.cmd \(Windows\). 
    -   **Enter the home directory for the JRE/JDK that the relay should use.**

        Specify the directory in which Java™ is installed. Press Y to accept the location set in the JAVA\_HOME parameter.

    -   ****Enter the directory to install the agent relay into.****

        Enter the current directory that the relay is installed in. The default value is `/opt/ibm/agentrelay` on Linux™ and `C:\Program Files\IBM\agentrelay` on Windows™.

    -   ****The specified directory appears to contain an existing installation. Do you want to upgrade it?****

        Enter `Y`.

    -   ****Enable the agent relay to verify the server HTTPS certificate? If enabled, you must import the server certificate to the JRE keystore on the agent relay.****

        Specify whether to verify the server HTTPS certificate.

5.   To start the agent relay, go to the installation folder for the relay and run the following command: 

    ```
    bin/agentrelay start
    ```


**Parent topic:** [Upgrading and migrating](../../com.ibm.udeploy.doc/topics/c_node_upgrading.md)

