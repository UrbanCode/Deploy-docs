# Create an empty group

Groups can only be created in Internal Storage authorization realms.

## Request

```
PUT https://{hostname}:{port}
    /cli/group/create?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|group|string|true|Name of the group|
|authorizationRealm|string|true|Name of the Internal Storage authorization realm|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "id": "a5be904f-d65a-41ae-9bfd-0a0384c90eeb",
  "name": "group1",
  "enabled": true
}
```

Related CLI command: [createGroup](udclient_creategroup.md).

**Parent topic:** [group resource](../../com.udeploy.api.doc/topics/rest_cli_group.md)

