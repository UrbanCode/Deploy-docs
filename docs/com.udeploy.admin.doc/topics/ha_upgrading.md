# Upgrading high-availability installations

All servers that are configured for the HA feature must be on the same version. Thus, all servers must be upgraded at the same time.

**Note:** During the upgrade of UrbanCode Deploy, the contents of the appdata/patches directory \(including all .jar files\) will be appended with .off, preventing the existing test fixes from being loaded once the UCD Server is started post-installation. All UI test fixes applied to the Tomcat directory will be wiped by the upgrade and will not be recoverable.

If a text fix received for a reported defect is not fixed in the upgraded version, you may need to open a Support Case to request a new build.

1.   Back up the database. 
2.   Ensure that no application and generic processes are running. Open the **Dashboard** and confirm that no processes are running. If processes are running, you can wait for them to complete or by clicking **Cancel** in the same row as each process, cancel them.
3.   Download and extract the installation package. Upgrades are done with the same package used to perform new installations.
4.   Shut down the servers. 

    **Warning:** Ensure that all servers are stopped. If any servers are accessing the database when the upgrade happens, the upgrade will cause errors.

5.   Ensure that each server is stopped and unable to connect to the load balancer. 

    1.   Check to ensure that there is no file server.pid in the server\_install/var folder. 
    2.   Check for running system processes. For example, on Linux™, you can use the netstat or ps commands. For example, if the server is running on port 8443, use the command `netstat -nap | grep 8443`. You can also run `ps -ef | grep server` and look for the server system process in the results.
    3.   If any server processes are still running, stop them. 
    If a server process is still running, when you install the new version, you see an error that says "A previously installed version of HCL® UrbanCode™ Deploy is running. Please shutdown the running HCL UrbanCode Deploy and start the installation again."

6.   If you are upgrading from a version before 6.1.1.5, update the network storage to match the folders in the new version. For information about how to structure the folders, see [Setting up high-availability clusters](../../com.udeploy.doc/topics/server_install_clustered.md).

    Depending on how you set up network storage for the high-availability cluster in the previous version, you might need to move files and folders to put them in the place that the new version of the server expects to find them. When you run the installation program, specify the location of the app\_data folder in the **Where should the server store application data such as logs, plugins, and keystores?** prompt.

    For more information, see [Setting up high-availability clusters](../../com.udeploy.doc/topics/server_install_clustered.md).

7.  Run the server installation script.
8.  From the command line, run the server installer program. 

    -   On Windows™, run the install-server.bat file.
    -   On Linux, run ./install-server.sh.
    -   To install a FIPS-compliant server, add the switch `-fips` to the command, such as `install-server.sh -fips`.

        **Note:** If you install a FIPS-compliant server, cloud provisioning is not available. Your JVM connects to only FIPS 140-2 certified IBM® providers.

    Depending on your system settings, you might need to run this file as an administrator.

9.  When prompted for the location of the installation directory, enter the path to one of the servers.By specifying an existing installation, you are asked if you want to upgrade the current installation. If you answer yes, the script leads you through the upgrade steps.
10.  Restart the upgraded server. Always use service scripts to start or stop the server. See [Starting and stopping the server](../../com.udeploy.install.doc/topics/run_server.md).
11.  After the first server is back online, upgrade the other servers. After you upgrade the first node, you will not be prompted to upgrade the database when you upgrade the other nodes. 

**Parent topic:** [Upgrading and migrating](../../com.udeploy.doc/topics/c_node_upgrading.md)

**Parent topic:** [Managing security](../../com.udeploy.admin.doc/topics/security_ch.md)

