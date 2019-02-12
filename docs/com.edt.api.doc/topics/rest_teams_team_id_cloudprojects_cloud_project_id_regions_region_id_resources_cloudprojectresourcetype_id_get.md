# List details about a resource

This command lists details about a blueprint designer palette resource.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/teams/{team_id}/cloudprojects/{cloud_project_id}/regions/{region_id}/resources/{CloudProjectResourceType}/{id}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|id|string|true| |
|cloud\_project\_id|string|true| |
|CloudProjectResourceType|string|true| |
|region\_id|string|true| |
|team\_id|string|true| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

**Parent topic:** [rest/teams/Cloud project resource](../../com.edt.api.doc/topics/rest_teams_team_id_cloudprojects_cloud_project_id.md)

