# Enable or disable filtering

This command enables or disables resource filtering for the given cloud project and team. This filtering affects what is available in the blueprint designer palette, when provisioning images, and in the REST API.

## Request

```
PUT http://{hostname}:{port}
  /landscaper/rest/teams/{team_id}/cloudprojects/{cloud_project_id}/regions/{region_id}/resources
Accept: application/json
Content-Type: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|cloud\_project\_id|string|true| |
|region\_id|string|true| |
|team\_id|string|true| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Content-Type|`application/json`|true| |
|Accept|`application/json`|true| |

**Parent topic:** [rest/teams/Cloud project resource](../../com.ibm.edt.api.doc/topics/rest_teams_team_id_cloudprojects_cloud_project_id.md)

