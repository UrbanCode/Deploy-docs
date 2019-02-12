# IBM::Google::Disk

This resource type represents a disk on a Google Cloud Platform image.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|availability\_zone |String|False|Core|The availability zone in which the volume is created.|
|backup\_id |String|False|Core|If specified, the backup to create the volume from.|
|description |String|False|Core|A description of the volume.|
|encrypted |String|False|Extended| |
|iops |String|False|Extended| |
|image |String|False|Core|The image name.|
|imageRef |String|False|Core|The ID of the image to create the volume from.|
|master\_key |String|False|Extended| |
|metadata |Map|False|Core|Key/value pairs to associate with the volume.|
|name |String|False|Core|A name that is used to distinguish the volume.|
|scheduler\_hints |Map|False|Core|Arbitrary key-value pairs that are specified by the client to help the Cinder scheduler create a volume.|
|size|String|False|Core|The size of the volume in GB. On update, only increase in size is supported.|
|snapshot\_id |String|False|Core|The snapshot the volume was created from, if any.|
|source\_volid |String|False|Core|The volume that was used as source, if any.|
|volume\_type |String|False|Core|The type of the volume mapping to a backend, if any.|

|Name|Description|
|----|-----------|
|attachments|The list of attachments of the volume.|
|availability\_zone|The availability zone in which the volume is located.|
|bootable|Boolean indicating if the volume can be booted or not.|
|created\_at|The time stamp that indicates volume creation.|
|display\_description|Description of the volume.|
|display\_name|Name of the volume.|
|encrypted|Boolean indicating whether the volume is encrypted or not.|
|metadata|Key/value pairs that are associated with the volume.|
|metadata\_values|Key/value pairs that are associated with the volume in raw dict form.|
|name|Disk name.|
|self\_link|Server-defined URL for this resource.|
|show|Show details of the disk.|
|size|The size of the volume in GB.|
|snapshot\_id|The snapshot the volume was created from, if any.|
|source\_volid|The volume that is used as source, if any.|
|status|The current status of the volume.|
|volume\_type|The type of the volume mapping to a backend, if any.|

**Parent topic:** [Google Cloud Platform resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_gc_ov.md)

