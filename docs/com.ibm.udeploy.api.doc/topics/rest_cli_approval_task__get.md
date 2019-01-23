# List recent approval tasks

This command returns the approval tasks that have been modified since the given time.

## Request

```
GET https://{hostname}:{port}
    /cli/approval/task/?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|modifiedAfter|long|false|Include approval tasks that have been created or edited since this provided time. \(Optional\)|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getApprovalTasks](udclient_getapprovaltasks.md).

**Parent topic:** [approval/task resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_approval_task_.md)

