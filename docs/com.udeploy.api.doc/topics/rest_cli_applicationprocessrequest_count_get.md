# Count all application process requests

This command returns the total number of application process requests for all applications.

## Request

```
GET https://{hostname}:{port}
    /cli/applicationProcessRequest/count?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|startedAfter|long|false|A timestamp, in milliseconds from the UNIX epoch. If you specify this parameter, the server counts all application process requests that were created after the specified timestamp.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/applicationProcessRequest/count?startedAfter=1471603999000" 

```

## Example response

```
{
  "appProcReqCount": 223
}
```

Related CLI command: [getApplicationsProcessRequestsCount](udclient_getapplicationsprocessrequestscount.md).

**Parent topic:** [applicationProcessRequest resource](../../com.udeploy.api.doc/topics/rest_cli_applicationprocessrequest.md)

