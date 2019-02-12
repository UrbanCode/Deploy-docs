# Add a tag to a component

## Request

```
PUT https://{hostname}:{port}
    /cli/component/tag?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|tag|string|true|Name of the tag|
|color|string|false|Hex representation of the color for the tag, such as FF0000. This parameter is used only if the tag is being created.|
|description|string|false|Description of the tag. This parameter is used only if the tag is being created.|

Related CLI command: [addTagToComponent](udclient_addtagtocomponent.md).

**Parent topic:** [component resource](../../com.udeploy.api.doc/topics/rest_cli_component.md)

