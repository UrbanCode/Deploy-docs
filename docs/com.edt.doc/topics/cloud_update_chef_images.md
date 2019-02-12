# Updating Chef-compatible images

If your image uses Chef recipes, after you upgrade to HCL® UrbanCode™ Deploy version 6.2.1 or later, you must manually update the Chef hook on the images in your cloud.

1.   Extract the os-chef-config-hook.tgz file. This file is provided in the heat engine installation media and is in the following location: /installation\_files\_location/ibm-ucd-patterns-install/engine-install/resources.
2.   Create a copy of the `hook-chef` file, which is in the following directory: extracted\_files/os-chef-config-hook/heat-templates/hot/software-config/elements/heat-config-chef/install.d. 
3.   Rename the `hook-chef.py` file that you copied as `chef`. 
4.   On an image that you configured for Chef, in the /var/lib/heat-config/hooks folder, replace the `chef` file with the copy that you renamed. 
5.   Change the permission of the new `chef` file to 0777. 
6.   Shut down the image with the following command: 

    ```
    shutdown -h now
    ```

7.   Create an image and upload it to your cloud. For more information, see [Creating Chef-compatible images](integrate_chef_images.md#).

After you update the Chef hook, you can provision environments from blueprints that contain Chef recipes. You can also modify blueprints that contain Chef recipes to obtain the Chef validator key value without the use of a hosted file that contains the value. See [Modifying blueprints to access the Chef validator key in version 6.2.1 and later](chef_validator.md#).

**Parent topic:** [Integrating with Chef](../../com.edt.doc/topics/integrate_chef.md)

