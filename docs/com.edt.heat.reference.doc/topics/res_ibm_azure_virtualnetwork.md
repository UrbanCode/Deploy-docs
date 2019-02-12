# IBM::Azure::VirtualNetwork

This type represents a Microsoft™ Azure virtual network.

This resource type extends the OpenStack resource type `OS::Neutron::Net`.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|address\_prefixes|List|True|Extended|A list of IP address ranges for this virtual network, specified in CIRD format, such as `10.0.0.0/16`.|
|dns\_servers|List|False|Extended|A list of DNS servers for the virtual network.|
|name|String|True|Core|The name of the virtual network. If the specified name exists, a new unique name is created.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|resource\_group|String|True|Extended|The resource group name.|
|tags|List|False|Extended|A list of name-value pairs to set as tags on the resource.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The name of the virtual network.|
|show|String|The details of the virtual network.|
|virtual\_network\_id|String|The ID of the virtual network.|

## Example

This example creates a virtual network with the specified address prefix and tag.

```
 azure_vnet_1:
    type: IBM::Azure::VirtualNetwork
    properties:
      name: testvnet1
    metadata:
      azure_properties:
        resource_group: test-rg
        address_prefixes:
          - '10.0.0.0/16'
        tags:
          tag1 : vnet1
```

**Parent topic:** [Microsoft Azure resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

