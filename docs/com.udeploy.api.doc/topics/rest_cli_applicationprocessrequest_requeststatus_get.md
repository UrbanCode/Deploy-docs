# Request the status of an application process request

Will return both the status of the request \(which indicates if it is still running\) and the request result \(which indicates the result of the process if it completed\).

## Request

```
GET https://{hostname}:{port}
    /cli/applicationProcessRequest/requestStatus?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|request|string|true|ID of the application process request|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "status": "CLOSED",
  "result": "SUCCEEDED"
}
```

This command returns the following statuses:

-   `CANCELING`
-   `CLOSED`
-   `COMPENSATING`
-   `EXECUTING`
-   `FAULTED`
-   `FAULTING`
-   `INITIALIZED`
-   `PENDING`
-   `UNINITIALIZED`

This command returns the following results:

-   `APPROVAL REJECTED`
-   `AWAITING APPROVAL`
-   `CANCELED`
-   `COMPENSATED`
-   `FAILED TO START`
-   `FAULTED`
-   `NONE`
-   `SCHEDULED FOR FUTURE`
-   `SUCCEEDED`
-   `UNINITIALIZED`

Related CLI command: [getApplicationProcessRequestStatus](udclient_getapplicationprocessrequeststatus.md).

**Parent topic:** [applicationProcessRequest resource](../../com.udeploy.api.doc/topics/rest_cli_applicationprocessrequest.md)

