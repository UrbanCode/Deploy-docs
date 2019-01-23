# Configuring private SoftLayer images

Before you use SoftLayer® private \(custom\) images with the blueprint designer, you can install the cloud-init package on those images. If you want to run Chef roles on the image, you must use the cloud-init package.The cloud-init package is a set of scripts and utilities that cloud systems use to initialize and configure instances.

The following steps apply to private images only. To use SoftLayer public images with the blueprint designer, see [Modeling environments for SoftLayer](blueprint_edit_softlayer.md).

1.   On the Linux™ image, install the cloud-init package, version 0.7.5 or version 0.7.6. This package is available from the Red Hat Network \(RHN\) common channel. On Linux images, you can often install the cloud-init package with the package manager. For example, if you are using a Red Hat Enterprise Linux \(RHEL\) version 7 image, you can enable the common repository and install the cloud-init package with the following command:

    ```
    yum install --enablerepo rhel-7-server-rh-common-rpms cloud-init
    ```

    You might need to adapt this command for your distribution of Linux. For example, for RHEL version 6, substitute the repository `rhel-6-server-rh-common-rpms` in this command. If you encounter a problem while you are enabling the common repository, you might need to subscribe to the common channel with a command that is similar to the following example:

    ```
    subscription-manager repos --enable=rhel-7-server-rh-common-rpms
    ```

    After you subscribe to the common channel, try running the install command again.

    If you still are unable to install the cloud-init package, manually enable the Extra Packages for Enterprise Linux \(EPEL\) repository. Locate the RPM Package Manager \(RPM\) file for the EPEL repository that corresponds to your operating system and version. The RPM file name is `epel-release-operation\_system\_version.noarch.rpm`, where the operation\_system\_version value corresponds to the version number of your Linux operating system. Then, run the following commands:

    ```
    wget https://repository\_mirror/epel-release-operation\_system\_version.noarch.rpm
    rpm -ivh epel-release-operation\_system\_version.noarch.rpm
    ```

    Then, try running the install command again.

    The following instructions assume that the cloud-init package was installed by the yum package manager. You might need to adapt these instructions to work with other package managers or other distributions of Linux.

2.   On the image, provide the Heat types that are necessary for the cloud-init package. Copy the file DataSourceSL.py to the folder /usr/lib/pythonversion\_number/site-packages/cloudinit/sources/. This file is provided with the installation files for the Heat engine and is available at the following location: ibm-ucd-patterns-install/engine-install/resources/cloud-init/softlayer/linux 
3.   Update the configuration file for the cloud-init package: 
    1.   Open the file /etc/cloud/cloud.cfg in a text editor. 
    2.   Remove any lines of code that begin with `datasource_list`. 
    3.   Add the following line of code: 

        ```
        datasource_list: ['SL']
        ```

    4.   To enable password access through SSH for the root user, set the value of `disable_root` to `0`. If the `disable_root` configuration value is not present, then add the following line of code to the file:

        ```
        disable_root: 0
        ```

    5.   Save your changes to the file. 
4.  Open ports that are required to communicate with your HCL® UrbanCode™ Deploy server.By default, open ports 8080 and 8843 to communicate with the server and port 7918 to allow the agent that the blueprint designer installs to communicate with the server. See [Firewall and communication configuration](../../com.ibm.udeploy.install.doc/topics/agent_firewalls.md#).
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

6.   Capture the image as a template for the cloud system: 

    1.   Shut down the image with the following command: 

        ```
        shutdown -h now
        ```

        **Note:** Before you capture the image as a template, you must shut it down.

    2.   From the SoftLayer Customer Portal, find your instance by clicking **Devices** \> **Device List**. 
    3.   Click the instance to select it. 
    4.   From the **Actions** list, click **Power On/Off**. The system informs you that the image is already powered off.

        **Important:** This step is necessary to ensure that the SoftLayer cloud knows that the image is powered off.

    5.   From the **Actions** list, click **Create Image Template** and follow the steps to create a template from your image. 
    For more information about creating images from the SoftLayer Customer Portal, see [Create a Standard Image](http://knowledgelayer.softlayer.com/procedure/create-standard-image).


You can use the private image in blueprints that you create on the blueprint designer. See [Modeling environments for SoftLayer](blueprint_edit_softlayer.md).

**Parent topic:** [Connecting to the SoftLayer cloud](../../com.ibm.edt.doc/topics/cloud_connect_softlayer.md)

