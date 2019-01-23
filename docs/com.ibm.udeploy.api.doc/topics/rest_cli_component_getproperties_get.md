# Get values for component properties

This command returns all component properties.

## Request

```
GET https://{hostname}:{port}
    /cli/component/getProperties?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "3702f391-09e1-4550-903a-d5ae286c94aa",
    "name": "Prop1",
    "value": "value1",
    "description": "",
    "secure": false
  }
]
```

Related CLI command: [getComponentProperties](udclient_getcomponentproperties.md).

**Parent topic:** [component resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_component.md)

