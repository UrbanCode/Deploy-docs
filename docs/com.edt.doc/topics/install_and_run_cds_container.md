# Installing and running the Cloud Discovery Service as a container

You can install and run the Cloud Discovery Service as a container.

The Cloud Discovery Service container image is for the x86\_64 platform.

1.   From the command line, change to the installation\_directory/ibm-ucd-patterns-install/web-install/containers folder. 
2.   Copy the `ibm-cloud-discovery-service-container-image-<version>.tar` file, and move it to a machine that hosts a Docker engine. 
3.   Log into the Docker engine machine as a user that belongs to the Docker group. Then, run this command: 

    ```
    docker load -i ibm-cloud-discovery-service-container-image-<version\>.tar
    ```

4.   To verify that you have successfully uploaded the ibm-ucd-cloud-discovery-service container image, run this command: 

    ```
    docker images local/ibm-ucd-cloud-discovery-service
    ```

5.   To accept the license, run this command: 

    ```
    docker run -d -e LICENSE="accept" -p 7575:7575 local/ibm-ucd-cloud-discovery-service:<version\_tag\>
    ```

    **Note:** If you have a custom Cloud Discovery Service file, you can use the CLOUDDISCOVERYSERVICE\_SETTINGS\_FILE variable to specify the file mounted path. The file must be mounted to the container. For more information, see the Docker help, [Use volumes](https://docs.docker.com/engine/admin/volumes/volumes/).

6.   Log into the HCL® UrbanCode™ Deploy blueprint designer. 
7.   In the upper-right corner, click the **Settings** icon, and then click **System Settings**. 
8.   In the General Settings section, update the **Cloud Discovery Service URL** field. 

    **Note:** You must ensure that the HCL UrbanCode Deploy blueprint designer can access the exposed port of the machine that hosts the HCL UrbanCode Deploy Cloud Discovery Service.


**Parent topic:** [Installing the blueprint design server](../../com.edt.doc/topics/install_server_bds.md)

