# IBM::Azure::NetworkInterface

This resource type represents a network interface on an Microsoft Azure image.

This resource type extends the OpenStack resource type `OS::Neutron::Port`.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|dns\_servers|List|False|Extended|The list of DNS servers to use for this network interface. This property overrides the default virtual network server list.|
|enable\_ip\_address\_forwarding|Boolean|False|Extended|Specify true to enable IP address forwarding on this network interface. The default is false.|
|fixed\_ips|Map|False|Core|The subnet and IP address information for this network interface. See [Table 2](#fixed_ips_list).|
|internal\_dns\_name\_label|String|False|Extended|The relative DNS name for this network interface. This name is used for internal communications between virtual machines that are in the same virtual network.|
|load\_balancer\_backend\_address\_pools|List|False|Extended|The list of load balancer backend address pools to which the network interfaced is attached.|
|load\_balancer\_inbound\_nat\_rules|List|False|Extended|The list of load balancer inbound NAT rules to which the network interface is attached.|
|name|String|False|Core|Name of the network interface. If the specified name exists, the blueprint design server creates a unique name.|
|network or network\_id|String|True|Core|The virtual network for the network interface. The properties network and network\_id are equvalent.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|resource\_group|String|True|Extended|The resource group name.|
|security\_groups|List|False|Core|The security group for the network interface. Azure supports only one security group per network interface.|
|tags|List|False|Extended|A list of name-value pairs to set as tags on the resource.|

The fixed\_ips parameter requires a list of IP addresses for the port. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|subnet\_id or subnet|String|False|The subnet for this network interface. The properties subnet and subnet\_id are equivalent. If neither of these properties are specified, the server assigns a subnet from the attached virtual network.|
|ip\_address|String|False|The static private IP address for the network interface.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The name of the network interface.|
|network\_interface\_id|String|The Azure ID of the network interface.|
|mac\_address|String|The MAC address of the network interface.|
|show|String|The details of the network interface.|

## Examples

This example creates a network interface on a subnet with a security group and tags.

```
  azure_nic:
    type: IBM::Azure::NetworkInterface
    properties:
      name: testnic1
      network: test-vnet
      fixed_ips:
        - subnet:  test-subnet
      security_groups:
          - test-nsg
    metadata:
      azure_properties:
        resource_group: test-rg
        tags:
          tag1 : value1
          tag2 : value2
```

This example creates a network interface on a subnet with a static private IP address.

```
  azure_nic_private_ip:
    type: IBM::Azure::NetworkInterface
    properties:
      name: testnic2
      network: test-vnet
      fixed_ips:
        - subnet:  test-subnet
          ip_address: 10.0.1.13
    metadata:
      azure_properties:
        resource_group: { get_param: resource_group }
```

This example creates a network interface on a subnet with DNS and IP forwarding settings.

```
  azure_nic_dns:
    type: IBM::Azure::NetworkInterface
    properties:
      name: testnic3
      network: test-vnet
      fixed_ips:
        - subnet:  test-subnet
    metadata:
      azure_properties:
        resource_group: { get_param: resource_group }
        enable_ip_address_forwarding: True
        dns_servers:
          - "9.1.1.1"
          - "8.1.1.1"
        internal_dns_name_label: testnic3
```

**Parent topic:** [Microsoft Azure resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

