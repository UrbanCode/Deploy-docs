# setSystemConfiguration

Update the system configuration

Use this command to set any of the properties on the System Settings page of the server. The JSON template for this command lists all of the properties that you can change, but you can omit properties that you are not changing.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  setSystemConfiguration [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "agentAutoLicense": "Specify true to automatically 
  assign licenses to agents",
  "artifactAgent": "Specify a default agent for component 
  version imports.",
  "auditLogCleanupEnabled": "Whether the audit logs will 
  be deleted after a given number of days.",
  "auditLogCleanupHour": "The hour when audit logs are 
  cleaned; the value must be an integer from 0 (midnight) to 
  23 (11pm).",
  "auditLogCleanupMinute": "The minute when audit logs are 
  cleaned; the value must be an integer from 0 to 59.",
  "auditLogReadEntriesEnabled": "Controls whether READ 
  events are captured in the audit log.",
  "auditLogRetentionLength": "The number of days to retain 
  audit log entries.",
  "cleanupArchivePath": "The path for archived component 
  versions",
  "cleanupCountToKeep": "The number of component versions 
  to keep",
  "cleanupDaysToKeep": "The number of days component 
  versions are kept",
  "cleanupHourOfDay": "The time when versions are cleaned; 
  the value must be an integer from 0 (midnight) to 23 (11 
  pm)",
  "defaultLocale": "The default locale to use for the 
  system (determines language and date formats.)",
  "deployMailHost": "The host name of the mail server that 
  is used for notifications",
  "deployMailPassword": "The user password for sending 
  email notifications",
  "deployMailPort": "The SMTP port that is used by the 
  notifications mail server",
  "deployMailSecure": "Specifies whether the SMTP 
  connection is secure",
  "deployMailSender": "The sender address for email 
  notifications",
  "deployMailUsername": "The user name for sending email 
  notifications",
  "enableAllowFailure": "Controls whether the 'allow 
  failure' option can be used on the steps in a workflow.",
  "enableInactiveLinks": "Specify true to show links to 
  inactive objects",
  "enablePromptOnUse": "Controls whether user-entered 
  values can be specified at process run time",
  "enableUIDebugging": "Changes how the UI resources are 
  loaded so it is easier to debug problems in the UI if set. 
  Enabling reduces UI performance.",
  "envCompPropsOverrideEnvProps": "Determines whether or 
  not environment component properties will override 
  environment properties.",
  "externalURL": "The URL that agents use to connect to 
  the server",
  "externalUserURL": "The URL that users enter to connect 
  to the server",
  "failProcessesWithUnresolvedProperties": "Determines 
  whether or not a process will fail when it encounters a 
  property that cannot be resolved.",
  "historyCleanupDaysToKeep": "The number of days 
  application process history is to be kept. -1 will disable 
  application process history cleanup.",
  "historyCleanupDuration": "The maxiumum number of hours 
  per day the history cleanup process can take; the value 
  must be an integer from 1 to 23.",
  "historyCleanupEnabled": "The system will not delete any 
  process history unless this is enabled.",
  "historyCleanupHour": "The time when application process 
  history is cleaned; the value must be an integer from 0 
  (midnight) to 23 (11pm).",
  "historyCleanupMinute": "The minute when process history 
  is cleaned; the value must be an integer from 0 to 59.",
  "integrationTag": "Specify an agent tag to use any agent 
  with the given tag for version imports.",
  "licenseServerUrl": "The host name and port of the 
  license server",
  "minimumPasswordLength": "Determines the minimum length 
  for passwords",
  "repoAutoIntegrationPeriod": "The number of seconds 
  between the times that the server polls components for new 
  versions",
  "requireCommentForProcessChanges": "When enabled, the 
  user must provide a comment when saving changes to any 
  process design.",
  "requireComplexPasswords": "If selected, passwords must 
  contain at least two of the four character classes and 
  must be at least as long as the specified minimum length",
  "skipCollectPropertiesForExistingAgents": "Controls 
  whether or not agent properties will be updated when an 
  existing agent reconnects to the server.",
  "use.default.atr.if.not.specified": "Use the Default 
  Auth Token Restriction for plugin steps that do not have 
  an auth token restriction set. If false this will not 
  restrict auth token usage at all. Any new version will 
  have an auth token restriction.",
  "validateAgentIp": "Controls validation of agent IPs and 
  hostnames. The first time the agent connects, its IP and 
  hostname will be saved. In subsequent connections, if 
  either has changed, the agent will be prevented from 
  coming online.",
  "winRSAgent": "The agent to use for running agent 
  installation processes on Windows machines. The agent must 
  be installed on a Windows machine."
}

```

## Example JSON request

```
{
  "minimumPasswordLength": "9",
  "requireComplexPasswords": "true"
}
```

Related REST command: [Update the system configuration](rest_cli_systemconfiguration_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

