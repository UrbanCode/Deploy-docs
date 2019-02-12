# IBM::EC2::VolumeAttachment

This resource type represents a volume attachment on Amazon Elastic Compute Cloud \(EC2\). It extends the type OS::Cinder::VolumeAttachment.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|instance\_uuid|String|True|Core|ID of the EC2 server to which the volume attaches.|
|mountpoint|String|False|Core|Location where the volume is exposed on the instance. This assignment is not necessarily accepted. Alternately, use the path /dev/disk/by-id/virtio-VolumeID as the mount point.|
|volume\_id|String|True|Core|ID of the volume to attach.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

