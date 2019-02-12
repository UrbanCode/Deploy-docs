# getApplicationProcessRequestStatus

Request the status of an application process request

Will return both the status of the request \(which indicates if it is still running\) and the request result \(which indicates the result of the process if it completed\).

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getApplicationProcessRequestStatus [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|request|string|true|ID of the application process request|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getApplicationProcessRequestStatus
  -request 47610d75-25c8-420d-a696-f006c34f5423
```

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

Related REST command: [Request the status of an application process request](rest_cli_applicationprocessrequest_requeststatus_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

