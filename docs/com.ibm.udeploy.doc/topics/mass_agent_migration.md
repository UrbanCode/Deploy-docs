# Migrating Agents to Web

Agent Configuration Templates allow you to migrate JMS agents on a server to Web agents with the ability to revert back to the original JMS configuration. This allows you to specify connection details for groups of agents.

## Prerequisites

You must upgrade agents and server to IBM UrbanCode Deploy 7.0.1. For more information see[Upgrading agents](../../com.ibm.udeploy.install.doc/topics/upgradeAgents.md#) and [Upgrading the server](../../com.ibm.udeploy.install.doc/topics/upgradeInstall.md#).

## About this task

IBM UrbanCode Deploy 7.0 introduced a new server/agent communication protocol which offers many performance improvements, and increased scalability. See [Web agents](web_agents.md#). UrbanCode Deploy 7.0.1 is extending this capability by adding Agent Configuration Templates which will allow you to define a reusable set of configuration that can be used to easily migrate existing JMS agents to WEB agents.

## Agent Configuration Templates

Before you can migrate an agents from JMS to Web an Agent Configuration Template will need to be assigned to the agent or agents.

1.  Click **Resources**\>**Agent Configuration Templates**.
2.  Click on **Create Agent Configuration Template** on the right side of the page.
3.  Give the template a name and description in the designated boxes.
4.  Add teams that you want to give access.
5.  Enter the URLs of the servers or relays where you would like agents to connect.
6.  Click **Save**.
7.  Click on the template name and click **Add Agents** to apply agents to the specific template.

After agents are added to templates they can be migrated to the new Web type.

## Agent Migration

Before you can change agents types from the Agents page an Agent Configuration Template will need to be assigned to the agents.

1.  Click **Resources** \>**Agents**.
2.  Select the agents that you want to convert.
3.  Click bulk **Actions** menu.
4.  From the **Actions** drop down dialog you can select **Migrate to Web** or **Revert to JMS**.

If an agent is currently on a template there will be an icon next to **Type** on the **Agents** page. Clicking that icon will also prompt for agent migration.

A confirmation message will appear when the migration was successfully started on all agents.

The connection setting on newly migrated agents will be taken from the Agent Configuration Template that the agents belong to.

**Note:** If migration fails you can view the logs by clicking on the agent name and then clicking on the **Logs** section of specified agent.

**Parent topic:** [Agents and agent relay configuration](../topics/configure_agents.md)

