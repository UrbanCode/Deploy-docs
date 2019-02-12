# List the cache clusters on the cloud

This command returns existing Elasticache clusters from AWS.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/cache_clusters
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/cache_clusters
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "engine": "redis",
    "replication_group_id": "rep-group-1",
    "name": "my-cluster",
    "id": "my-cluster",
    "icon": "images/editor/Elastic_Cache.gif",
    "category": "service",
    "subcategory": "memoryCache"
  },
  {
    "engine": "redis",
    "replication_group_id": "rep-group-1",
    "name": "my-cluster2",
    "id": "my-cluster2",
    "icon": "images/editor/Elastic_Cache.gif",
    "category": "service",
    "subcategory": "memoryCache"
  }
]
```

**Parent topic:** [rest/cloud resource](../../com.edt.api.doc/topics/rest_cloud.md)

