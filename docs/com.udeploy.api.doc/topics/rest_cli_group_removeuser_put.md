# Remove a user from a group

## Request

```
PUT https://{hostname}:{port}
    /cli/group/removeUser?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|Name of the user|
|group|string|true|Name of the group|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [removeUserFromGroup](udclient_removeuserfromgroup.md).

**Parent topic:** [group resource](../../com.udeploy.api.doc/topics/rest_cli_group.md)

