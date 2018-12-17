# Configuring OpenStack images

Before you can use images on an OpenStack or OpenStack-based cloud with the blueprint designer, you must configure cloud-init on those images.Cloud-init is a set of scripts and utilities that cloud systems use to initialize and configure instances.

1.   On the image, install a package for cloud initialization. 
    -   If you use a Linux™ image, install the cloud-init package, version 0.7.5 or version 0.7.6. This package is available from the Red Hat Network \(RHN\) common channel. On Linux images, you can often install cloud-init with the package manager. For example, if you are using a Red Hat Enterprise Linux \(RHEL\) version 7 image, you can enable the common repository and install cloud-init with the following command:

        ```
        yum install --enablerepo rhel-7-server-rh-common-rpms cloud-init
        ```

        You might need to adapt this command for your distribution of Linux. For example, for RHEL version 6, substitute the repository `rhel-6-server-rh-common-rpms` in this command. If you have a problem enabling the common repository, you might need to subscribe to the common channel with a command that is similar to the following example:

        ```
        subscription-manager repos --enable=rhel-7-server-rh-common-rpms
        ```

        Then, try running the install command again.

        The following instructions assume that cloud-init was installed by the yum package manager. You might need to adapt these instructions to work with other package managers or other distributions of Linux.

    -   If you use a Windows™ image, install the cloudbase-init package. Download it from [https://www.cloudbase.it/downloads/CloudbaseInitSetup\_Beta.msi](https://www.cloudbase.it/downloads/CloudbaseInitSetup_Beta.msi) and install it by following the procedure at [http://www.cloudbase.it/cloud-init-for-windows-instances/](http://www.cloudbase.it/cloud-init-for-windows-instances/). Accept the default values, and ensure that the user name is Administrator.
2.   On a Linux image, enable password access through SSH for the root user: 
    1.   Open the file /etc/cloud/cloud.cfg in a text editor. 
    2.   Remove any lines of code that begin with `disable_root`. 
    3.   Add the following line of code: 

        ```
        disable_root: 0
        ```

    4.   Save your changes to the file. 
3.  Open ports that are required to communicate with your HCL® UrbanCode™ Deploy server.By default, open ports 8080 and 8843 to communicate with the server and port 7918 to allow the agent that the blueprint designer installs to communicate with the server. See [Firewall and communication configuration](../../com.ibm.udeploy.install.doc/topics/agent_firewalls.md#).
4.   Configure the image to resize the file system in response to disk size changes. See [OpenStack Linux image requirements](http://docs.openstack.org/image-guide/openstack-images.html#disk-partitions-and-resize-root-partition-on-boot-cloud-init). 
5.   If you want to run Chef roles on the image, run the automated script to install the heat-config toolchain on the image. 

    **Note:** Chef roles are supported only on RHEL version 6 and version 7 images.

    1.   Download and extract the file os-chef-config-hook.tgz. This file is provided in the Heat engine installation media and is in the following location: /installation\_files\_location/ibm-ucd-patterns-install/engine-install/resources 
    2.   Copy the file install.sh to a temporary folder, such as /tmp/install\_chain. 
    3.   On the command line, move to the temporary folder. 
    4.   Run the following command: 

        ```
        ./install.sh > install.log 2>&1
        ```

        This command might take several minutes to complete.

    5.   Verify that the command ran successfully by looking at the end of the file install.log. If the command ran successfully, the end of this file shows the output of the os-collect-config command, as in the following example:

        ```
        + cat /etc/os-collect-config.conf
        [DEFAULT]
        command = os-refresh-config
        + os-collect-config --one-time --debug
        2015-08-14 13:51:30.764 27527 WARNING os_collect_config.ec2 [-] ('Connection aborted.', error(101, 'Network is unreachable'))
        2015-08-14 13:51:30.765 27527 WARNING os-collect-config [-] Source [ec2] Unavailable.
        2015-08-14 13:51:30.765 27527 WARNING os_collect_config.cfn [-] No Access Key ID configured.
        2015-08-14 13:51:30.766 27527 DEBUG os-collect-config [-] Source [cfn] Not configured. collect_all /usr/lib/python2.6/site-packages/os_collect_config/collect.py:153
        2015-08-14 13:51:30.766 27527 WARNING os_collect_config.heat [-] No auth_url configured.
        2015-08-14 13:51:30.766 27527 DEBUG os-collect-config [-] Source [heat] Not configured. collect_all /usr/lib/python2.6/site-packages/os_collect_config/collect.py:153
        2015-08-14 13:51:30.767 27527 WARNING os_collect_config.request [-] No metadata_url configured.
        2015-08-14 13:51:30.767 27527 WARNING os-collect-config [-] Source [request] Unavailable.
        2015-08-14 13:51:30.767 27527 WARNING os_collect_config.local [-] /var/lib/os-collect-config/local-data not found. Skipping
        2015-08-14 13:51:30.767 27527 WARNING os_collect_config.local [-] No local metadata found (['/var/lib/os-collect-config/local-data'])
        2015-08-14 13:51:30.768 27527 DEBUG os-collect-config [-] No changes detected. __main__ /usr/lib/python2.6/site-packages/os_collect_config/collect.py:274
        ```

    6.   Set the communications interval for the image to communicate with the Heat engine. The polling\_interval parameter is the frequency in seconds with which the image communicates with the Heat engine. By default, the polling\_interval is 30 seconds, but the default value can cause excessive engine load. To modify this value, open the /etc/os-collect-config.conf configuration file and add the following text:

        ```
        polling_interval = 90
        ```

        In this case, the polling\_interval value is `90` seconds.

        Ensure that the polling\_interval value is short enough that the virtual machine can collect any changes from the Heat engine before the stack timeout elapses. The default timeout value is 60 minutes, but you can set the timeout value for each cloud. See [Creating cloud projects for the blueprint designer](../../com.ibm.udeploy.admin.doc/topics/security_projects.md#).

    7.   Verify that the Chef client is running. On the command line, run the following command:

        ```
        chef-client -v
        ```

        The version number is displayed. If the Chef client is not running, manually install it. See [Chef Downloads: Chef Client](https://downloads.chef.io/chef-client/).

    8.   Verify that the knife command-line tool is running. On the command line, run the following command:

        ```
        knife -v
        ```

        The version number is displayed. If the knife command-line tool is not running, manually configure the Chef development kit. See [Install the Chef DK](https://docs.chef.io/install_dk.html).

6.   Shut down the image with the following command: 

    ```
    shutdown -h now
    ```

7.   Upload the image to your cloud. For more information, see the documentation for your cloud system.

You can use the image in blueprints that you create on the blueprint designer. See [Modeling environments for OpenStack and OpenStack-based clouds](blueprint_edit_os.md).

**Parent topic:** [Connecting to OpenStack and OpenStack-based clouds](../../com.ibm.edt.doc/topics/cloud_connect_openstack.md)

