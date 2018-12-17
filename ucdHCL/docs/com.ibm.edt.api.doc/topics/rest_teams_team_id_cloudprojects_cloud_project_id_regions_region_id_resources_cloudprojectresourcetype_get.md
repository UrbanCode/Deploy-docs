# List all resources of a resource type

This command lists all resources of a given resource type that are available to a given cloud project and team.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/teams/{team_id}/cloudprojects/{cloud_project_id}/regions/{region_id}/resources/{CloudProjectResourceType}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|cloud\_project\_id|string|true| |
|CloudProjectResourceType|string|true| |
|region\_id|string|true| |
|team\_id|string|true| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

**Parent topic:** [rest/teams/Cloud project resource](../../com.ibm.edt.api.doc/topics/rest_teams_team_id_cloudprojects_cloud_project_id.md)

