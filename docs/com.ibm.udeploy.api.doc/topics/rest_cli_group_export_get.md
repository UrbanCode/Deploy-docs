# List the members of a group

## Request

```
GET https://{hostname}:{port}
    /cli/group/export?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|group|string|true|Name of the group|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "name": "group1",
  "users": [
    "jsmith",
    "jdoe"
  ]
}
```

Related CLI command: [exportGroup](udclient_exportgroup.md).

**Parent topic:** [group resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_group.md)

