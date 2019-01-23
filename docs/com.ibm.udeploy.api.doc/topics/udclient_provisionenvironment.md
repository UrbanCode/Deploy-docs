# provisionEnvironment

Provision a cloud environment

This command provisions an instance of an application blueprint and creates an application environment based on that blueprint.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  provisionEnvironment [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "application": "Application name or ID (required if you 
  are specifying the blueprint by name",
  "baseResource": "Path to the resource node to create 
  this environment in",
  "blueprint": "Blueprint name or ID",
  "cleanupCountToKeep": "Number of most recently deployed 
  versions to keep (optional)",
  "cleanupDaysToKeep": "Number of days to keep versions 
  deployed to this environment (optional)",
  "color": "HTML color code for the environment (optional)",
  "description": "Description (optional)",
  "historyCleanupDaysToKeep": "Number of days to keep 
  application process history for this environment 
  (optional)",
  "lockSnapshots": "Whether snapshots will be locked when 
  deployed to this environment (optional)",
  "name": "Environment name",
  "noSelfApprovals": "When this option is selected, users 
  that submit deployment requests cannot approve their own 
  requests (optional)",
  "nodeProperties": {"Path to the resource node, such as 
  /path/to/resource/node": {"Name of node property": "Value 
  or node property"}},
  "requireApprovals": "Whether approvals will be required 
  (optional)",
  "requireSnapshot": "If enabled, all deployments must use 
  a snapshot instead of loose versions (optional)"
}

```

## Examples

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  provisionEnvironment newEnvironment.json
```

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  provisionEnvironment -file newEnvironment.json
```

## Example JSON requests

How you structure the JSON request depends on whether you assign the virtual nodes to a cloud group or an environment profile. For more information on cloud groups and environment profiles, see the documentation for your cloud system.

The following example creates an environment that is named `CloudEnv1` from a blueprint that is named `My application`. In this case, the `cloud_group` property is at the root of the JSON string, which specifies that the nodes will receive IP addresses from the same cloud group.

```
{
  "name": "CloudEnv1",
  "application": "My application",
  "baseResource": "/environments",
  "blueprint": "Blueprint 1",
  "description": "New cloud environment from blueprint 1",
  "lockSnapshots": "false",
  "requireApprovals": "false",
  "cloud_group": "2",
  "nodeProperties": {
    "/UCD Agent/os_part": {
      "multiplicity": "1",
      "numvcpus": "1",
      "memsize": "1024",
      "password": "password",
      "password_0": "password"
    }
  }
}
```

You can also specify IP addresses for the nodes individually. In this case, you specify an environment profile to use for the request and then a cloud group and IP group for each node. The following example has two nodes, and each uses a different cloud group and IP group.

```
{
  "name": "CloudEnv2",
  "application": "My application",
  "baseResource": "/environments",
  "blueprint": "Blueprint 1",
  "description": "New cloud environment from blueprint 1",
  "lockSnapshots": "false",
  "requireApprovals": "false",
  "environment_profile": "1",
  "nodeProperties": {
    "/UCD Agent/os_part": {
      "cloud_group": "1",
      "ip_group": "1",
      "multiplicity": "1",
      "numvcpus": "1",
      "memsize": "1024",
      "password": "password",
      "password_0": "password"
    },
    "/UCD Agent/os_part0": {
      "cloud_group": "2",
      "ip_group": "2",
      "multiplicity": "1",
      "numvcpus": "1",
      "memsize": "1024",
      "password": "password",
      "password_0": "password"
    }
  }
}
```

**Note:** You must specify cloud groups, IP groups, and environment profiles by ID, not by name. In most cases, to get the ID, open the cloud system console, open the group or profile, and find the ID in the URL in your web browser. In other cases, the ID is shown on the cloud system console.

To specify parameters on script packages on the nodes, add the information to the `nodeProperties` array. The following example assumes a script package named `iwd_registration` with a parameter named `cloud_hostname`:

```
{
  "name": "CloudEnv3",
  "application": "My application",
  "baseResource": "/environments",
  "blueprint": "Blueprint 1",
  "description": "New cloud environment from blueprint 1",
  "lockSnapshots": "false",
  "requireApprovals": "false",
  "cloud_group": "2",
  "nodeProperties": {
    "/UCD Agent/os_part": {
      "multiplicity": "1",
      "numvcpus": "1",
      "memsize": "1024",
      "password": "password",
      "password_0": "password",
      "iwd_registration/cloud_hostname": "cloudserver.example.org"
    }
  }
}
```

## Example response

```
{
  "id": "d84f5683-b05f-4e8b-afdf-f28a38b0fece",
  "securityResourceId": "2eb5db02-b07e-4010-a0cf-3b84509d0ca4",
  "name": "CloudEnv1",
  "description": "New cloud environment",
  "color": "#ffffff",
  "requireApprovals": false,
  "lockSnapshots": false,
  "calendarId": "7aac87db-3984-4cde-98be-a935fd38bdb0",
  "active": true,
  "cleanupDaysToKeep": 0,
  "cleanupCountToKeep": 0,
  "conditions": [
  ]
}
```

Related REST command: [Provision a cloud environment](rest_cli_environment_provisionenvironment_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

