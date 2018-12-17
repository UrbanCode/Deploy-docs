# Import a group

Specify the details about the group in the JSON file. You can list one or more members of the new group in the 'users' array, or you can leave the array blank to create an empty group. Groups can be created only in Internal Storage authorization realms.

## Request

```
PUT https://{hostname}:{port}
    /cli/group/import
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "authorizationRealm": "Authorization realm name",
  "name": "Group name",
  "users": ["User names"]
}

```

## Example JSON request

```
{
  "name": "group1",
  "authorizationRealm": "Internal Security",
  "users": [
    "jdoe",
    "jsmith"
  ]
}
```

## Example response

```
{
  "id": "9dc44e77-e241-480e-8fbb-50f84b64b24b",
  "name": "group1",
  "enabled": true
}
```

Related CLI command: [importGroup](udclient_importgroup.md).

**Parent topic:** [group resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_group.md)

