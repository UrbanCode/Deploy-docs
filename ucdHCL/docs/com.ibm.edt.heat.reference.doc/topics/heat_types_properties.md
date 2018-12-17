# Resource type properties: core and extended

In blueprints, Heat resource types have two types of properties: core and extended. Core properties are inherited from a base type and extended properties are added to a type that comes with HCL® UrbanCode™ Deploy.

In the blueprint designer, when you drag a resource from the palette to a blueprint, the blueprint designer creates a resource in the blueprint. You might expect the blueprint designer to create a resource that is specific to the type of cloud that you are connected to. For example, if you are using Amazon EC2 and you create a virtual machine in a blueprint, you might expect to see the Amazon resource type `IBM::EC2::Server` in the blueprint. Instead, the blueprint designer creates a resource of the core OpenStack resource type `OS::Nova::Server`.

The blueprint designer uses core OpenStack resource types for portability. You later use a configuration file to map the core OpenStack types to cloud-specific types for your target cloud. You can also create resources from cloud-specific types in a blueprint, but in this case you must write the blueprint code manually.

Therefore, most resource types have two types of properties:

-   Core properties that are inherited from the core OpenStack Heat resource type. Not all of these inherited properties are implemented in the cloud-specific types. See the individual topics about the custom types for details about which properties are implemented.
-   Extended properties that are defined on the cloud-specific type that is provided by HCL UrbanCode Deploy. When you map the resource in the blueprint to a cloud-specific resource type, these properties are applied to that cloud-specific resource type.

Properties are identified as core or extended in the reference information for each resource type.

Resources also have attributes, which are output values that can be referenced from other places.

For example, assume that you connect to Amazon and create a server in a blueprint. The blueprint designer creates a resource of the type `OS::Nova::Server`, as in the following code:

```
resources:
  MyVirtualImage:
    type: OS::Nova::Server
    properties:
      name: MyVirtualImage
      image: "ami-06c4cb11" # ubuntu/images/hvm-ssd/ubuntu-yakkety-16.10-amd64-server-20161214
      flavor: { get_param: flavor }
      key_name: { get_param: key_name }
      availability_zone: { get_param: availability_zone }
      metadata: 
        "__os_type__" : "Linux"
```

You can add both core and extended properties to the resource here, but the properties must be in the appropriate place.

Core properties go in the main `properties` section. For example, the previous example code includes the core properties name, image, flavor, key\_name, and availability\_zone. More information about these properties and other core properties is available in the reference information for the resource type: [IBM::EC2::Server](res_ibm_ec2_server.md).

Extended properties go in the `metadata` section, in a subsection that is named for the target cloud. For example, the Amazon resource type `IBM::EC2::Server` has the extended property subnet\_id, so you can add that property to the `metadata/ec2_properties` metadata section, as in the following example:

```
resources:
  MyVirtualImage:
    type: OS::Nova::Server
    properties:
      name: MyVirtualImage
      image: "ami-06c4cb11" # ubuntu/images/hvm-ssd/ubuntu-yakkety-16.10-amd64-server-20161214
      flavor: { get_param: flavor }
      key_name: { get_param: key_name }
      availability_zone: { get_param: availability_zone }
      metadata: 
        "__os_type__" : "Linux"
 **       ec2\_properties:
          subnet\_id: \{ get\_param: mySubnet \}**
```

Each type of non-OpenStack target cloud has a different metadata section for its extended properties:

-   Amazon EC2: `metadata/ec2_properties`
-   SoftLayer: `metadata/softlayer_properties`
-   VMware vCenter: `metadata/vmware_properties`
-   VMware vRealize Automation: `metadata/vra_properties`
-   Microsoft Azure: `metadata/azure_properties`
-   Google Cloud: `medata/google_properties`

For examples of blueprints, see [Modeling environments for clouds through OpenStack Heat](../../com.ibm.edt.doc/topics/blueprint_edit_clouds.md).

**Parent topic:** [Heat resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_ov.md)

