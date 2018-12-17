# List links on a version

This command lists all links that are associated with a specified component version.

## Request

```
GET https://{hostname}:{port}
    /cli/version/getLinks?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "name": "Link to MyCompany example web site",
    "value": "http://mycompany.example.com"
  },
  {
    "name": "Link to IBM web site",
    "value": "http://www.ibm.com"
  }
]
```

Related CLI command: [getVersionLinks](udclient_getversionlinks.md).

**Parent topic:** [version resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_version.md)

