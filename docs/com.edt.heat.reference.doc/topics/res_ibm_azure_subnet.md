# IBM::Azure::Subnet

This type represents a Microsoft™ Azure subnet.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|cidr|String|True|Core|The address space for this subnet. This value must be within the range of the virtual network.|
|name|String|True|Core|The name of the subnet. If a subnet with the specified name exists, a new unique name is created.|
|network|String|True|Core|The virtual network name in which to create the subnet.|
|resource\_group|String|True|Extended|The resource group name.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|route\_table|String|False|Extended|The route table name to attach to the subnet.|
|security\_group|String|False|Extended|The network security group to attach to the subnet.|

|Attribute|Type|Description|
|---------|----|-----------|
|ip\_configurations|String|The IP configurations of the subnet.|
|name|String|The name of the subnet.|
|show|String|The details of the subnet.|
|subnet\_id|String|The ID of the subnet.|

## Example

This example creates a subnet with address space and optional security group and route table.

```
  azure_subnet
    type: IBM::Azure::Subnet
    properties:
      network: test-vnet
      cidr: 10.0.1.0/26
      name: test-subnet
    metadata:
      azure_properties:
        resource_group: test-rg
        security_group: test-nsg
        route_table: test-routetable
```

**Parent topic:** [Microsoft Azure resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

