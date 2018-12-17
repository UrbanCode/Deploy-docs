# List system properties

This command returns a JSONArray representation of the system properties, which behave like global variables for the server.

## Request

```
GET https://{hostname}:{port}
    /cli/systemConfiguration/getProperties
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "af25c8b2-a69a-4d1b-a0ed-ddb226dfac18",
    "name": "System property 1",
    "value": "value001",
    "description": "This is a system property",
    "secure": false
  }
]
```

Related CLI command: [getSystemProperties](udclient_getsystemproperties.md).

**Parent topic:** [systemConfiguration resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_systemconfiguration.md)

