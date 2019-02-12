# Approve or reject an approval task

## Request

```
PUT https://{hostname}:{port}
    /cli/approval/task/{taskId}/close
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|taskId|string|true| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [closeTask](udclient_closetask.md).

**Parent topic:** [approval/task resource](../../com.udeploy.api.doc/topics/rest_cli_approval_task_.md)

