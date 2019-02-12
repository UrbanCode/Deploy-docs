# List the properties on a component version

## Request

```
GET https://{hostname}:{port}
    /cli/version/versionProperties?{parameters}
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
    "id": "33528ab5-a7be-46cb-9f0c-916a42bd2f62",
    "name": "Prop1",
    "value": "value1",
    "description": "",
    "secure": false
  },
  {
    "id": "92339074-ab59-4fe3-936f-9ceec16ce5e6",
    "name": "Prop2",
    "value": "value1",
    "description": "",
    "secure": false
  }
]
```

Related CLI command: [getVersionProperties](udclient_getversionproperties.md).

**Parent topic:** [version resource](../../com.udeploy.api.doc/topics/rest_cli_version.md)

