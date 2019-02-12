# Delete a tag from a component

## Request

```
DELETE https://{hostname}:{port}
    /cli/component/tag?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|tag|string|true|Name of the tag|

Related CLI command: [removeTagFromComponent](udclient_removetagfromcomponent.md).

**Parent topic:** [component resource](../../com.udeploy.api.doc/topics/rest_cli_component.md)

