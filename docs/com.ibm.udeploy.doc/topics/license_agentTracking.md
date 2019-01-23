# Tracking agent usage

You can track daily agent usage. Agent usage can provide a rough estimate of agent license use.

HCL® UrbanCode™ Deploy records the number of agents online and the maximum number of agents deploying at a time. Both measurements are referred to as the agent high-water mark. The records are updated very 10 minutes and are aggregated at the end of the day.

Although the agent usage records do not correspond precisely to agent license use, they can provide useful estimates of agent license use. These estimates can be especially useful for installations of HCL UrbanCode Deploy on z/Linux™. If you are using z/Linux, IBM recommends that you review your agent high-water totals quarterly. If you discover that you significantly or routinely exceed your licenses, contact your IBM sales representative to ensure that your installation remains compliant.

The agent usage records can be accessed at the following REST API endpoint:

```
https://{hostname}:{port}/cli/agentCLI/usage

```

The REST endpoint returns a JSON object with both the highest number of agents online for the day, and the maximum number of agents deploying at a time. A typical JSON object returned by the command is shown in the following example: `{"onlineAgents":5,"agentsrunningDeployments":4}`.

Both measurements are referred to as the agent high-water mark. For information about the CLI command, see [getHighWatermarks](../../com.ibm.udeploy.api.doc/topics/udclient_gethighwatermarks.md). For information about the REST API method, see [Return high watermarks for agent usage](../../com.ibm.udeploy.api.doc/topics/rest_cli_agentcli_usage_get.md).

**Parent topic:** [License management](../topics/licenseManage.md)

