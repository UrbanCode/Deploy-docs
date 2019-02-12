# Installing the server in evaluation mode

To explore the features of HCL® UrbanCode™ Deploy, install the server in evaluation mode.

-   The following instructions are for exploring the features of HCL UrbanCode Deploy in evaluation mode. Do not follow these instructions if you are installing a production server. For instructions on installing a production server, see [Installing the server in interactive mode](server_install_interactive.md#).
-   You can evaluate the product for a trial period of up to 60 days.
-   Ensure that a supported version of a Java™ Runtime Environment \(JRE\) or Java Development Kit \(JDK\) is installed on the computer on which you are installing HCL UrbanCode Deploy. For more information, see [System Requirements for IBM® UrbanCode Deploy](http://www-01.ibm.com/support/docview.wss?uid=swg27038801).

    **Important:** 

    For best results, download and use the latest available version of the IBM Java Runtime Environment \(JRE\) for the HCL UrbanCode Deploy server and agent relays. An IBM JRE is available as a separate download. See the [IBM developer kits](https://www.ibm.com/developerworks/java/jdk/) page to get the latest version. Install the IBM JRE according to the documentation on the page. Be sure to set the JAVA\_HOME system variable to the location of the IBM JRE. If you are updating or changing the JRE to the latest version, see [Changing or updating the JRE of servers](../../com.udeploy.doc/topics/jre_change.md#) and [Updating the JRE location for agent relays](../../com.udeploy.doc/topics/update_JRE_agent_relays.md#) for instructions. For documentation on the IBM JRE, see [IBM SDK, Java Technology Edition](https://www.ibm.com/support/knowledgecenter/SSYKE2/welcome_javasdk_family.html).

    Using JREs or Java development kits other than those provided by IBM might cause unexpected results.

-   Set the JAVA\_HOME system variable to the location of the JRE or JDK that you are using.
-   Ensure that the IBM JRE or JDK is a supported version and supported service refresh \(SR\) level. For more information, see [System Requirements for IBM UrbanCode Deploy](http://www-01.ibm.com/support/docview.wss?uid=swg27038801).
-   If you are installing on AIX®, the unzip program is required.

**Note:** HCL UrbanCode Deploy is also available as a hosted service. In this case, IBM hosts the server for you. For more information, see the [IBM Marketplace](https://www.ibm.com/us-en/marketplace/application-release-automation).

The properties that are set during installation are recorded in the file server\_install/conf/server/installed.properties on the server.

1.   Download and extract the installation files for HCL UrbanCode Deploy. These files are available for download from the IBM Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
2.   From the command line, run the server installer program. 

    -   On Windows™, run the install-server.bat file.
    -   On Linux™, run ./install-server.sh.
    Depending on your system settings, you might need to run this file as an administrator.

3.  Read the license agreements for the software package. Press Enter to show one page at a time, or press F and then press Enter to show the entire license at once.
4.  If you agree to the terms of all of the license agreements, press Y and then press Enter.
5.   Specify the following information as the installation program prompts you. Accept the default values \(displayed within brackets\) by pressing Enter. If two options are given, such as `[Y/n]`, the capitalized option is the default value.
    -   ****Enter the directory where the HCL® UrbanCode™ Deploy server should be installed.****

        Specify the installation directory for the server. The default server installation directory is /opt/ucd/server on Linux™ and C:\\Program Files\\ucd\\server on Windows™.

        **Note:** Do not use any shell expansions or abbreviations, such as the tilde character \(`~`\).

    -   ****The specified directory does not exist. Do you want to create it?****

        Press Y to create the installation directory.

    -   ****Please enter the home directory of the JRE/JDK used to run the server.****

        Specify the location of the JRE or JDK for the server.

    -   ****Will this server be used as a node in a high availability cluster?****

        Press N. Do not add servers to high-availability clusters in evaluation mode.

    -   ****Where should the server store application data such as logs, plugins, and keystores?****

        Type the name of the application data directory. The directory must be accessible to the server, and you must have the appropriate permissions. The default directory is /server\_installation\_directory/appdata.

        Depending on whether the shared folder exists or is empty, you are prompted with one of the following options:

        -   If the folder does not exist, you are prompted with the following option: **The specified directory for application data doesn't exist. Do you want to create it?**. Press Y to create the application data directory. If you select `N`, the installation process ends.
        -   If the shared folder exists and is not empty, you are prompted with the following option: **The specified directory for shared resources already exists and is non-empty. Do you want to use the existing data?**. Press Y to use the data. If you select `N`, the installation process ends; in this case, you must manually clear the application data folder to use it.
        -   If the shared folder exists but is empty, the folder is used and you are not prompted to use the existing data.
        **Note:** Do not use any shell expansions or abbreviations, such as the tilde character \(`~`\).

    -   ****What host name will users access the web UI at?****

        Specify the host name of the computer that hosts the server.

        The server listens on all IP addresses that are available to it, not just this host name or IP address.

    -   ****Do you want the Web UI to always use secure connections using SSL?****

        Press N. Do not use secure connections in evaluation mode.

    -   ****Enter the port on which the Web UI should redirect unsecured HTTP requests.****

        Specify the HTTP port for the server. The default value is `8080`.If you are installing HCL® UrbanCode™ Deploy, UrbanCode Velocity, and IBM® UrbanCode™ Release, be sure to use a different port for each product. If you are installing multiple instances of HCL® UrbanCode™ Deploy on the same computer, be sure to use a different port for each instance.

    -   ****Enter the initial password for the admin user.****

        Specify the starting password for the administrator account on the server. The administrator user name is `admin`. Then, type the password again to verify it.

    -   ****Enter the port to use for agent communication.****

        Specify the port that agents use to contact the server. The default value is `7918`.

    -   ****Do you want the Server and Agent communication to require mutual authentication? This requires a manual key exchange between the server and each agent. See the documentation for more details.****

        Do not use mutual authentication in evaluation mode.

    -   ****Enter the RCL server path\(s\).****

        Do not specify connection information for a license server. You can evaluate the product for a trial period of up to 60 days without a license.

    -   ****Create database schema****

        Press Y to create new schema definitions in the database.

    -   ****Enter the database type to use.****

        Select `derby`.

        **Warning:** Derby is for evaluation purposes only; do not use Derby for a production server.

    -   ****Enter the database username.****

        Specify the user name for the database.

    -   ****Enter the database password.****

        Specify the password for the database.

6.   If you are installing on Windows, the installation program prompts you with the following questions after a pause: 
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


The installation program installs the server.

To start the server, see [Starting and stopping the server](run_server.md).

When you run the server for the first time, you might see an error message that says that no agent or tag is configured to import new component versions. To import component versions, including built artifacts, you must use an agent, and the server requires that you specify a default agent for this purpose. You can override this default setting when you create a component. Follow these steps to specify a default agent or agent tag:

-   To specify a default agent, click **System** \> **System Settings** and under **General Settings**, clear the **Use Agent Tag For Integration** check box. Then, select an agent in the **Agent for Version Imports** list. Then, at the bottom of the page, click **Save**.
-   To specify a default agent tag, click **Settings** \> **System Settings** and under **General Settings**, clear the **Use Agent Tag For Integration** check box. Then, select an agent tag in the **Agent Tag for version imports** list. Then, at the bottom of the page, click **Save**. If no tags are listed, add a tag to one or more agents on the server.

On Windows, if you see "Out of memory" errors, increase the amount of memory that is available to the HCL UrbanCode Deploy service. To increase the memory for the server on Windows for a non-service installation, follow these steps:

1.  Stop the server.
2.  In the bin/set\_env.cmd file, increase the memory in the `JAVA_OPTS` parameter.
3.  Restart the server.

For servers that are running as a service on Windows, see the following technote: [http://www-01.ibm.com/support/docview.wss?uid=swg21698228](http://www-01.ibm.com/support/docview.wss?uid=swg21698228).

You might see the following error in the results of the installation program:

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

