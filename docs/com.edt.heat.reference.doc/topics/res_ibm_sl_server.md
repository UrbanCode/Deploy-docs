# IBM::SoftLayer::Server

This resource type represents a server on SoftLayer. It extends the type OS::Nova::Server.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_pass|String|False|Core|The administrator password for the SoftLayer server.|
|admin\_user|String|False|Core|Name of the administrative user to use on the SoftLayer server. This property will be removed from Juno in favor of the default cloud-init user that is set up for each image \(for example, "ubuntu" for Ubuntu 12.04+, "fedora" for Fedora 19+ and "cloud-user" for CentOS/Red Hat Enterprise Linux 6.5\).|
|availability\_zone|String|False|Core|Name of the availability zone for SoftLayer server placement.|
|block\_device\_mapping|List|False|Core|Block device mappings for this SoftLayer server. This property is not used; it is in the type for portability.|
|block\_device\_mapping\_v2|List|False|Core|Block device mappings for this SoftLayer server. This property is not used; it is in the type for portability.|
|config\_drive|String|False|Core|Value for config drive either `boolean`, or `volume-id`.|
|datacenter|String|False|Extended|Specify the short name of the data center in which the server resides.|
|dedicated|Boolean|False|Extended|Specify False \(the default\) to provision the SoftLayer server on a shared host. Specify True to provision the server on a dedicated host, with an additional fee.|
|diskConfig|String|False|Core|Controls how the disk is partitioned when the server is created. Valid values are `AUTO` and `MANUAL`.|
|disk\_type|String|False|Extended|Specify if the SoftLayer server uses a local disk or SAN.|
|disks|String \(array\)|False|Extended|The number of additional disks to add to the server. When the disk\_type parameter is set to `SAN`, you can add up to four additional SAN disks by specifying the following sizes, in gigabytes: `10`, `20`,`25`, `30`, `40`, `50`,`75`, `100`, `125`, `150`, `175`, `200`, `250` ,`300`, `350`, `400`, `500`, `750`, `1000`, `1500`, or `2000`. When the disk\_type parameter is not set to `SAN`, you can add one additional disk by specifying the following sizes, in gigabytes: `25`, `100`, `150`, `200`, or `300`.

|
|domain|String|False|Extended|The device domain.|
|flavor|String|True|Core|The ID or name of the flavor to boot onto.|
|flavor\_update\_policy|String|False|Core|Policy governing how to apply a flavor update; either by requesting a server resize or by replacing the entire SoftLayer server. Valid values are `RESIZE` and `REPLACE`.|
|hourly|Boolean|False|Extended|Specify True \(the default\) to use an hourly billing interval, or False to use a monthly billing interval.|
|image|String|False|Core|The ID or name of the image to boot with.|
|image\_update\_policy|String|False|Core|Policy governing how to apply an image-id update; either by requesting a server rebuild or by replacing the entire SoftLayer server. Valid values are -   `REPLACE` \(the default\)
-   `REBUILD`
-   `REBUILD_PRESERVE_EPHEMERAL`

|
|key\_name|String|False|Core|Name of key pair to inject into the SoftLayer server.|
|metadata|Map|False|Core|Arbitrary key/value metadata to store for this SoftLayer server. Both keys and values must be 255 characters or less. Non-string values are serialized to JSON \(and the serialized string must be 255 characters or less\).|
|name|String|False|Core|SoftLayer server name.|
|networks|List|False|Core|An ordered list of NICs to be added to this SoftLayer server, with information about connected networks, fixed IP addresses, and ports.|
|nic\_speed|Integer|False|Extended|The port speed to set. Valid values are 10, 100, or 1000. The default value is 100.|
|personality|Map|False|Core|A map of files to create or overwrite on the SoftLayer server at boot time. Keys are file names and values are the file contents.|
|private\_vlan|String|False|Extended|The private network VLAN id.|
|port\_speed|Integer|False|Extended|Port speed in Mbps.|
|public\_vlan|String|False|Extended|The public network VLAN id.|
|reservation\_id|String|False|Core|A UUID for the set of SoftLayer servers requested.|
|scheduler\_hints|String|False|Core|Arbitrary key-value pairs that are specified by the client to help boot a SoftLayer server.|
|security\_groups|List|False|Core|List of security group names or IDs. Cannot be used if Neutron ports are associated with this SoftLayer server; assign security groups to the ports instead.|
|software\_config\_transport|String|False|Core|Specifies how the SoftLayer server receives the metadata that is required for software configuration. `POLL_SERVER_CFN` allows calls to the Cloud Formation API action DescribeStackResource authenticated with the provided key pair. `POLL_SERVER_HEAT` allows calls to the Heat API action resource-show by using the provided keystone credentials.|
|storage\_account|String|False|Extended|The object storage account.|
|storage\_datacenter|String|False|Extended|The datacenter to locate the object storage account in.|
|storage\_private\_url|Boolean|False|Extended|Specify the provision script URL.|
|use\_cloudinit|Boolean|False|Extended|Specify True \(the default\) to use cloud-init for script provisioning or False to not use cloud-init|
|user\_data|String|False|Core|User data script to be run by cloud-init.|
|user\_data\_format|String|False|Core|How the user\_data is formatted for the SoftLayer server. For `HEAT_CFNTOOLS`, the user\_data is bundled as part of the `heat-cfntools cloud-init` boot configuration data. For `RAW`, the `user_data` is passed to Nova unmodified. For `SOFTWARE_CONFIG`, the `user_data` is bundled as part of the software configuration data, and metadata is derived from any associated SoftwareDeployment resources.|

|Name|Description|
|----|-----------|
|accessIPv4|The manually assigned alternative public IPv4 address of the SoftLayer server.|
|accessIPv6|The manually assigned alternative public IPv6 address of the SoftLayer server.|
|addresses|A dict of all network addresses with corresponding port\_id values.|
|console\_urls|URLs of server's consoles. To get a specific console type, the requested type can be specified as parameter to the `get_attr` function,as shown in the following code: `get_attr: [ server, console_urls, novnc ]`. The following types are allowed:-   `novnc`
-   `xvpvnc`
-   `spice-html5`
-   `rdp-html5`
-   `serial`

|
|domain\_name|Server domain name.|
|first\_address|A convenience attribute to fetch the first assigned network address or an empty string if nothing is assigned. The result might not be predictable if the SoftLayer server has addresses from more than one network.|
|host\_name|Server host name.|
|instance\_name|The AWS compatible instance name.|
|name|The name of the SoftLayer server.|
|networks|A dict of assigned network addresses of the form: `{\"public\": [ip1, ip2...], \"private\": [ip3, ip4]}`.|
|passwords|The user and passwords of the SoftLayer VM.|
|post\_script\_uri|Post script URI.|
|show|A dict of all SoftLayer server details as returned by the API.|
|uuid|The UUID of the virtual machine.|

**Parent topic:** [SoftLayer resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_sl_ov.md)

