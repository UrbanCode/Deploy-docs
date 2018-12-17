# IBM::ElasticLoadBalancing::Pool

This resource type represents the load balancing pool.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_state\_up|Boolean|False|Core|The administrative state of this pool. The default value is true.|
|description|String|False|Core|The description of the load balancing pool.|
|lb\_method|String|True|Core|The algorithm that is used to distribute load between the members of the pool. The following values are allowed: -   round\_robin
-   least\_connections
-   source\_ip

|
|monitors|List|False|Core|The list of health monitors that are associated with the pool.|
|name|String|False|Core|The name of the load balancing pool.|
|protocol|String|True|Core|The protocol for load balancing. The following values are allowed: -   TCP
-   HTTP
-   HTTPS

|
|subnet|String|False|Core|The subnet for the port on which the members of the pool are connected.|
|subnet\_id|String|False|Core|The subnet for the port on which the members of the pool are connected.|
|vip|Map|True|Core|The IP addresses and port numbers of the pool.|

The vip parameter requires a list of addresses and ports for the pool. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|address|String|False|The vip IP address.|
|admin\_state\_up|Boolean|False|The vip administrative state. The default value is `true`.|
|connection\_limit|Integer|False|The maximum number of connections per second that the vip allows.|
|description|String|False|The vip description.|
|name|String|False|The vip name.|
|protocol\_port|Integer|True|The TCP port on which to listen for client traffic that is associated with the vip address.|
|session\_persistence|Map|False|The configuration of session persistence.|
|subnet|String|False|The vip subnet.|

The session\_persistence parameter for the vip parameter requires a list of types. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|cookie\_name|String|False|The name of the cookie, which is required if the type is `app_cookie`.|
|type|String|True|The method of implementation of the session persistence feature. The following values are allowed:-   source\_ip
-   http\_cookie
-   app\_cookie

|

This resource type has no attributes.

**Parent topic:** [Amazon ElasticLoadBalancing resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_elasticloadbalancing_ov.md)

