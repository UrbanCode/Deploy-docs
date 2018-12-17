# Add a tag to an application

## Request

```
PUT https://{hostname}:{port}
    /cli/application/tag?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|tag|string|true|Name of the tag|
|color|string|false|Hex representation of the color for the tag, such as FF0000. This parameter is used only if the tag is being created.|
|description|string|false|Description of the tag. This parameter is used only if the tag is being created.|

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/application/tag
  ?application=JPetStore&tag=Tag1" -X PUT
```

Related CLI command: [addTagToApplication](udclient_addtagtoapplication.md).

**Parent topic:** [application resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_application.md)

