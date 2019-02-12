# Modeling environments for Amazon Web Services

To model an Amazon Web Services \(AWS\) environment, log in with an AWS cloud project and specify the AWS-specific information in a blueprint.

-   Connect the blueprint design server to a cloud system. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).
-   Make sure that your user account is authenticated to a cloud system. See [Setting up access to clouds in the blueprint designer](../../com.udeploy.admin.doc/topics/security_auth_bds.md).
-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.udeploy.doc/topics/ucdp_integrate.md).
-   Log in to the blueprint designer.
-   At the top of the page, select the cloud project and region to use.

1.   Create the blueprint. See [Creating files with the blueprint designer](blueprint_edit.md#).
2.   Add resources from the palette to the blueprint, such as virtual images. The palette shows resources from the currently connected cloud, which is shown in the upper-right corner of the page. For more information on working with the blueprint designer, see [Editing blueprint diagrams](blueprint_diagram.md) and [Editing blueprint source code](blueprint_source.md).
3.   Customize the blueprint source code for your configuration of AWS. For example, you might have to change the mount points of volumes from defaults like `/dev/vdc` to specific locations like `/dev/xvdc`, as in the following example:

    ```
    linux_image_1_volume_1_attachment:
      type: OS::Cinder::VolumeAttachment
      properties:
        volume_id: vol-4d4aaa04
        instance_uuid: { get_resource: linux_image_1_volume_1_attachment }
        mountpoint: /dev/xvdc
    ```

    In another example, to ensure that nodes and volumes are created in the same zone, you might need to update the `availability_zone` property to resources in the blueprint, as in the following example:

    ```
    parameters:
      availability_zone:
        type: string
        **default: us-east-1d**
        description: Name of availability zone in which to create the instance
    
    resources:
    linux_image_A:
      type: OS::Nova::Server
      properties:
        flavor: { get_param: flavor }
        image: "LinuxImageA"
        key_name: { get_param: key_name }
        name: "images/linux_image_A"
        **availability\_zone: \{ get\_param: availability\_zone \}**
      metadata:
        ec2_properties:
          access_id: ABC12345
          secret_key: 67890DEF
    linux_image_A_volumeA_attachment:
      type: OS::Cinder::VolumeAttachment
      properties:
        volume_id: volumeA
        instance_uuid: { get_resource: linux_image_A }
        mountpoint: /dev/xvdc
      metadata:
        ec2_properties:
          access_id: ABC12345
          secret_key: 67890DEF
    
    volumeA:
      type: OS::Cinder::Volume
      properties:
        name: volumeA
        **availability\_zone: \{ get\_param: availability\_zone \}**
        size: 1
      metadata:
        ec2_properties:
          access_id: ABC12345
          secret_key: 67890DEF
    ```

    For more information, see the Amazon Web Services documentation.

4.   In the blueprint source code, specify any additional core or extended properties for the resources in the blueprint. Specify core properties in the `properties` section of the resource code, as in the following example:

    ```
    
    linux_image_A:
      type: OS::Nova::Server
      properties:
        flavor: { get_param: flavor }
        image: "LinuxImageA"
        key_name: { get_param: key_name }
        name: "images/linux_image_A"
        availability_zone: { get_param: availability_zone }
    ```

    Specify extended properties in the `metadata/ec2_properties` section of the resource code, as in the following example. This example applies two tags to a virtual image.

    ```
    
    linux_image_A:
      type: OS::Nova::Server
      properties:
        flavor: { get_param: flavor }
        image: "LinuxImageA"
        key_name: { get_param: key_name }
        name: "images/linux_image_A"
        availability_zone: { get_param: availability_zone }
      metadata:
        ec2_properties:
          cluster: blue
          database_type: mysql
    ```

    For information about the properties that are available for resource types, see [Heat resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ov.md).

5.  Create a configuration file and externalize properties to the file.See [Editing configuration files](blueprint_configs.md).
6.   In the configuration file, ensure that the core OpenStack types are mapped to Amazon Elastic Compute Cloud \(EC2\) types. The configuration file must have mapping similar to the following code:

    ```
    resource_registry:
      OS::Nova::Server : IBM::EC2::Server
      OS::Cinder::Volume : IBM::EC2::Volume
      OS::Cinder::VolumeAttachment : IBM::EC2::VolumeAttachment
      OS::Neutron::Port : IBM::EC2::Port
      OS::Neutron::Net : IBM::EC2::VPC
      OS::Neutron::Subnet : IBM::EC2::Subnet
      OS::Neutron::Router : IBM::EC2::RouteTable
      OS::Neutron::RouterGateway : IBM::EC2::InternetGateway
      OS::Neutron::RouterInterface : IBM::EC2::RouteTableAssociation
    ```


Add the components of your application to the blueprint. See [Deploying components with blueprints](blueprint_deploy_env.md).

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.edt.doc/topics/blueprint_edit_clouds.md)

