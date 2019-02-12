# Create a resource

This command creates a resource. The specified cloud project and team can use the resource in the blueprint designer palette, when provisioning environments, and through the REST API.

## Request

```
POST http://{hostname}:{port}
  /landscaper/rest/teams/{team_id}/cloudprojects/{cloud_project_id}/regions/{region_id}/resources/{CloudProjectResourceType}
Accept: application/json
Content-Type: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|cloud\_project\_id|string|true| |
|CloudProjectResourceType|string|true| |
|region\_id|string|true| |
|team\_id|string|true| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Content-Type|`application/json`|true| |
|Accept|`application/json`|true| |

**Parent topic:** [rest/teams/Cloud project resource](../../com.edt.api.doc/topics/rest_teams_team_id_cloudprojects_cloud_project_id.md)

