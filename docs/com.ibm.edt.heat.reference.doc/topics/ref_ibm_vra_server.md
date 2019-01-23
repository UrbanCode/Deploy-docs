# IBM::VRA::Server

These Heat resource types represent elements on VMware vRealize Automation. These types are discovered from vRealize Automation and are the results of data collection from the defined reservations and endpoints. HCL® UrbanCode™ Deploy supports VMware vCenter integration for this release. The templates are represented in the palette.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|action|String|False|Extended|The provisioning action.|
|admin\_pass|String|False|Core|The administrator password for the server.|
|admin\_user|String|False|Core|Name of the administrative user to use on the vCenter server. This property is removed from Juno in favor of the default cloud-init user that is set up for each image \(for example, "Ubuntu" for Ubuntu 12.04+, "fedora" for Fedora 19+ and "cloud-user" for CentOS/Red Hat Enterprise Linux 6.5\).|
|availability\_zone|String|False|Core|Name of the availability zone for server placement.|
|block\_device\_mapping|List|False|Core|Block device mappings for this vCenter server.|
|block\_device\_mapping\_v2|List|False|Core|Block device mappings for this vCenter server.|
|config\_drive|Boolean|False|Core|If `True`, enable config drive on the server.|
|cpu|Integer|False|Extended|The number of processors on the virtual machine.|
|customization\_spec|String|False|Extended|The customization specification of the virtual machine. The information is set in the vSphere environment.|
|disk\_config|String|False|Extended|Control how the disk is partitioned when the server is created. Valid values are-   `AUTO`
-   `MANUAL`

|
|flavor|String|False|Core|The ID or name of the flavor to boot onto.|
|flavor\_update\_policy|String|False|Core|Policy on how to apply a flavor update, either by requesting a server resize or by replacing the entire server. Valid values are -   `RESIZE` \(the default\)
-   `REPLACE`

|
|image|String|False|Core|The ID or name of the image to boot with.|
|image\_update\_policy|String|False|Core|Policy governing how to apply an image-id update; either by requesting a server rebuild or by replacing the entire vCenter server. Valid values are -   `REPLACE` \(the default\)
-   `REBUILD`
-   `REBUILD_PRESERVE_EPHEMERAL`

|
|key\_name|String|False|Core|Name of keypair to inject into the server.|
|machine\_prefix|String|False|Extended|The machine prefix of the virtual machine.|
|memory|Integer|False|Extended|The virtual machine memory \(MB\).|
|metadata|Map|False|Core|Arbitrary key/value metadata to store for this server. Both keys and values must be 255 characters or less. Non-string values are serialized to JSON \(and the serialized string must be 255 characters or less\).|
|name|String|False|Core|Server name.|
|networks|List|False|Core|An ordered list of NICs to be added to this vCenter server, with information about connected networks, fixed IP addresses, and ports.|
|personality|Map|False|Core|A map of files to create/overwrite on the server upon boot. Keys are file names and values are the file contents.|
|properties|Map|False|Extended|The custom properties on a vRealize Automation virtual machine|
|provisioning\_workflow|String|False|Extended|The provisioning workflow to run.|
|reservation\_id|String|False|Core|A UUID for the set of servers that are being requested.|
|reservation\_policy|String|False|Extended|The vRealize Automation reservation policy of the virtual machine.|
|security\_groups|List|False|Core|List of security group names or IDs. Cannot be used if neutron ports are associated with this server; assign security groups to the ports instead.|
|scheduler\_hints|Map|False|Core|Arbitrary key-value pairs that are specified by the client to help boot a server.|
|software\_config\_transport|String|False|Core|Specifies how the vCenter server receives the metadata that is required for software configuration. `POLL_SERVER_CFN` \(the default\) allows calls to the Cloud Formation API action DescribeStackResource authenticated with the provided key pair. `POLL_SERVER_HEAT` allows calls to the Heat API action resource-show by using the provided keystone credentials. Valid values are-    `POLL_SERVER_CFN` \(the default\)
-   `POLL_SERVER_HEAT`
-    `POLL_TEMP_URL`

|
|storage|Integer|False|Extended|The virtual machine memory in GB.|
|user\_data|String|False|Core|User data script to be run by cloud-init.|
|user\_data\_format|String|False|Core|How the user\_data is formatted for the vCenter server. For `HEAT_CFNTOOLS` \(the default\), the user\_data is bundled as part of the `heat-cfntools cloud-init` boot configuration data. For `RAW`, the `user_data` is passed to Nova unmodified. For `SOFTWARE_CONFIG`, the `user_data` is bundled as part of the software configuration data, and metadata is derived from any associated SoftwareDeployment resources. Valid values are-    `HEAT_CFNTOOLS` \(the default\)
-   `RAW`
-    `SOFTWARE_CONFIG`

|

|Name|Description|
|----|-----------|
|accessIPv4|The manually assigned alternative public IPv4 address of the server.|
|accessIPv6|The manually assigned alternative public IPv6 address of the server.|
|addresses|A dictionary of all network addresses with corresponding port\_id values.```
"addresses": {"VIS241": 
[{"NETWORK_MAC_ADDRESS":"00:50:56:b6:f4:53","NETWORK_ADD
RESS": "9.37.204.234"}
```

|
|console\_urls|URLs of server's consoles. To get a specific console type, the requested type can be specified as parameter to the `get_attr` function, e.g. `get_attr: [ <server>, console_urls, novnc ]`. Currently supported types are novnc, xvpvnc, spice-html5, rdp-html5, and serial.|
|first\_address|Convenience attribute to fetch the first assigned network address, or an empty string if nothing has been assigned at this time. Result may not be predictable if the server has addresses from more than one network.|
|instance\_name|The VM machine name|
|name|Name of the server|
|networks|A dict of assigned network addresses of the following form: ```
{networks”: {"public": ["9.37.204.234"],"private": []}
```

|
|machine\_name|Convenience attribute to fetch the machine name.|
|show|A string of all vRealize Automation server resource \(JSON\) details as returned by the API.|
|ucd\_generated\_sw\_comp|The name of the generated HCL UrbanCode Deploy component that is added to the VM node. If there is no HCL UrbanCode Deploy component added, the return string is null.|

**Parent topic:** [VMware vRealize Automation resource types](../../com.ibm.edt.heat.reference.doc/topics/VRA_heat_types_ov.md)

