# getSystemConfiguration

List system configuration properties

These properties are available on the System Settings page of the server.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getSystemConfiguration
```

## Parameters

None.

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

Related REST command: [List system configuration properties](rest_cli_systemconfiguration_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

