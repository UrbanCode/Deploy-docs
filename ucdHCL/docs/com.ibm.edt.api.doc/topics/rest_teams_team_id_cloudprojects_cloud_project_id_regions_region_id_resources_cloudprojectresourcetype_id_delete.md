# Remove access to a resource

This command removes access to a resource from the specified team and cloud project. This filtering affects what is available in the blueprint designer palette, when provisioning images, and in the REST API.

## Request

```
DELETE http://{hostname}:{port}
  /landscaper/rest/teams/{team_id}/cloudprojects/{cloud_project_id}/regions/{region_id}/resources/{CloudProjectResourceType}/{id}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|id|string|true| |
|cloud\_project\_id|string|true| |
|CloudProjectResourceType|string|true| |
|region\_id|string|true| |
|team\_id|string|true| |

**Parent topic:** [rest/teams/Cloud project resource](../../com.ibm.edt.api.doc/topics/rest_teams_team_id_cloudprojects_cloud_project_id.md)

