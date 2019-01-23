# Get the value of a system property

## Request

```
GET https://{hostname}:{port}
    /cli/systemConfiguration/getProperty?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|name|string|true|Name of the property|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
value001
```

Related CLI command: [getSystemProperty](udclient_getsystemproperty.md).

**Parent topic:** [systemConfiguration resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_systemconfiguration.md)

