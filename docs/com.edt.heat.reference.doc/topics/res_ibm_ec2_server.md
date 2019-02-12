# IBM::EC2::Server

This resource type represents a server on Amazon Elastic Compute Cloud. It extends the type OS::Nova::Server.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_pass|String|False|Core|The administrator password for the server.|
|admin\_user|String|False|Core|Name of the administrative user to use on the server. This property will be removed from Juno in favor of the default cloud-init user that is set up for each image \(for example, "ubuntu" for Ubuntu 12.04+, "fedora" for Fedora 19+ and "cloud-user" for CentOS/Red Hat Enterprise Linux 6.5\).|
|availability\_zone|String|False|Core|Name of the availability zone for server placement.|
|block\_device\_mapping|List|False|Core|Block device mappings for this server. See [Table 2](#block_device_mapping).|
|config\_drive|String|False|Core|value for config drive either `boolean`, or `volume-id`.|
|disable\_source\_dest\_check|Boolean|False|Extended|Set to True to disable Source/Destination Check on instance. Use for NAT instances.|
|diskConfig|String|False|Core|Control how the disk is partitioned when the server is created. Valid values are `AUTO` and `MANUAL`.|
|flavor|String|True|Core|The ID or name of the flavor to boot onto.|
|flavor\_update\_policy|String|False|Core|Policy on how to apply a flavor update; either by requesting a server resize or by replacing the entire server. Valid values are `RESIZE` and `REPLACE`.|
|image|String|False|Core|The ID or name of the image to boot with.|
|image\_update\_policy|String|False|Core|Policy on how to apply an image-id update; either by requesting a server rebuild or by replacing the entire server. Valid values are -   `REPLACE` \(the default\)
-   `REBUILD`
-   `REBUILD_PRESERVE_EPHEMERAL`

|
|key\_name|String|False|Core|Name of key pair to inject into the server.|
|metadata|Map|False|Core|Arbitrary key/value metadata to store for this server. Both keys and values must be 255 characters or less. Non-string values are serialized to JSON \(and the serialized string must be 255 characters or less\).|
|name|String|False|Core|Server name.|
|nat\_routetable|String|False|Extended|Route table in which to create a route for all traffic for this instance. Use for NAT instances.|
|networks|List|False|Core|An ordered list of NICs to be added to this server, with information about connected networks, fixed IP addresses, and ports. See [Table 3](#networks).|
|personality|Map|False|Core|A map of files to create/overwrite on the server at boot time. Keys are file names and values are the file contents.|
|reservation\_id|String|False|Core|A UUID for the set of servers requested.|
|scheduler\_hints|String|False|Core|Arbitrary key-value pairs that are specified by the client to help boot a server.|
|security\_groups|List|False|Core|List of security group names or IDs. Cannot be used if neutron ports are associated with this server; assign security groups to the ports instead.|
|software\_config\_transport|String|False|Core|Specifies how the server receives the metadata that is required for software configuration. `POLL_SERVER_CFN` allows calls to the Cloud Formation API action DescribeStackResource authenticated with the provided key pair. `POLL_SERVER_HEAT` allows calls to the Heat API action resource-show by using the provided keystone credentials.|
|subnet\_id|String|False|Extended|The subnet to launch the instance in.|
|user\_data|String|False|Core|User data script to be run by cloud-init.|
|user\_data\_format|String|False|Core|How the user\_data is formatted for the server. For `HEAT_CFNTOOLS`, the user\_data is bundled as part of the `heat-cfntools cloud-init` boot configuration data. For `RAW` the `user_data` is passed to Nova unmodified. For `SOFTWARE_CONFIG` the `user_data` is bundled as part of the software configuration data, and metadata is derived from any associated SoftwareDeployment resources.|

The block\_device\_mapping parameter requires a list of storage volume mappings for the server. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|delete\_on\_termination|Boolean|False|Indicates whether the volume is deleted when the server is stopped.|
|device\_name|String|True|A device name where the volume is attached in the system at /dev/device\_name. This value is typically `vda`.|
|snapshot\_id|String|False|The ID of the snapshot to create a volume from.|
|volume\_id|String|False|The ID of the volume to boot from. Provide either the volume\_id property or the snapshot\_id property but not both.|
|volume\_size|Integer|False|The size of the volume, in GB. You can leave this property blank and have the Compute service infer the size.|

The networks parameter requires a list of NICs for the server. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|fixed\_ip|String|False|Fixed IP address to specify for the port that is created on the requested network|
|network|String|False|Name or ID of network to create a port on.|
|port|String|False|ID of an existing port to associate with this server.|
|uuid|String|False|ID of network to create a port on.|

|Name|Description|
|----|-----------|
|accessIPv4|The manually assigned alternative public IPv4 address of the server.|
|accessIPv6|The manually assigned alternative public IPv6 address of the server.|
|addresses|A dict of all network addresses with corresponding port\_id values.|
|first\_address|A convenience attribute to fetch the first assigned network address, or an empty string if nothing is assigned. Result might not be predictable if the server has addresses from more than one network.|
|id|The ID of the instance.|
|instance\_name|An AWS compatible instance name.|
|name|The name of the server.|
|networks|A dict of assigned network addresses of the form: `{\"public\": [ip1, ip2...], \"private\": [ip3, ip4]}`.|
|private\_dns\_name|The private DNS name of the instance.|
|public\_dns\_name|The public DNS name of the instance.|
|public\_ip\_address|A convenience attribute to fetch the public IP address or an empty string if nothing is assigned.|
|show|A dict of all server details as returned by the API.|

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

