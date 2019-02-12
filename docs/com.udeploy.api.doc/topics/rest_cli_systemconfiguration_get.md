# List system configuration properties

These properties are available on the System Settings page of the server.

## Request

```
GET https://{hostname}:{port}
    /cli/systemConfiguration
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "externalURL": "https://ucdeploy.example.com:8443",
  "externalUserURL": "https://ucdeploy.example.com:8443",
  "repoAutoIntegrationPeriod": 15000,
  "deployMailHost": "smtp.example.com",
  "deployMailPassword": "",
  "deployMailPort": 25,
  "deployMailSecure": false,
  "deployMailSender": "sender@example.com",
  "deployMailUsername": "username",
  "cleanupHourOfDay": 0,
  "cleanupDaysToKeep": -1,
  "cleanupCountToKeep": -1,
  "cleanupArchivePath": "",
  "enableInactiveLinks": false,
  "enablePromptOnUse": false,
  "requireComplexPasswords": false,
  "minimumPasswordLength": 0,
  "validateAgentIp": false,
  "enableUIDebugging": false,
  "failProcessesWithUnresolvedProperties": true,
  "artifactAgent": "vm192-168",
  "serverLicenseType": "Session",
  "rclServerUrl": "27000@RCLServer.example.com",
  "agentAutoLicense": false
}
```

Related CLI command: [getSystemConfiguration](udclient_getsystemconfiguration.md).

**Parent topic:** [systemConfiguration resource](../../com.udeploy.api.doc/topics/rest_cli_systemconfiguration.md)

