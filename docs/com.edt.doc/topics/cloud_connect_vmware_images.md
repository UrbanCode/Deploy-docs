# Configuring VMware vCenter images

Before you can use VMware vCenter images with the blueprint designer, you must install VMware Tools and a virtual CD-ROM drive on those images.To configure images that are compatible with Chef roles, see [Configuring VMware vCenter images for Chef roles](cloud_connect_vmware_images_chef.md#).

1.  Install VMware Tools on the image and create a customization specification for it.See the VMware documentation.
2.   On a Linux™ image, enable password access through SSH for the root user: 
    1.   Open the file /etc/cloud/cloud.cfg in a text editor. 
    2.   Remove any lines of code that begin with `disable_root`. 
    3.   Add the following line of code: 

        ```
        disable_root: 0
        ```

    4.   Save your changes to the file. 
3.  On a Linux image, enable sudo access for a different user name.By default, the blueprint designer accesses vCenter virtual images by using the root password. To use a different user name, you must enable sudo access for it and disable password access for users in the sudo user group.
    1.  Create the user name and enable sudo access for it.For example, see [Configuring sudo Access](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux_OpenStack_Platform/2/html/Getting_Started_Guide/ch02s03.html).
    2.  From the command line, open the sudo configuration file that is located at /etc/sudoers by running this command: `visudo`.
    3.  In the file, add the following line of code to disable password access for users in the sudo user group: 

        ```
        %sudo ALL=(ALL) NOPASSWD:ALL
        ```

    4.  Save your changes to the file.
4.  On a Windows™ image, create an initial user name and password for the image.See the VMware documentation.
5.  Open ports that are required to communicate with your HCL® UrbanCode™ Deploy server.By default, open ports 8080 and 8843 to communicate with the server and port 7918 to allow the agent that the blueprint designer installs to communicate with the server. See [Firewall and communication configuration](../../com.udeploy.install.doc/topics/agent_firewalls.md#).
6.   Install a virtual CD-ROM drive on your image. See [Add a DVD or CD-ROM Drive to a Virtual Machine](https://pubs.vmware.com/vsphere-4-esx-vcenter/index.jsp?topic=/com.vmware.vsphere.vmadmin.doc_41/vsp_vm_guide/configuring_virtual_machines/t_add_a_dvd_cd-rom_drive_to_a_virtual_machine.html).
7.   Capture the image as a template for the cloud system: 
    1.   Shut down the image. For example, on a Linux image, run the following command:

        ```
        shutdown -h now
        ```

    2.   From the VMware vSphere Web Client, find your instance. 
    3.   Right-click the instance and then click **Clone to Template** and follow the steps to create a template from your image. 

You can use the image with the blueprint designer. See [Modeling environments for VMware vCenter](blueprint_edit_vc.md).

**Parent topic:** [Connecting to VMware vCenter v5.5 to 6.0](../../com.edt.doc/topics/cloud_connect_vmware.md)

