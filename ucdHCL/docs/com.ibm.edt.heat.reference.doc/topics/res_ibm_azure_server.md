# IBM::Azure::Server

This resource type represents a server on an Microsoft Azure virtual machine.

This resource type extends the OpenStack resource type `OS::Nova::Server`.

Beginning in version 6.2.5, you can create virtual machines from public \(marketplace\) images and private \(VHD\) images, with both managed and unmanaged OS disks. When using managed disks on the OS, you can also attach managed data disks.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_user |String|False|Core|The name of the administrative user to use on the server. This property will be removed from Juno in favor of the default `cloud-init` user set up for each image \(for example, `\"ubuntu\"` for Ubuntu 12.04+, `\"fedora\"` for Fedora 19+, and `\"cloud-user\"` for CentOS/RHEL 6.5\).|
|admin\_pass|String|False|Core|The administrator password for the server.|
|availability\_set |String|False|Extended|The name of the availability set to which the virtual machine belongs.|
|boot\_diagnostic\_storage\_uri|String|False|Extended|The blob endpoint for the storage account to hold the virtual machine's diagnostic files, which must be the root of a storage account and not a storage container.|
|disk\_size|Integer|False|Extended|The disk size, in GB, of the base disk of the instance.|
|flavor|String|True|Core|The name of a virtual machine size in Azure, such as `DS1_standard`.|
|image|String|True|Core|The ID of the image to create a virtual machine from. This image can be a public \(marketplace\) image or a private image \(VHD\) from an Azure storage account.|
|key\_name|String|False|Core|Specifies an SSH key to be placed on the virtual machine.|
|metadata|Map|False|Core|Arbitrary key-value metadata to store for this server. Both keys and values must be 255 characters or fewer. Nonstring values are serialized to JSON \(and the serialized string must be 255 characters or fewer\).|
|name|String|True|Core|The name of the virtual machine. If the specified name exists, a new unique name is created.|
|networks|List|False|Core|List of network attachments for the virtual machine. See [Table 2](#networks).|
|os\_disk\_name|String|False|Extended|The name of the operating system disk to create for the virtual machine.|
|preserve\_os\_disk|Boolean|False|Extended|Specify False to delete the operating system disk when the virtual machine is deleted. The default \(True\) preserves the disk.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|resource\_group\_name|String|True|Extended|The resource group name.|
|storage\_account\_name|String|True|Extended|The storage account name for storing the OS disk and optional script provisioning content.|
|tags|List|False|Extended|A list of name-value pairs to set as tags on the resource.|
|use\_boot\_diagnostic|Boolean|False|Extended|Enables boot diagnostics for the virtual machine.|
|use\_cloudinit|Boolean|False|Extended|Specify False to use the Azure default tools to install the HCL® UrbanCode™ Deploy agent. Specify True to use the `cloud-init` package instead. The default is False for Azure Marketplace images and True for custom images.|
|use\_managed\_disk|Boolean|False|Extended|By default, an un-managed disk is used. Specify True to use a managed disk for the operating system disk.|
|user\_data|String|False|Core|User data script that the cloud-init command runs.|
|user\_data\_format|String|False|Core|How to format the user data for the server. For the `RAW` value, the user data is passed to Nova unmodified. For the `SOFTWARE_CONFIG` value, user data is bundled as part of the software config data, and metadata is derived from any associated SoftwareDeployment resources. Valid values are as follows:-   `RAW` \(default\)
-   `SOFTWARE_CONFIG`

 |
|volume\_type|String|False|Extended|The disk type for the operating system disk on the virtual machine. Valid values are `hdd` \(the default\) and `ssd`.|

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|port|String|False|The network interface to attach to this virtual machine.|

|Attribute|Type|Description|
|---------|----|-----------|
|first\_address|String|The private IP address of the network interace of the virtual machine.|
|name|String|The name of the virtual machine.|
|os\_disk|String|The name of the operating system disk of the virtual machine.|

## Examples

This example creates a virtual machine from the resource ID of a generalized image.

```
 myserver:
    type: OS::Nova::Server
    properties:
      networks:
          - port: { get_resource: Ubuntu_Server_14_04_4-LTS__to__vnet__port  }
      name: "server1"
      image: "/subscriptions/YOUR_SUBSCRIPTION/resourceGroups/customImage/providers/Microsoft.Compute/images/IMAGE_NAME"
      flavor: { get_param: flavor }
      admin_user: { get_param: admin_user }
      admin_pass: { get_param: admin_pass }
      availability_zone: { get_param: availability_zone }
      metadata: 
        "__os_type__" : "Linux"
    metadata:
      azure_properties:
        use_cloudinit: False
        storage_account: { get_param: storage_account }
        resource_group: { get_param: resource_group }
        use_managed_disk: True
        volume_type: ssd
```

This example creates a server with properties.

```
 ServerName:
    type: OS::Nova::Server
    properties:
      user_data: ...
      user_data_format: ...      
    metadata:
      azure_properties:
        boot_diagnostic_storage_uri: 'https://storage_account_endpoint/'
        use_boot_diagnostic: False
        disk_size: 15
```

**Parent topic:** [Microsoft Azure resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

