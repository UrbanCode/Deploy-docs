# Get a link on a component version

## Request

```
GET https://{hostname}:{port}
    /cli/version/getLink?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|
|linkName|string|true|Name of the link|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "name": "Link to IBM web site",
  "value": "http://www.ibm.com"
}
```

Related CLI command: [getVersionLink](udclient_getversionlink.md).

**Parent topic:** [version resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_version.md)

