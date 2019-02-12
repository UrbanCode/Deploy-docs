# IBM::S3::Bucket

This resource type represents an Amazon Simple Storage Service \(S3\) bucket of files.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|name|String|False|Core|The name for the container. If this property is not specified, a unique name is generated at provisioning time.|
|X-Account-Meta|Map|False|Core|A map of user-defined meta data to associate with the account. Each key in the map sets the header `X-Account-Meta-{key}` with the corresponding value.|
|X-Container-Meta|Map|False|Core|A map of user-defined metadata to associate with the container. Each key in the map will set the header `X-Container-Meta-{key}` with the corresponding value.|
|X-Container-Read|String|False|Core|The ACL permissions that specify who can read objects in the container.|
|X-Container-Write|String|False|Core|The ACL permissions that specify who can write to objects in the container.|

|Name|Description|
|----|-----------|
|BucketName|The name of the bucket.|
|BytesUsed|The number of bytes that the container uses.|
|DomainName|The host name from the bucket URL.|
|ObjectCount|The number of objects that are in the container.|
|RootURL|The parent URL of the bucket.|
|WebsiteURL|The fully qualified hostname to access this bucket as a web site.|

**Parent topic:** [Amazon S3 resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_s3_ov.md)

