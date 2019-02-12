# IBM::Azure::DiskAttachment

This type represents the connection from a Microsoft™ Azure virtual machine to a disk.

This resource type extends the OpenStack resource type `OS::Cinder::VolumeAttachment`.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|mode|String|False|Core|The read/write mode of the attached disk. Valid values are `READ_ONLY` and `READ_WRITE`.|
|resource\_group\_name|String|True|Extended|The name of the resource group.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The name of the disk attachment.|

## Example

```
  storage-volume__attachment:
    type: OS::Cinder::VolumeAttachment
    properties:
      volume_id: { get_resource: azure-storage-volume }
      instance_uuid: { get_resource: my_azure_server}
    metadata:
      azure_properties:
        resource_group: { get_param: resource_group }
        mode: READ_WRITE
  
my_azure_server
    type: OS::Nova::Server
    properties:
      metadata: 
        "__os_type__" : "Linux"
    metadata:
      azure_properties:
        use_cloudinit: False
        storage_account: { get_param: storage_account }
        resource_group: { get_param: resource_group }
        use_managed_disk: True
        volume_type: ssd
  
  azure-storage-volume:
    type: OS::Cinder::Volume
    properties:
      name: storagevolumecopy
      size: 30
      volume_type: "hdd"
    metadata:
      azure_properties:
        resource_group: { get_param: resource_group }
        creation_option: "Empty"

```

**Parent topic:** [Microsoft Azure resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

