# Configuring VMware vCenter images for Chef roles

 Before you can use VMware vCenter images that run Chef roles with the blueprint designer, you must install cloud-init and a virtual CD-ROM drive on those images. Cloud-init is a set of scripts and utilities that cloud systems use to initialize and configure instances. Chef roles can run on only Red Hat Enterprise Linux™ \(RHEL\) version 6 and version 7 image images.

1.   Install cloud-init version 0.7.5 or version 0.7.6. This package is available from the Red Hat Network \(RHN\) package manager on the common channel. For example, if you are using a RHEL version 7 image, you can enable the common repository and install cloud-init with the following command:

    ```
    yum install --enablerepo rhel-7-server-rh-common-rpms cloud-init
    ```

    You might need to adapt this command for your distribution of Linux™. For example, for RHEL version 6, substitute the repository `rhel-6-server-rh-common-rpms` in this command. If you have a problem enabling the common repository, you might need to subscribe to the common channel with a command that is similar to the following example:

    ```
    subscription-manager repos --enable=rhel-7-server-rh-common-rpms
    ```

    Then, try running the install command again.

2.   On a Linux image, enable password access through SSH for the root user: 
    1.   Open the file /etc/cloud/cloud.cfg in a text editor. 
    2.   Remove any lines of code that begin with `disable_root`. 
    3.   Add the following line of code: 

        ```
        disable_root: 0
        ```

    4.   Save your changes to the file. 
3.   If you want to run Chef roles on the image, run the automated script to install the heat-config toolchain on the image. 

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

        Ensure that the polling\_interval value is short enough that the virtual machine can collect any changes from the Heat engine before the stack timeout elapses. The default timeout value is 60 minutes, but you can set the timeout value for each cloud. See [Creating cloud projects for the blueprint designer](../../com.udeploy.admin.doc/topics/security_projects.md#).

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

4.   Install a virtual CD-ROM drive on your image. See [Add a DVD or CD-ROM Drive to a Virtual Machine](https://pubs.vmware.com/vsphere-4-esx-vcenter/index.jsp?topic=/com.vmware.vsphere.vmadmin.doc_41/vsp_vm_guide/configuring_virtual_machines/t_add_a_dvd_cd-rom_drive_to_a_virtual_machine.html).
5.   Capture the image as a template for the cloud system: 
    1.   Shut down the image. For example, on a Linux image, run the following command:

        ```
        shutdown -h now
        ```

    2.   From the VMware vSphere Web Client, find your instance. 
    3.   Right-click the instance and then click **Clone to Template** and follow the steps to create a template from your image. 

You can use the image with the blueprint designer. See [Modeling environments for VMware vCenter](blueprint_edit_vc.md).

**Parent topic:** [Connecting to VMware vCenter v5.5 to 6.0](../../com.edt.doc/topics/cloud_connect_vmware.md)

