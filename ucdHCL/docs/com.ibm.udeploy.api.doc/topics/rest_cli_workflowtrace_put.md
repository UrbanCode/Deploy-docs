# Cancel a workflow in progress

## Request

```
PUT https://{hostname}:{port}
    /cli/workflowTrace?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|workflow|string|true|ID of the workflow to cancel.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/workflowTrace?
  workflow=193e892f-677d-4534-9763-ff8d005a5829" -X PUT
```

Related CLI command: [cancelWorkflow](udclient_cancelworkflow.md).

**Parent topic:** [workflowTrace resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_workflowtrace.md)

