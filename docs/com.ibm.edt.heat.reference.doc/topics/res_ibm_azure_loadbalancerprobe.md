# IBM::Azure::LoadBalancerProbe

This type represents a Microsoft™ Azure load balancer probe. It can create an inbound NAT rule for a load balancer.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|interval\_in\_seconds|Integer|True|Core|The interval, in seconds, between probes to the backend endpoint for health status. The default value is `15`; the minimum value is `5`.|
|load\_balancer|String|True|Core|The name of the load balancer to which to add the probe.|
|name|String|True|Core|The name of the load balancing rule.|
|number\_of\_probes|Integer|False|Core|The number of failed probe attempts after which the backend endpoint is removed from notation. The default value is `2`.|
|port|Integer|True|Core|The port on which the probe queries the backend endpoint.|
|protocol|String|True|Core|The protocol for this probe. Valid values are `Http` and `Tcp`.|
|request\_path|String|False|Core|The URI that is used for requesting health status from the backend endpoint. This value is required if the protocol is set to `Http`.|
|resource\_group|String|True|Core|The name of the resource group.|

|Attribute|Type|Description|
|---------|----|-----------|
|load\_balancing\_rules|String|The load balancing rules that use the probe.|
|name|String|The name of the probe.|
|probe\_id|String|The Azure ID of the probe.|
|show|String|The details of the probe.|

## Example

This example creates a probe and associates it with a load balancer:

```
 azure_lb_probe:
    type: IBM::Azure::Probe
    properties:
      name: test-probe-1
      resource_group: cmh-resourcegroup-1
      load_balancer: test-lb-2
      interval_in_seconds: 10
      number_of_probes: 2
      request_path: /index.html/test
      port: 8080
      protocol: Http
        
```

**Parent topic:** [Microsoft Azure resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

