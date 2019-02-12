# Add a user to a group

## Request

```
PUT https://{hostname}:{port}
    /cli/group/addUser?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|Name of the user|
|group|string|true|Name of the group|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [addUserToGroup](udclient_addusertogroup.md).

**Parent topic:** [group resource](../../com.udeploy.api.doc/topics/rest_cli_group.md)

