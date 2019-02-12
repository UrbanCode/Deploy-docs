# IBM::Azure::InboundNatRule

This type represents a Microsoft™ Azure load balancing rule. It can create an inbound NAT rule for a load balancer.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|backend\_port|Integer|True|Core|The port for the internal endpoint. The value must be between 1 and 65534.|
|enable\_floating\_ip|Boolean|False|Core|Configures a virtual machine's endpoint for the floating IP capability that is required for configuring a SQL AlwaysOn Availability Group.|
|frontend\_ip\_configuration|String|True|Core|The name or ID of the front-end IP configuration for the inbound NAT rule.|
|frontend\_port|Integer|True|Core|The port for the external endpoint. Port numbers for each rule must be unique within the load balancer. Values must be between 1 and 65534.|
|idle\_timeout|Integer|False|Core|Timeout, in minutes, for the TCP idle connection. The default is `4` minutes, and the value must be between 4 and 30 minutes.|
|load\_balancer|String|True|Core|The name of the load balancer to add the inbound NAT rule to.|
|name|String|True|Core|The name of the load balancing rule.|
|protocol|String|True|Core|The transport protocol for the external endpoint. Valid values are `Udp` and `Tcp`.|
|resource\_group|String|True|Core|The name of the resource group.|

|Attribute|Type|Description|
|---------|----|-----------|
|backend\_ip\_configuration|String|The backend IP configuration of the inbound NAT rule.|
|inbound\_nat\_rule\_id|String|The Azure ID of the inbound NAT rule.|
|name|String|The name of the inbound NAT rule.|
|show|String|The details of the inbound NAT rule.|

## Example

This example creates a load balancing rule:

```
 azure_lb_nat_rule:
    type: IBM::Azure::InboundNatRule
    properties:
      name: test-lbnatrule-1
      resource_group: test-rg
      load_balancer: test-lb
      frontend_ip_configuration: LoadBalancerFrontEnd
      frontend_port: 8080
      backend_port: 80
      protocol: Tcp
      idle_timeout: 6
```

This example associates the load balancing rule with a load balancer:

```
 azure_nic:
    type: IBM::Azure::NetworkInterface
    properties: 
     name: testnic1
     network: test-vnet
     fixed_ips:
      -subnet: subnet2
    metadata:
     azure_properties:
      resource_group: test-rg
      load_balancer_inbound_nat_rules:
        - { get_attr: [azure_lb_nat_rule, inbound_nat_rule_id]}
```

**Parent topic:** [Microsoft Azure resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

