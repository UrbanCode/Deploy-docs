# List the members of a group \(detailed\)

This command lists the members of a group, including IDs and e-mail addresses.

## Request

```
GET https://{hostname}:{port}
    /cli/group/exportDetailed?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|group|string|true|Name of the group|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/group/exportDetailed
  ?group=TeamA"
```

## Example response

```
[
  {
    "userName": "jdoe",
    "userId": "a459dffd-e057-494d-b119-16e85d7cd911",
    "userEmail": "jdoe@example.org"
  },
  {
    "userName": "jsmith",
    "userId": "7794dee7-d4c6-4f6f-b1ce-56c5d3cbfdda",
    "userEmail": "jsmith@example.org"
  }
]

```

Related CLI command: [exportDetailedGroup](udclient_exportdetailedgroup.md).

**Parent topic:** [group resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_group.md)

