# IBM::Google::DiskAttachment

This resource type represents a disk attachment on Google Cloud Platform.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|availability\_zone|String|False|Extended|Availability zone of resources.|
|instance\_uuid|String|True|Core|The ID of the server to which the volume attaches.|
|mode|String|False|Extended|Read/write mode of the attached disk. The following values are allowed:-   
 Must be READ\_ONLY or READ\_WRITE.|
|mountpoint|String|False|Core|The location where the volume is exposed on the instance. This assignment may not be honored and it is advised that the path /dev/disk/by-id/virtio-VolumeId be used instead.|
|volume\_id|String|False|Core|The ID of the associated volume.|

This resource type has no attributes.

**Parent topic:** [Google Cloud Platform resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_gc_ov.md)

