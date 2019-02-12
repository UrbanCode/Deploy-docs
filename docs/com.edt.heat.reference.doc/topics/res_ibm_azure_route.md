# IBM::Azure::Route

This type represents a Microsoft™ Azure route.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|address\_prefix|String|True|Core|The destination CIDR to which the route applies.|
|name|String|True|Core|The name of the route table. If the specified name exists, a new unique name is created.|
|next\_hop\_type|String|True|Core|The type of Azure hop that the packet should be sent to. Valid values are as follows:-   VirtualNetworkGateway
-   VnetLocal
-   Internet
-   VirtualAppliance
-   None

|
|next\_hop\_ip\_address|String|False|Core|The IP address that packets should be forwarded to if the hop type is VirtualAppliance.|
|resource\_group|String|True|Core|The name of the resource group.|
|route\_table\_name|String|True|Core|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The name of the route.|
|route\_id|String|The Azure ID of the route ID.|
|show|String|The details of the route.|

## Example

This example creates a route table.

```
  azure_route_table_1:
    type: IBM::Azure::RouteTable
    properties:
      name: test-route-table
    metadata:
      azure_properties:
       resource_group:test-resource-group 
       tags:
          tag1 : value1
          tag2 : value2
```

This example creates a route for the new route table.

```
  azure_route_1:
    type: IBM::Azure::Route
    properties:
      name: test-route-1
      resource_group: test-resource-group
      route_table_name: {get_attr: [azure_route_table_1, name]}
      address_prefix: 192.0.0.0/16
      next_hop_type: Internet
    
```

**Parent topic:** [Microsoft Azure resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

