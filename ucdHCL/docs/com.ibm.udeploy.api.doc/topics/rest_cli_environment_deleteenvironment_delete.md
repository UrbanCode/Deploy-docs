# Delete an environment

## Request

```
DELETE https://{hostname}:{port}
    /cli/environment/deleteEnvironment?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|
|deleteAttachedResources|boolean|false|Specify true to delete all resources in this environment, including all subresources \(Optional\)|
|deleteCloudInstances|boolean|false|Specify true to delete any associated instances in the cloud provider; this parameter is valid only for environments that were created dynamically along with the environment \(Optional\)|

Related CLI command: [deleteEnvironment](udclient_deleteenvironment.md).

**Parent topic:** [environment resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment.md)

