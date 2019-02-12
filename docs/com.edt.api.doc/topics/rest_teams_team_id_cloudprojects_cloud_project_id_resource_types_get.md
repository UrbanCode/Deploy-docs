# List all resource types

This command lists all resource types that are available to the given cloud project and team, including in the blueprint designer palette, at provisioning time, and through the REST API.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/teams/{team_id}/cloudprojects/{cloud_project_id}/resource_types
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|cloud\_project\_id|string|true| |
|team\_id|string|true| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

**Parent topic:** [rest/teams/Cloud project resource](../../com.edt.api.doc/topics/rest_teams_team_id_cloudprojects_cloud_project_id.md)

