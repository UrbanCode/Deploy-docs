# List the replication groups on the cloud

This command returns existing replication groups from AWS.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/replication_groups
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/replication_groups
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "name": "my-rep-group1",
    "id": "my-rep-group1",
    "icon": "images/editor/Replication_Group.gif",
    "category": "service",
    "subcategory": "replicationGroup"
  }
]
```

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

