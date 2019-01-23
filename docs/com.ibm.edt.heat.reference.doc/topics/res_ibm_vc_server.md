# IBM::VCenter::Server

This resource type represents a server on VMware vCenter. It extends the type OS::Nova::Server.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_pass|String|False|Core|The administrator password for the vCenter server.|
|admin\_user|String|False|Core|Name of the administrative user to use on the vCenter server. This property will be removed from Juno in favor of the default cloud-init user that is set up for each image \(for example, "ubuntu" for Ubuntu 12.04+, "fedora" for Fedora 19+ and "cloud-user" for CentOS/Red Hat Enterprise Linux 6.5\).|
|availability\_zone|String|False|Core|Name of the availability zone for vCenter server placement.|
|block\_device\_mapping|List|False|Core|Block device mappings for this vCenter server.|
|block\_device\_mapping\_v2|List|False|Core|Block device mappings for this vCenter server.|
|cluster|String|False|Extended|The cluster to put the VM in.|
|config\_drive|String|False|Core|Value for config drive either `boolean`, or `volume-id`.|
|customization\_spec|String|False|Extended|The customization specification of the virtual machine. The information is set in the vSphere environment.|
|datastore|String|False|Extended|The datastore to put the VM in.|
|destination\_folder|String|False|Core|The folder to put the image in on the vCenter server.|
|destination\_folder|String|False|Extended|The destination folder to put the VM in.|
|diskConfig|String|False|Extended|Controls how the disk is partitioned when the vCenter server is created. Valid values are `AUTO` and `MANUAL`.|
|disk\_type|String|False|Core|Defines the vm disk type as thick or thin.|
|flavor|String|True|Core|The ID or name of the flavor to boot onto.|
|flavor\_update\_policy|String|False|Core|Policy governing how to apply a flavor update; either by requesting a server resize or by replacing the entire vCenter server. Valid values are `RESIZE` and `REPLACE`.|
|image|String|False|Core|The ID or name of the image to boot with.|
|image\_update\_policy|String|False|Core|Policy governing how to apply an image-id update; either by requesting a server rebuild or by replacing the entire vCenter server. Valid values are -   `REPLACE` \(the default\)
-   `REBUILD`
-   `REBUILD_PRESERVE_EPHEMERAL`

|
|key\_name|String|False|Core|Name of key pair to inject into the vCenter server.|
|metadata|Map|False|Core|Arbitrary key/value metadata to store for this vCenter server. Both keys and values must be 255 characters or less. Non-string values are serialized to JSON \(and the serialized string must be 255 characters or less\).|
|name|String|False|Core|vCenter server name.|
|networks|List|False|Core|An ordered list of NICs to be added to this vCenter server, with information about connected networks, fixed IP addresses, and ports.|
|personality|Map|False|Core|A map of files to create or overwrite on the vCenter server at boot time. Keys are file names and values are the file contents.|
|reservation\_id|String|False|Core|A UUID for the set of vCenter servers requested.|
|resource\_pool|String|False|Extended|The resource pool to put the VM in.|
|scheduler\_hints|Map|False|Core|Arbitrary key-value pairs that are specified by the client to help boot a vCenter server.|
|security\_groups|List|False|Core|List of security group names or IDs. Cannot be used if Neutron ports are associated with this vCenter server; assign security groups to the ports instead.|
|software\_config\_transport|String|False|Core|Specifies how the vCenter server receives the metadata that is required for software configuration. `POLL_SERVER_CFN` \(the default\) allows calls to the Cloud Formation API action DescribeStackResource authenticated with the provided key pair. `POLL_SERVER_HEAT` allows calls to the Heat API action resource-show by using the provided keystone credentials.|
|ssh\_key|String|False|Extended|The path to an SSH private key to authenticate with.|
|ssh\_username|String|False|Extended|The user used to ssh into the vCenter server.|
|subnet\_id|String|False|Extended|The subnet to launch the instance in.|
|user\_data|String|False|Core|User data script to be run by cloud-init.|
|user\_data\_format|String|False|Core|How the user\_data is formatted for the vCenter server. For `HEAT_CFNTOOLS` \(the default\), the user\_data is bundled as part of the `heat-cfntools cloud-init` boot configuration data. For `RAW`, the `user_data` is passed to Nova unmodified. For `SOFTWARE_CONFIG`, the `user_data` is bundled as part of the software configuration data, and metadata is derived from any associated SoftwareDeployment resources.|

|Name|Description|
|----|-----------|
|accessIPv4|The manually assigned alternative public IPv4 address of the vCenter server.|
|accessIPv6|The manually assigned alternative public IPv6 address of the vCenter server.|
|addresses|A dict of all network addresses with corresponding port\_id values.|
|first\_address|A convenience attribute to fetch the first assigned network address or an empty string if nothing is assigned. The result might not be predictable if the vCenter server has addresses from more than one network.|
|console\_urls|URLs of a server's consoles. To get a specific console type, the requested type can be specified as a parameter to the `get_attr` function, e.g. `get_attr: [server, console_urls, novnc`. Currently supported types are `novnc`, `xvpvnc`, `spice-html5`, `rdp-html5`, and `serial`.|
|instance\_name|The AWS compatible instance name.|
|name|The name of the vCenter server.|
|networks|A dict of assigned network addresses of the form: `{\"public\": [ip1, ip2...], \"private\": [ip3, ip4]}`.|
|show|A dict of all vCenter server details as returned by the API.|

**Parent topic:** [VMware vCenter resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_vc_ov.md)

