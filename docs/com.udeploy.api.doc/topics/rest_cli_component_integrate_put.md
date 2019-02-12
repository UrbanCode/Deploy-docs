# Import new component versions

This command polls the source configuration for new component versions. Add property name/value pairs as necessary - this can be used to add specific versions.

## Request

```
PUT https://{hostname}:{port}
    /cli/component/integrate
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "component": "Component name or ID",
  "properties": {"Source configuration plugin property 
  name": "Property value"}
}

```

## Example JSON request

```
{
  "component": "JPetStore-WEB",
  "properties": {
    "Prop1": "value1"
  }
}
```

Related CLI command: [importVersions](udclient_importversions.md).

**Parent topic:** [component resource](../../com.udeploy.api.doc/topics/rest_cli_component.md)

