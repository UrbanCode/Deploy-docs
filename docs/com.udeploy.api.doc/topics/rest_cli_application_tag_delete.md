# Remove a tag from an application

## Request

```
DELETE https://{hostname}:{port}
    /cli/application/tag?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|tag|string|true|Name of the tag|

Related CLI command: [removeTagFromApplication](udclient_removetagfromapplication.md).

**Parent topic:** [application resource](../../com.udeploy.api.doc/topics/rest_cli_application.md)

