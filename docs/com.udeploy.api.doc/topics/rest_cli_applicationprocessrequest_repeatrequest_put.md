# Repeat an application process request

## Request

```
PUT https://{hostname}:{port}
    /cli/applicationProcessRequest/repeatRequest?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|request|string|true|ID of the application process request to repeat|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "requestId": "8ece2acb-b8d6-4748-809a-44bf19f4f8f0"
}
```

Related CLI command: [repeatApplicationProcessRequest](udclient_repeatapplicationprocessrequest.md).

**Parent topic:** [applicationProcessRequest resource](../../com.udeploy.api.doc/topics/rest_cli_applicationprocessrequest.md)

