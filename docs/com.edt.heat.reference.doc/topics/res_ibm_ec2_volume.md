# IBM::EC2::Volume

This resource type represents a volume on Amazon Elastic Compute Cloud. It extends the type OS::Cinder::Volume.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|availability\_zone|String|False|Core|The availability zone in which to create the volume.|
|backup\_id|String|False|Core|If specified, the backup from which to create the volume.|
|description|String|False|Core|Description of the volume.|
|encrypted|Boolean|False|Extended|Specify True to encrypt the volume.|
|image|String|False|Core|The name or ID of the image from which to create the volume.|
|imageRef|String|False|Core|ID of the image from which to create the volume.|
|iops|Integer|False|Extended|The number of I/O operations per second \(IOPS\) that the volume supports. Use with vol type io1.|
|metadata|String|False|Core|Key/value pairs to associate with the volume.|
|master\_key|String|False|Extended|The Amazon Resource Name \(ARN\) of the AWS Key Management Service master key that is used to create the encrypted volume.|
|name|String|False|Core|Name of the volume.|
|size|Number|False|Core|Size of the volume in GB.|
|snapshot\_id|String|False|Core|The snapshot from which to create the volume.|
|source\_volid|String|False|Core|The volume to use as a source.|
|volume\_type|String|False|Core|The type of volume to use. The volume type is mapped to a specific back end.|

|Name|Description|
|----|-----------|
|availability\_zone|The availability zone in which the volume is located.|
|bootable|A Boolean value that indicates if the volume can be booted or not.|
|created\_at|The time stamp that indicates volume creation.|
|create\_time|The time that this volume was created.|
|display\_description|The description of the volume.|
|display\_name|The name of this volume.|
|encrypted|The value is `true` if this volume is encrypted.|
|id|The ID of this volume.|
|iops|The I/O operations that this volume can support.|
|metadata|The key/value pairs that are associated with the volume.|
|metadata\_values|The key/value pairs that are associated with the volume in raw dict form.|
|region|The region of this volume.|
|size|The size of the volume in GB.|
|snapshot\_id|The snapshot the volume was created from, if any.|
|source\_volid|The volume that is used as source, if any.|
|status|The current status of the volume.|
|type|The type of this volume.|
|volume\_type|The type of the volume mapping to a back end, if any.|
|zone|The availability zone of this volume.|

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

