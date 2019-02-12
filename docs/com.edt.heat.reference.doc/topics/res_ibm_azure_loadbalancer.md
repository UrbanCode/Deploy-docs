# IBM::Azure::LoadBalancer

This type represents a Microsoft™ Azure load balancer. It can create a new load balancer.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|frontend\_ip\_configurations|List|False|Core|A list of front-end IP configurations for the load balancer. See [Table 2](#frontend).|
|name|String|True|Core|The name of the load balancer. If a specified name exists, a new, unique name is created.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|resource\_group|String|True|Core|The name of the resource group.|
|tags|List|False|Extended|A list of name-value pairs to set as tags on the resource.|

The frontend\_ip\_configurations parameter requires a list of front-end IP configurations for the load balancer. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|frontend\_ip\_configuration\_name|String|True|The name of the IP configuration.|
|private\_ip\_address|String|False|The static, private IP address of the IP configuration.|
|private\_ip\_address\_allocation\_method|String|False|The private IP allocation method. Valid values are `Static` and `Dynamic`.|
|public\_ip\_address\_name|String|False|The name or ID of the public IP configuration.|
|subnet\_ip|String|False|The Azure ID of a subnet to use for the IP configuration.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The name of the load balancer.|
|load\_balancer\_id|String|The Azure ID of the load balancer.|
|show|String|The details of the load balancer.|

## Example

This example creates a new internet-facing load balancer with a front-end IP configuration by using a public IP address:

```
 azure_lb:
    type: IBM::Azure::LoadBalancer
    properties:
      name: test-internet-lb
      resource_group: test-rg
      frontend_ip_configurations:
       -frontend_ip_configuration_name: frontendconfig1
        public_ip_address_name: { get_resource: azure_public_ip }
```

```
 azure_public_ip:
      type: IBM::Azure::PublicIP
      metadata:
       azure_properties:
        resource_group: test-rg
        name: testloadbal1ip1
```

This example creates a new internal load balancer with a front-end IP configuration by using an existing subnet ID:

```
 azure_internal_ip:
    type: IBM::Azure::LoadBalancer
    properties:
      name: test-internal-lb
      resource_group: test-rg
      frontend_ip_configurations: 
       -frontend_ip_configuration_name: subnetconfig1
        subnet_id: /subscriptions/<sub ID>/resourceGroups/test-rg/providers/Microsoft.Network/virtualNetworks/test-vnet/subnets/default
```

**Parent topic:** [Microsoft Azure resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

