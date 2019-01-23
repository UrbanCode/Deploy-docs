# IBM::Azure::VirtualNetworkPeering

This type represents a Microsoft™ Azure virtual network peering.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|allow\_forwarded\_traffic|Boolean|False|Core|Specify `True` to allow forwarded traffic from the virtual machines in the remote virtual network.|
|allow\_gateway\_transit|Boolean|False|Core|Specify `True` if gateway links can be used in remote virtual networking to link to this virtual network.|
|allow\_virtual\_network\_access|Boolean|False|Core|Specify `True` to allow the virtual machines in the linked virtual network space to be able to access all of the virtual machines in the local virtual network space.|
|name|String|True|Core|The virtual network peering name. If the specified name exists, a new, unique name is created.|
|remove\_virtual\_network|String|True|Core|The name or ID of the remote virtual network. If the name is used, it assumes the same resource group as the `virtual_network_name` parameter value.|
|resource\_group|String|True|Core|The resource group name.|
|use\_remote\_gateways|Boolean|False|Core|Specify `True` if the remote gateways can be used on this virtual network. If the flag is set to `True`, and the allowGatewayTransit parameter on remote peering is also true, the virtual network uses the gateways of the remote virtual network for transit. Only one peering can have this flag set to true. This flag cannot be set if the virtual network already has a gateway.|
|virtual\_network\_name|String|True|Core|The virtual network name for the peering.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The virtual network peering name.|
|peering\_id|String|The Azure ID of the virtual network peering.|
|peering\_state|String|The peering state of the virtual network peering. Valid values are:-   `Initiated`
-   `Connected`
-   `Disconnected`

|
|show|String|The virtual network details.|

## Example

These examples creates two virtual networks:

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
        
```

```
 azure_vnet_2:
    type: IBM::Azure::VirtualNetwork
    properties:
      name: testvnet2
    metadata:
      azure_properties:
        resource_group: test-rg
        address_prefixes:
          - '192.0.0.0/16'
```

This example creates bi-directional virtual network peering by using the remote network names:

```
 azure_vnet_peering_1_to_2:
    type: IBM::Azure::VirtualNetworkPeering
    properties:
      resource_group: test-rg
      name: testpeering1_to_2
      virtual_network_name: { get_resource: azure_vnet_1 }
      remote_virtual_network: { get_resource: azure_vnet_2 } #testvnet2
      allow_virtual_network_access: True
      allow_forwarded_traffic: True
      allow_gateway_transit: True
      use_remote_gateways: False
    
```

This example creates bi-directional virtual network peering by using the remote network IDs:

```
 azure_vnet_peering_2_to_1:
    type: IBM::Azure::VirtualNetworkPeering
    properties:
      resource_group: test-rg
      name: testpeering2_to_1
      virtual_network_name: { get_resource: azure_vnet_2 }
      remote_virtual_network: { get_attr: [azure_vnet_1, virtual_network_id]}
      allow_virtual_network_access: True
      allow_forwarded_traffic: True
      allow_gateway_transit: True
      use_remote_gateways: False
    

```

**Parent topic:** [Microsoft Azure resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

