# List properties that must be specified for a process

If a snapshot name or ID is specified, results include any component process steps which have some properties marked to receive values later for a specific version based on the snapshot.

## Request

```
GET https://{hostname}:{port}
    /cli/applicationProcess/unfilledProperties?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|processName|string|true|Name of the application process|
|snapshot|string|false|Name or ID of the snapshot|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/
  applicationProcess/unfilledProperties?application=MyApplication&processName=deploy"
```

## Example response

```
[
  {
    "id": "decc3570-17ae-4b46-b640-6a7180edafa9",
    "name": "MyProperty",
    "label": "MyProperty",
    "pattern": "",
    "type": "TEXT",
    "value": "",
    "required": false,
    "description": "",
    "placeholder": ""
  }
]
```

Related CLI command: [getApplicationProcessUnfilledProperties](udclient_getapplicationprocessunfilledproperties.md).

**Parent topic:** [applicationProcess resource](../../com.udeploy.api.doc/topics/rest_cli_applicationprocess.md)

