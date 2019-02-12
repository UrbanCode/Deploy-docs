# Remove access to all resources

This command removes access to all resources from the specified team and cloud project. This filtering affects what is available in the blueprint designer palette, when provisioning images, and in the REST API.

## Request

```
DELETE http://{hostname}:{port}
  /landscaper/rest/teams/{team_id}/cloudprojects/{cloud_project_id}/regions/{region_id}/resources
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|cloud\_project\_id|string|true| |
|region\_id|string|true| |
|team\_id|string|true| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

**Parent topic:** [rest/teams/Cloud project resource](../../com.edt.api.doc/topics/rest_teams_team_id_cloudprojects_cloud_project_id.md)

