# Installing agents in silent mode

In silent mode, you specify the installation properties in a text file and then run the installation without command-line prompts.

-   For production environments, create a user account that is dedicated to running the agent on the computer where the agent is installed.
-   Ensure that each computer where you are installing an agent has a supported version of the Java™ Runtime Environment \(JRE\) or Java developer kit. For more information, see [System Requirements for IBM® UrbanCode™ Deploy](http://www-01.ibm.com/support/docview.wss?uid=swg27038801).

-   If the target computer has an IBM JRE or Java developer kit, update to a supported version of the IBM JRE or Java developer kit.

-   Set the JAVA\_HOME system variable to the location of the JRE or JDK that you are using.
-   Make sure that your networks and firewalls allow communication on the required ports. See [Firewall and communication configuration](agent_firewalls.md).
-   Ensure that there is no limit on the maximum memory size and virtual memory size. For example, on most Linux™ systems, you can run the `ulimit -m` and `ulimit -v` commands and ensure that both return the value `unlimited`. To find out how to remove the limit on the maximum memory size and virtual memory size, see the documentation for the operating system.

You specify the installation properties in a properties file. The example.agent.install.properties file is provided as an example of a properties file. The example.agent.install.properties file is in the ucd-agent.zip archive.

1.   Copy the following file from the HCL® UrbanCode Deploy server to the target system: installation\_folder/opt/tomcat/webapps/ROOT/tools/ucd-agent.zip. 
2.   Extract the ucd-agent.zip archive file. 

    **Note:** If you are installing the agent on IBM z/OS® by extracting files to the UNIX file system, you must convert the character encoding for several text-type files in the installation package to IBM-1047 encoding. If you are installing the agent by using SMP/E, you do not have to convert the character encoding. Move the installation files to the z/OS computer, and then extract the files. If the unzip program is not installed on the z/OS computer, use the jar command to extract the files. For instance, type the following text on the command line:

    ```
    JAVA_HOME/bin/jar xvf ucd-agent.zip
    ```

    Run the convertFilesForZos.sh script to convert the character encoding of the relevant files to IBM-1047 encoding. After you convert the files, continue with installation.

    If you used the jar command to extract files, add execute permission to convertFilesForZos.sh script first.

    **Note:** If you are installing the agent on IBM i, you must run the commands through the IBM Portable Application Solutions Environment for i \(PASE for i\) shell. Move the installation files to the i system, and then extract the files. Run the ibmi-compatability-fix.sh script to update the installer to use the PASE for i shell. After you run the script, continue with installation.

3.  Open the example.agent.install.properties file for editing, or copy the example.agent.install.properties file to a new properties file.
4.  Customize the installation by editing the properties file. If you do not specify a property, the default value is used. Some properties in the example file are commented out by default. For a list of these properties, see [Agent installation properties](agent_properties.md).
5.  Save the file.
6.   Run the installation file with the install-agent-from-file.bat command on Windows™ or the ./install-agent-from-file.sh command on Linux. Provide the properties file as a command-line argument. On Windows, if the properties file is named install.properties, type the following command:

    ```
    install-agent-from-file install.properties
    ```


The installation program installs the agent.

Start the agent. See [Starting agents](run_agent.md).

**Parent topic:** [Installing agents](../../com.udeploy.install.doc/topics/agent_install_ov.md)

