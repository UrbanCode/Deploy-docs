# Modeling environments for VMware vCenter

To model a VMware vCenter environment, log in with a VCenter cloud project and specify the VCenter-specific information in a blueprint.

-   Connect the blueprint design server to a cloud system. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).
-   Make sure that your user account is authenticated to a cloud system. See [Setting up access to clouds in the blueprint designer](../../com.ibm.udeploy.admin.doc/topics/security_auth_bds.md).
-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.ibm.udeploy.doc/topics/ucdp_integrate.md).
-   Log in to the blueprint designer.
-   At the top of the page, select the cloud project and region to use.

1.   Create the blueprint. See [Creating files with the blueprint designer](blueprint_edit.md#).
2.   Add resources from the palette to the blueprint, such as virtual images. The palette shows resources from the currently connected cloud, which is shown in the upper-right corner of the page. For more information on working with the blueprint designer, see [Editing blueprint diagrams](blueprint_diagram.md) and [Editing blueprint source code](blueprint_source.md).
3.   Specify the property for the customization specification. VMware Tools must be installed on the image to specify the customization spec. In the OS::Nova::Server resource for the image, add and define the customization\_spec extended property, as shown in the following code:

    ```
    linux_image_A:
      type: OS::Nova::Server
      properties:
        name: "My image A"
        image: "MyImage123"
      metadata:
        vmware_properties:
          **customization\_spec: your-customization-spec-name
          use\_cloudinit: False
          init\_password: password
          init\_username: user\_name**
    ```

    In the `vmware_properties` property, specify the following properties:

    -   **customization\_spec**

        The name of an existing vCenter customization specification.

    -   **use\_cloudinit**

        Whether to use cloud-init. In most cases, the value of this property is False. Set this value to True only if you apply Chef roles to images.

    -   **init\_password**

        The password for the user name. For Linux™ images, you must provide a value. For Windows™ images, you do not provide a value.

    -   **init\_username**

        The user name for the virtual image. For Linux™ images, provide a value if you are not using root. For Windows™ images, you do not provide a value.

4.   To provision the images in a specific folder on the cloud, add a destination\_folder extended property to each image, as in the following example code. The target folder must already exist on the vCenter system.

    ```
    linux_image_A:
      type: OS::Nova::Server
      properties:
        name: "My image A"
        image: "MyImage123"
      metadata:
        vmware_properties:
          destination_folder: "/MyImageFolder/MyNewImages"
    ```

5.   Specify whether to provision the images on a cluster or on a resource pool. 

    -   To provision the images on a cluster, the cluster must have enabled support for DRS \(Distributed Resource Scheduler\). Then, on each image, specify the cluster extended property on the image, as in the following example. You can specify a literal value or you can make this property a parameter and specify it at provisioning time.

        ```
        linux_image_A:
          type: OS::Nova::Server
          properties:
            name: "My image A"
            image: "MyImage123"
          metadata:
            vmware_properties:
              cluster: { get_param: cluster }
        ```

    -   To provision the images on a resource pool, specify the resource\_pool extended property, as in the following example. You can specify a literal value or you can make this property a parameter and specify it at provisioning time.

        ```
        linux_image_A:
          type: OS::Nova::Server
          properties:
            name: "My image A"
            image: "MyImage123"
          metadata:
            vmware_properties:
              resource pool: { get_param: resourcePool }
        ```

    **Note:** Do not specify both the cluster and resource\_pool extended properties. If you do, the environment fails to provision.

6.   To provision Linux images to a static network in a cloud, specify the properties for the network. In the OS::Nova::Server resource for the image, add and define the fixed\_ips property and the vmware\_properties extended properties, as shown in the following code:

    ```
    linux_image_A:
      type: OS::Nova::Server
      properties:
        name: "My image A"
        image: "MyImage123"
    **    fixed\_ips:
          - ip\_address: 10.10.10.212
            subnet: 255.255.255.0**
      metadata:
    **    vmware\_properties:
          gateway: 10.10.10.1
          dns: \['11.110.135.31', '11.110.135.52'\]
          hostname: your-host-name
          domain\_name: your-domain-name.com**
    ```

    In the `fixed_ips` property, specify the following properties:

    -   **ip\_address**

        The IP address that is wanted in the subnet for this port.

    -   **subnet**

        The subnet in which to allocate the IP address for this port.

    In the `vmware_properties` metadata, specify the following properties:

    -   **gateway**

        The IP address of the gateway.

    -   **dns**

        A list of DNS name servers to be used.

    -   **hostname**

        The hostname of the instance.

    -   **domain\_name**

        The domain name of the DHCP pool.

7.   If you configured your provisioned virtual image for SSH, to access to the virtual image through SSH, you must add resources to the blueprint source code. 
    -   If your virtual image does not contain a component, add the `OS::Heat::MultipartMime` and `OS::Heat::CloudConfig` resources:

        ```
          multipart:
            type: OS::Heat::MultipartMime
            properties:
              parts:
                - config: {get_resource: cloud\_config}
                subtype: cloud-config
        
          cloud\_config:
            type: OS::Heat::CloudConfig
            properties:
              cloud_config:
                users:
                  - default
                  - name: "user\_ID"
                    lock-passwd: true
                    sudo: ALL=(ALL) NOPASSWD:ALL
                    ssh-authorized-keys:
                      - { get_param: key_name }
        ```

        -   For the user\_ID, specify the login ID for the virtual image.
        -   Ensure that the resource name of the `OS::Heat::CloudConfig` resource is specified in the - config: \{get\_resource: cloud\_config\} property in the `OS::Heat::MultipartMime` resource.
        -   The key\_name parameter must be in the following form:

            ```
            parameters:
              key_name: "ssh-rsa s1AAB3Nza45yc2EA27AADAQADDABAQC jsmith@example.com"
            ```

        Additionally, the `OS::Nova::Server` resource must contain the `user_data_format` and `user_data` properties. For example, if your virtual image name is linux\_image\_B, the `OS::Nova::Server` resource contains the following code:

        ```
        linux_image_B:
          type: OS::Nova::Server
          properties:
            user_data_format: SOFTWARE_CONFIG
            user_data: {get_resource: multipart}
        ```

        Ensure that the resource name of the `OS::Heat::MultipartMime` resource is specified in the user\_data: \{get\_resource: multipart\} property in the `OS::Nova::Server` resource.

    -   If your virtual image does contain a component, add the `OS::Heat::CloudConfig` resource:

        ```
          cloud_config:
            type: OS::Heat::CloudConfig
            properties:
              cloud_config:
                users:
                  - default
                  - name: "user\_ID"
                    lock-passwd: true
                    sudo: ALL=(ALL) NOPASSWD:ALL
                    ssh-authorized-keys:
                      - { get_param: key_name }
                    
        ```

        -   For the user\_ID, specify the login ID for the virtual machine.
        -   The key\_name parameter must be in the following form:

            ```
            parameters:
              key_name: "ssh-rsa s1AAB3Nza45yc2EA27AADAQADDABAQC jsmith@example.com"
            ```

        Additionally, the `OS::Heat::MultipartMime` must contain the `- config: {get_resource: cloud_config}` resource. For example, if your virtual image name is linux\_image\_B, the `OS::Heat::MultipartMime` resource resembles the following code:

        ```
          linux_image_B_cloudinit_mime:
            type: OS::Heat::MultipartMime
            properties:
              parts:
                - config: {get_resource: ucd_agent_install_linux }
                - config: {get_resource: cloud_config}
                subtype: cloud-config
        ```

    -   If you configured a virtual image for SSH and later added a component to it, you must add the following property to the `OS::Heat::MultipartMime` resource: `- config: {get_resource: ucd_agent_install_linux }`

        The `OS::Heat::MultipartMime` resource resembles the following code:

        ```
          multipart:
            type: OS::Heat::MultipartMime
            properties:
              parts:
                - config: {get_resource: cloud_config}
                subtype: cloud-config
                - config: {get_resource: ucd_agent_install_linux }
        ```

8.  Create a configuration file and externalize properties to the file.See [Editing configuration files](blueprint_configs.md).
9.  In the configuration file, ensure that the core OpenStack types are mapped to VMware vCenter types.The configuration file must have mapping similar to the following code:

    ```
    resource_registry:
      OS::Nova::Server : IBM::VCenter::Server
      OS::Neutron::Port : IBM::VCenter::Port
      OS::Neutron::Net : IBM::VCenter::Network
    ```


Add the components of your application to the blueprint. See [Deploying components with blueprints](blueprint_deploy_env.md).

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.ibm.edt.doc/topics/blueprint_edit_clouds.md)

