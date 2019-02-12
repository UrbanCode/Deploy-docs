# IBM::VCenter::VolumeAttachment

This resource type represents a volume attachment on VMware vCenter. It extends the type OS::Cinder::VolumeAttachment.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|instance\_uuid|String|True|Core|The ID of the server to which the volume attaches.|
|mountpoint|String|False|Core|Location where the volume is exposed on the instance. This assignment is not necessarily accepted. Alternately, use the path /dev/disk/by-id/virtio-VolumeID as the mount point.|
|volume\_id|String|False|Core|ID of the volume to attach.|
|volume\_type|String|False|Extended| -   Thick
-   Thin

 |

This resource type has no attributes.

**Parent topic:** [VMware vCenter resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_vc_ov.md)

