# IBM::Azure::Disk

This type represents a Microsoft™ Azure disk. It can create a managed disk or copy, import, or snapshot an existing disk.

This resource type extends the OpenStack resource type `OS::Cinder::Volume`.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|creation\_option|String|True|Extended|How to create or access the disk. Valid values are:-   `Empty`
-   `Attach`
-   `FromImage`
-   `Import`
-   `Copy`
-   `Restore`

|
|description|tring|False|Extended|A description of the disk.|
|name|String|True|Core|The name of the managed disk.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|resource\_group\_name|String|True|Extended|The name of the resource group.|
|size|String|True|Core|The size of the disk in GB.|
|source\_resource\_id|String|False|Extended|If createOption is `Copy`, this is the ARM ID of the source snapshot or disk. If creationOption is `Restore`, this is the ARM-like ID of the source disk restore point.|
|source\_uri|String|False|Extended|If creationOption is `Import`, this is a URI to a blob to be imported into a managed disk. If creationOption is `Copy`, this is a relative URI containing the ID of the source snapshot to be copied into a managed disk|
|volume\_type|String|True|Core|The type of disk. Valid values are `SSD` and `HDD`.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The name of the disk.|
|show|String|The details of the disk.|
|source\_volid|String|The ID of the disk.|

## Example

This example creates an empty disk:

```
  storage-volume_empty:
    type: OS::Cinder::Volume
    properties:
      name: storagevolumeempty
      size: 2
      volume_type: "ssd"
    metadata:
      azure_properties:
        resource_group: { get_param: resource_group }
        creation_option: "Empty"
```

This example copies an existing disk:

```
  storage-volume_import:
    type: OS::Cinder::Volume
    properties:
      name: storagevolumeimport
      size: 40
      volume_type: "hdd"
    metadata:
      azure_properties:
        resource_group: { get_param: resource_group }
        creation_option: "Copy"
        source_resource_id: "/subscriptions/SUBSCRIPTION/resourceGroups/CUSTOMIMAGE/providers/Microsoft.Compute/disks/DISK_NAME"
```

This example creates a disk from a snapshot:

```
  storage-volume_snapshot:
    type: OS::Cinder::Volume
    properties:
      name: storagevolumesnapshot
      size: 30
      volume_type: "hdd"
    metadata:
      azure_properties:
        resource_group: { get_param: resource_group }
        creation_option: "Copy"
        source_uri: "/subscriptions/SUBSCRIPTION/resourceGroups/RESOURCE_GROUP/providers/Microsoft.Compute/snapshots/MY_SNAPSHOT" 
```

This example imports a disk:

```
  storage-volume_copy:
    type: OS::Cinder::Volume
    properties:
      name: storagevolumecopy
      size: 30
      volume_type: "hdd"
    metadata:
      azure_properties:
        resource_group: { get_param: resource_group }
        creation_option: "Import"
        source_uri: "https://blob.core.windows.net/vhds/jkedbaf7ef5.vhd"
```

**Parent topic:** [Microsoft Azure resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

