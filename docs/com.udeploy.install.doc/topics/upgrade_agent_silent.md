# Upgrading agents in silent mode

You can upgrade agents by specifying the installation properties in a text file.

In most cases, upgrade the server before you upgrade the agents. If you are upgrading from a version before 4.8.5, you must upgrade the server to 4.8.5 or 5.0 before you upgrade the server to 6.0 or later. To ensure compatibility between your agents and the server, upgrade the agents after you upgrade the server to 4.8.5 or 5.0.

1.   From the new version of the server, download the agent installer for the new agent version. 
    -   To download the installer, log in to the server and click the **Help** icon ![](../images/help_button.gif) at the upper right of any page on the server, and click **Tools**. Then, click **HCL® UrbanCode™ Deploy Agent**, and download and extract the file.
    -   To find the installer on the server with the command line, go to the following location, and copy the file to the target computer: installation\_folder/opt/tomcat/webapps/ROOT/tools/ucd-agent.zip

        **Note:** If you are installing the agent on IBM® z/OS® by extracting files to the UNIX™ file system, you must convert the character encoding for several text-type files in the installation package to IBM-1047 encoding. If you are installing the agent by using SMP/E, you do not have to convert the character encoding. Move the installation files to the z/OS computer, and then extract the files. If the unzip program is not installed on the z/OS computer, use the jar command to extract the files. For instance, type the following text on the command line:

        ```
        JAVA_HOME/bin/jar xvf ucd-agent.zip
        ```

        Run the convertFilesForZos.sh script to convert the character encoding of the relevant files to IBM-1047 encoding. After you convert the files, continue with installation.

        If you used the jar command to extract files, add execute permission to convertFilesForZos.sh script first.

        **Note:** If you are installing the agent on IBM i, you must run the commands through the IBM Portable Application Solutions Environment for i \(PASE for i\) shell. Move the installation files to the i system, and then extract the files. Run the ibmi-compatability-fix.sh script to update the installer to use the PASE for i shell. After you run the script, continue with installation.

2.   Transfer the new agent installation package to the system that hosts the agent and extract the package. 
3.   Create or update the agent installation properties file. For more information see [Installing agents in silent mode](agent_install_silent.md).
4.   Stop the agent. 
5.   Run the installation file with the install-agent-from-file.bat command on Windows™ or the ./install-agent-from-file.sh command on Linux™. Provide the properties file as a command-line argument. On Windows, if the properties file is named install.properties, type the following command:

    ```
    install-agent-from-file install.properties
    ```

6.   Restart the agent. 

On the server, click **Resources** \> **Agents** and verify that the agent shows the new version.

**Parent topic:** [Upgrading agents](../../com.udeploy.install.doc/topics/upgradeAgents.md)

