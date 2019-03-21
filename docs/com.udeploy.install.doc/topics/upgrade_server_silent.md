# Upgrading the server in silent mode

Use silent mode to upgrade without command-line prompts. To upgrade the server, stop the server, edit the properties file, and run the new installation program. These instructions apply to upgrades from versions 6.0 and later.

Depending on the version of UrbanCode Deploy you are upgrading, be sure to address these build-specific considerations.

|Affected Build|Consideration|
|--------------|-------------|
|6.1 and later|If the server is using an IBM® JRE, upgrade the JRE to a version that is shipped with version 6.2 or later.|
|6.1 - 6.2.3.0|UrbanCode Deploy servers and relays must be upgraded at the same time. Agents that connect through relays may not connect successfully until both server and relay are upgraded.|
|6.2.2 and later|Urban Code Deploy server and agent relays require a Java™ Runtime Environment \(JRE\) or Java Development Kit \(JDK\) version 8.After upgrading, these changes apply to the agent relays.

-   Users might notice that some agent relays are no longer listed in the user interface even though they were able to view relays before the upgrade. The new version includes updated security controls. The agent relays are still available to the users. However, System Team administrators can assign agent relays to teams and set the **View Agent Relays** permission for roles so that appropriate users can see the agent relays in the user interface.
-   Users can install and use agent relays. However, the relays are not listed in the user interface for the user until a System Team administrator assigns the agent relay to teams and sets the **View Agent Relays** permission.

|
|6.1 - 6.2.1.1|Ensure that all secure property values are obscured, the values of all properties in the history for existing deployments are obscured. In the deployment history for deployments that you run after you upgrade, only secure properties are obscured in the logs.|
|6.1 - 6.2.1.1|New security features erase old component version import logs to hide secure information. If you want to keep the logs, in the installed.properties file, set the property com.urbancode.ds.cleanup.sourceConfig.fullCleanupSkip to True.|

This task applies to upgrades of versions 6.1 or later. Contact UrbanCode Deploy support for all other versions.

**Note:** During the upgrade of UrbanCode Deploy, the contents of the appdata/patches directory \(including all .jar files\) will be appended with .off, preventing the existing test fixes from being loaded once the UCD Server is started post-installation. All UI test fixes applied to the Tomcat directory will be wiped by the upgrade and will not be recoverable.

If a text fix received for a reported defect is not fixed in the upgraded version, you may need to open a Support Case to request a new build.

**Note:** Setting com.urbancode.ds.cleanup.sourceConfig.fullCleanupSkip to True is only effective upon upgrade. After upgrading, component version import logs are automatically cleaned up after 24 hours by default. Refer to [Component Versions.](https://www.ibm.com/support/knowledgecenter/SS4GSP_7.0.0/com.udeploy.doc/topics/comp_version.html)

1.   If you have added custom keystores, certificates, or any other files to the server\_install/opt/tomcat directory, back up those files before you upgrade. If you do not back up files that you have added to the server\_install/opt/tomcat directory, those files are removed when the upgrade process runs. 
2.   Download and extract the installation files for HCL® UrbanCode™ Deploy. These files are available for download from the IBM Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
3.   Ensure that no application and generic processes are running. Open the **Dashboard** and confirm that no processes are running. If processes are running, you can wait for them to complete or by clicking **Cancel** in the same row as each process, cancel them. In versions 6.2.5.1 and later, you can use the Message of the Day feature \(**Settings \> System \> General Settings** \> ****\) to notify users of the planned upgrade, and request that they do not start new processes.
4.   Stop the server. 
5.   Ensure that the server is stopped: 

    1.   Check to ensure that there is no file server.pid in the server\_install/var folder. 
    2.   Check for running system processes. For example, on Linux™, you can use the netstat or ps commands. For example, if the server is running on port 8443, use the command `netstat -nap | grep 8443`. You can also run `ps -ef | grep server` and look for the server system process in the results.
    3.   If any server processes are still running, stop them. 
    If a server process is still running, when you install the new version, you see an error that says "A previously installed version of HCL UrbanCode Deploy is running. Please shutdown the running HCL UrbanCode Deploy and start the installation again."

6.   Back up the database. 
7.   If you are upgrading from a version prior to version 6.2.2 to version 6.2.2 or later, upgrade the version of Java on the server to version 8 or later. See [Changing or updating the JRE of servers](../../com.udeploy.doc/topics/jre_change.md).
8.   In the installation files, open the install.properties file in a text editor, and add the following line of code to the file: 

    ```
    nonInteractive=true
    ```

9.  Ensure that the install.server.dir property is set to the directory where HCL UrbanCode Deploy is installed.
10. From the command line, run the server installer program. 

    -   On Windows™, run the install-server.bat file.
    -   On Linux, run ./install-server.sh.
    -   To install a FIPS-compliant server, add the switch `-fips` to the command, such as `install-server.sh -fips`.

        **Note:** If you install a FIPS-compliant server, cloud provisioning is not available. Your JVM connects to only FIPS 140-2 certified IBM providers.

    Depending on your system settings, you might need to run this file as an administrator.

11. Start the server, and verify that the server is upgraded. 
12.  Ensure that licensing is set up for the server. See [License management](../../com.udeploy.doc/topics/licenseManage.md).
13. If you are upgrading the server from version 6.0.1.1 or earlier to a version later than version 6.0.1.1, upgrade the encryption key strength.See [Upgrading encryption key strength](upgrade_key_strength.md).
14.  Upgrade the agents. See [Upgrading agents](upgradeAgents.md). If you are upgrading from a version before 6.1.0.4 to version 6.1.0.4 or later, you must upgrade agents that use Java plug-ins, including most source configuration plug-ins. If you do not upgrade the agents, they will throw an IllegalCharsetNameException exception that refers to the variable DS\_SYSTEM\_ENCODING.

If you are upgrading from version 6.2.3.0 to 6.2.3.1 or later, upgrade all agent relays to the current version. Agents that connect through relays may not connect successfully until both server and relay are upgraded.

**Parent topic:** [Upgrading the server](../../com.udeploy.install.doc/topics/upgradeInstall.md)

