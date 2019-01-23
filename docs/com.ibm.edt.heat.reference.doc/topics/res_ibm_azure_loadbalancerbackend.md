# IBM::Azure::BackendAddressPool

This type represents a Microsoft™ Azure load balancing rule. It can create a backend address pool for a load balancer.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|load\_balancer|String|True|Core|The name of the load balancer to which to add the backend address pool.|
|name|String|True|Core|The name of the backend address pool.|
|resource\_group|String|True|Core|The name of the resource group.|

|Attribute|Type|Description|
|---------|----|-----------|
|backend\_address\_pool\_id|String|The Azure ID of the backend address pool.|
|backend\_ip\_configurations|String|The list of backend IP configurations that use the backend address pool.|
|name|String|The name of the backend address pool.|
|outbound\_nat\_rules|String|The list of the outbound NAT rules that use the backend address pool.|
|show|String|The details of the backend address pool.|

## Example

These examples create two backend address pools on a load balancer:

```
 azure_lb_pool:
    type: IBM::Azure::BackendAddressPool
    properties:
      name: test-pool-1
      resource_group: test-rg
      load_balancer: test-lb
```

```
 azure_lb_pool_2:
    type: IBM::Azure::BackendAddressPool
    properties:
      name: test-pool-2
      resource_group: test-rg
      load_balancer: test-lb
```

This example associates the backend address pools to a network interface:

```
 azure_nic:
    type: IBM::Azure::NetworkInterface
    properties: 
     name: testnic1
     network: test-vnet
     fixed_ips:
      -subnet: subnet2
     load_balancer_backend_address_pools:
       - { get_attr: [azure_lb_pool, backend_address_pool_id]}
       - { get_attr: [azure_lb_pool_2, backend_address_pool_id]}
    metadata:
     azure_properties:
      resource_group: test-rg
```

**Parent topic:** [Microsoft Azure resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

