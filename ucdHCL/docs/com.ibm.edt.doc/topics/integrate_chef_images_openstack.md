# Using a dedicated environment to create Chef-compatible images on OpenStack-based clouds

To create images for OpenStack-based clouds that can use Chef, set up a development environment that includes the prerequisites, and then use the disk-image-create command.

To create images that are compatible with Chef and the blueprint designer, you can either update individual images or configure an environment to create images in bulk. To update individual images, see [Configuring OpenStack images](cloud_connect_openstack_images.md).

To create images in bulk, you must set up an environment to use in creating those images. This environment must include certain prerequisites, which are listed in the steps that follow. This environment does not have to be on the cloud system, and it does not have to be the same operating system as the images that you want to create for use on the cloud. The following procedure assumes a Red Hat Enterprise Linux™ \(RHEL\) version 7 operating system.

**Note:** Chef roles are supported only on RHEL version 6 and version 7 images.

1.   On RHEL version 7, install these packages: 
    -   `git`
    -   `qemu-system-x86 qemu-img`
    -   `kpartx`
2.  Using the `git` program, clone the following repositories as shown:

    ```
    git clone https://github.com/openstack/diskimage-builder.git
    git clone https://github.com/openstack/tripleo-image-elements.git
    git clone https://github.com/openstack/heat-templates.git
    git clone https://git.openstack.org/openstack/dib-utils.git
    ```

    Place all the cloned repositories into the same folder, such as /opt/image-builder.

3.   Add the Chef hook element to your environment by extracting the os-chef-config-hook.tgz file into the same folder that you placed the Git repositories. This file is provided in the engine installation media and is in the /ibm-ucd-patterns-install/engine-install/resources folder.

    ```
    tar -xf os-chef-config-hook.tgz
    ```

4.  Specify these environment variables:

    -   **ELEMENTS\_PATH**

        Specify the location of the Chef hook element that you extracted and the repositories that you cloned. Separate the locations of different paths with colons. For example, if you extracted the Chef hook element and cloned the repositories into the /opt/image-builder folder, the code might look like the following example:

        `/opt/image-builder/tripleo-image-elements/elements:/opt/image-builder/heat-templates/hot/software-config/elements:/opt/image-builder/os-chef-config-hook/heat-templates/hot/software-config/elements:/opt/image-builder/ibm-customizations/elements`

    -   **BASE\_IMAGE\_FILE**

        Specify the name of the file for the image.

    -   **DIB\_CLOUD\_IMAGES**

        Specify the location of the image file that is listed in the BASE\_IMAGE\_FILE variable.

    -   **PATH**

        Add the location of the disk image creation tool, such as `/usr/local/source/dib-utils/bin:$PATH`.

    -   **QEMU\_IMG\_OPTIONS**

        Specify the version of the `qemu-img` program to use, such as `compat=0.10`.

    For example, you might set these variables with the following code:

    ```
    export ELEMENTS_PATH=/opt/image-builder/tripleo-image-elements/elements:/opt/image-builder/heat-templates/hot/software-config/elements:/opt/image-builder/os-chef-config-hook/heat-templates/hot/software-config/elements:/opt/image-builder/ibm-customizations/elements
    export DIB_CLOUD_IMAGES=file:///usr/local/source/image
    export BASE_IMAGE_FILE=rhel-guest-image-7.0-20140930.0.x86_64.qcow2
    export PATH="/usr/local/source/dib-utils/bin:$PATH"
    export QEMU_IMG_OPTIONS="compat=0.10"
    ```

5.   Using the disk-image-create image creation tool, create the Chef-compatible image: 

    ```
    ./diskimage-builder/bin/disk-image-create vm image-type disable-selinux ntp 
      heat-config os-collect-config os-refresh-config os-apply-config 
      heat-config-chef heat-config-script 
      --image-size image-size 
      -o image-name
    ```

    **Note:** This command must be entered on a single line. The preceding command is split into multiple lines for clarity.

    -   **`image-type`**

        Specify the type of image, such as `rhel` for a Red Hat Enterprise Linux™ image. You can create an image type that is different from the operating system on which you create the image.

    -   **`image-size`**

        The size of the image in gigabytes.

    -   **`image-name`**

        The name of the output image.

    For more information about this command and the image creation process, see [http://docs.openstack.org/developer/diskimage-builder/](http://docs.openstack.org/developer/diskimage-builder/).

    For example, the following command creates a 20 GB image that is named chefhook-rhel-7.0.qcow2:

    ```
    ./diskimage-builder/bin/disk-image-create vm rhel 
      disable-selinux ntp heat-config os-collect-config 
      os-refresh-config os-apply-config heat-config-chef 
      heat-config-script --image-size 20 
      -o chefhook-rhel-7.0.qcow2
    ```

6.   Set the communications interval for the image to communicate with the Heat engine. The polling\_interval parameter is the frequency in seconds with which the image communicates with the Heat engine. By default, the polling\_interval is 30 seconds, but the default value can cause excessive engine load. To modify this value in the image, open the /etc/os-collect-config.conf configuration file in the image and add the following text:

    ```
    polling_interval = 90
    ```

    In this case, the polling\_interval value is `90` seconds.

    Ensure that the polling\_interval value is short enough that the virtual machine can collect any changes from the Heat engine before the stack timeout elapses. The default timeout value is 60 minutes, but you can set the timeout value for each cloud. See [Creating cloud projects for the blueprint designer](../../com.ibm.udeploy.admin.doc/topics/security_projects.md#).

7.  Upload the image to your cloud system.

When you edit blueprints in the blueprint designer, you can apply Chef roles to virtual images. See [Applying Chef roles to environments](blueprint_chef.md).

**Parent topic:** [Connecting to OpenStack and OpenStack-based clouds](../../com.ibm.edt.doc/topics/cloud_connect_openstack.md)

