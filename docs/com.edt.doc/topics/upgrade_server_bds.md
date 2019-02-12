# Upgrading the blueprint design server

To upgrade the blueprint design server, stop the Tomcat server, install the new version, and restart the blueprint design server. When you upgrade the blueprint design server, you must also upgrade the engine.

Upgrade the HCL® UrbanCode™ Deploy server. See [Upgrading the server](upgradeInstall.md#).

1.   Stop the cloud discovery service. See [Stopping the blueprint designer, cloud discovery service, and engine](stop_patterns.md).
2.   Stop the Tomcat service: 
    -   On Linux™, run the following command:

        ```
        server\_installation\_directory/bin/server stop
        ```

        Use the location of the blueprint design server installation for `server\_installation\_directory`. The default installation directory is /opt/ibm-ucd-patterns. By default, the command looks like the following code:

        ```
        /opt/ibm-ucd-patterns/bin/server stop
        ```

    -   On Windows™, run the following command:

        ```
        C:\server\_installation\_directory\bin\stop_server
        ```

        Use the location of the blueprint design server installation for `server\_installation\_directory`. The default installation directory is C:\\Program Files\\ibm-ucd-patterns. By default, the command looks like the following code:

        ```
        "C:\Program Files\ibm-ucd-patterns\bin\stop_server"
        ```

3.   Delete the contents of the following folder, including any subfolders: server\_installation\_directory/opt/tomcat/webapps/landscaper 
4.   Delete the following file, if it exists: server\_installation\_directory/opt/tomcat/webapps/landscaper.war 
5.   Download and extract the installation files for the blueprint design server. These files are available for download from the IBM® Passport Advantage® website. See the [IBM UrbanCode Deploy download document](https://www.ibm.com/software/passportadvantage/pao_customer.html). 
6.   If you are using a database other than Apache Derby or PostgreSQL, make the JDBC JAR file for your database available to the installer by completing one of these steps: 
    -   Place the JAR file for the database in the installation directory. On Linux, place it in the installation\_directory/ibm-ucd-patterns-install/web-install/media/server/opt/tomcat/lib folder, and on Windows, place it in the installation\_directory\\media\\server\\opt\\tomcat\\lib folder.
    -   Record the location of the JAR file, and, when you are prompted by the installer, specify both the path and file name.
7.   From the command line, run the installation program. On Windows, you must use the command line instead of the Windows PowerShell.
    -   On Linux, change to the installation\_directory/ibm-ucd-patterns-install/web-install/ folder, and run the install.sh file.
    -   On Windows, change to the installation\_directory folder, and run the install.bat file.
8.   Read the license agreements for the software package. Press the Space bar to show one page at a time, or press F to show the entire license text. 
9.   If you agree to the terms of all of the license agreements, press Y, and then press Enter. 
10.  At the prompt `Specify the directory where the blueprint design server for UrbanCode Deploy should be installed`, specify the current installation folder and press Enter. 
11.  At the prompt `A previous version exists in the specified directory. Do you want to upgrade the currently installed version? [y, n]`, press Y and then press Enter. The installation program installs the new version of the server and connects it to the existing database.

    **Note:** If you upgraded from a version before 6.2.1.2 to version 6.2.1.2 or later and secured connections by using SSL, the server.xml file in the server\_installation\_directory/opt/tomcat folder was replaced. The previous server.xml file was retained and renamed server.xml.number, where number represents the time of the server upgrade.

12.  Start the Tomcat service: 
    -   On Linux, run the following command:

        ```
        server\_installation\_directory/bin/server start
        ```

        Use the location of the blueprint design server installation for `server\_installation\_directory`. The default installation directory is /opt/ibm-ucd-patterns. By default, the command looks like the following code:

        ```
        /opt/ibm-ucd-patterns/bin/server start
        ```

    -   On Windows, run the following command:

        ```
        C:\server\_installation\_directory\bin\start_server
        ```

        Use the location of the blueprint design server installation for `server\_installation\_directory`. The default installation directory is C:\\Program Files\\ibm-ucd-patterns. By default, the command looks like the following code:

        ```
        "C:\Program Files\ibm-ucd-patterns\bin\start_server"
        ```

13.  Start the cloud discovery service. See [Starting the blueprint designer, cloud discovery service, and engine](start_patterns.md).
14.  If the blueprint design server is connected to an HCL UrbanCode Deploy server, update the agent components: 
    1.   On the HCL UrbanCode Deploy server, delete the following components: `ucd-agent-linux-ppc64`, `ucd-agent-linux-x86_64`, `ucd-agent-win-x86_64`, and `ucd-agent-linux-s390x`. 
    2.   Install the agent components as described on step [3](ucdp_integrate.md#agent_components_step) of [Connecting the blueprint design server to the server](ucdp_integrate.md). 
15. If you provision environments in VMware vCenter, you must create new images to use with the blueprint designer.In versions 6.2.4 and later, you use VMware Tools and customization specifications to provision images to vCenter. See [Configuring VMware vCenter images](cloud_connect_vmware_images.md#).
16.  If you are upgrading from before 6.1.2, provision environments in VMware vCenter, and use VMware NSX, provide VMware NSX credentials for your cloud project. If you provide VMware NSX credentials, you can create networks on vCenter clouds.
    1.   Log in to the blueprint designer as a user with the following permissions: 
        -   Configure Security
        -   Manage Users & Groups
    2.   Click **Settings** \> **Clouds**. 
    3.   From the Clouds pane, select the vCenter cloud connection to update. 
    4.   From the Authorization pane, select the project to update. 
    5.   Select the **Configure NSX access** check box and specify the following information: 

        |Property|Description|
        |--------|-----------|
        |**NSX User ID**|Enter the NSX user ID.|
        |**NSX Password**|Enter the password for the NSX user ID.|
        |**NSX Host**|Enter the VMWare NSX API host IP address and port number.|


**Note:** You must upgrade the engine. See [Upgrading engines](upgrade_engine.md).

If you use Chef recipes, you might need to take more steps.

-   If you are upgrading from a version before version 6.2.1 and use Chef recipes, you must upgrade the Chef hook on the images on your cloud. See [Updating Chef-compatible images](cloud_update_chef_images.md#).
-   In versions of the blueprint designer before version 6.2.1, you hosted the Chef validator key a location that your cloud environments can access. You can remove the copy of the validator key that you hosted. If you remove the validator key, before you provision an environment that contains Chef roles, you must modify the blueprint. See [Modifying blueprints to access the Chef validator key in version 6.2.1 and later](chef_validator.md#).

**Parent topic:** [Upgrading and migrating](../../com.udeploy.doc/topics/c_node_upgrading.md)

