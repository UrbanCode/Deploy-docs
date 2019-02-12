# List resource properties

## Request

```
GET https://{hostname}:{port}
    /cli/resource/getProperties?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "bd20924e-8547-4d41-b9b1-36b41278d224",
    "name": "property1",
    "value": "1",
    "description": "A new property",
    "secure": false
  },
  {
    "id": "18963e9e-2cca-47ac-807a-7fc5e67c49ee",
    "name": "property2",
    "value": "",
    "description": "A property with no value",
    "secure": false
  },
  {
    "id": "9cc56712-65f8-41fe-8fd6-d07414364c98",
    "name": "property3",
    "value": "****",
    "description": "A secure property",
    "secure": true
  }
]
```

Related CLI command: [getResourceProperties](udclient_getresourceproperties.md).

**Parent topic:** [resource resource](../../com.udeploy.api.doc/topics/rest_cli_resource.md)

